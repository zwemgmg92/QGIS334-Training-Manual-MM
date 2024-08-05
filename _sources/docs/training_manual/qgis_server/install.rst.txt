.. index:: QGIS Server; WMS Server; WFS Server; WCS Server

.. _`label_qgisserver_tutorial`:

သင်ခန်းစာ - QGIS Server ကို Install ပြုလုပ်ခြင်း (Lesson: Install QGIS Server)
===============================================================================

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Debian Stretch ပေါ်တွင် **QGIS Server** ကို install ပြုလုပ်နည်းကို လေ့လာရန်။ Ubuntu နှင့် ၎င်း၏ ဆင့်ပွားများကဲ့သို့ Debian ကိုအခြေခံသည့်အရာများအတွက်လည်း လိုက်လုပ်နိုင်ပါသည်။

.. note:: Ubuntu တွင် admin permission လိုအပ်သော command များရှေ့တွင် ``sudo`` ကြိုထည့်ပေးပြီး ပုံမှန် user အဖြစ်အသုံးပြုနိုင်ပါသည်။ Debian တွင် ``sudo`` အသုံးပြုရန်မလိုအပ်ပဲ admin (``root``) အနေဖြင့် လုပ်ဆောင်နိုင်ပါသည်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ - Package များမှ Install ပြုလုပ်ခြင်း (Follow Along: Install from packages)
--------------------------------------------------------------------------------------------------------------------------

ယခုသင်ခန်းစာတွင် `ဤ <https://qgis.org/en/site/forusers/alldownloads.html#linux>`_ တွင် ပြထားသည့်အတိုင်း package များမှ install ပြုလုပ်ခြင်းကိုသာ လုပ်ဆောင်သွားမည်ဖြစ်သည်။

QGIS Server ကို အောက်ပါအတိုင်း install ပြုလုပ်ပါ-

.. code-block:: bash

 apt install qgis-server --no-install-recommends --no-install-suggests

 # if you want to install server plugins, also:
 apt install python3-qgis

QGIS Server ကိုအသုံးပြုရာတွင် QGIS Desktop (တွဲဖက် X Server နှင့်အတူ) ကို install မပြုလုပ်ထားပဲ အသုံးပြုသင့်ပါသည်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ - QGIS Server Executable (Follow Along: QGIS Server Executable)
--------------------------------------------------------------------------------------------------------------

QGIS Server executable သည် ``qgis_mapserv.fcgi`` ဖြစ်ပါသည်။ ၎င်းကို မည်သည့်နေရာတွင် install ပြုလုပ်ထားသည်ကို စစ်ဆေးရန် ``find / -name 'qgis_mapserv.fcgi'`` ကို run ကြည့်နိုင်ပြီး output သည် ``/usr/lib/cgi-bin/qgis_mapserv.fcgi`` ဆိုသည့်ပုံစံမျိုး ဖြစ်သင့်ပါသည်။

Command line စမ်းသပ်မှုတစ်ခု ပြုလုပ်လိုပါက ``/usr/lib/cgi-bin/qgis_mapserv.fcgi --version`` command ကို run နိုင်ပြီး output သည် အောက်ပါပုံစံအတိုင်း ထွက်လာသင့်ပါသည်-

::

 QGIS 3.21.0-Master 'Master' (1c70953f1e)
 QGIS code revision 1c70953f1e
 Qt version 5.15.2
 Python version 3.9.5
 GDAL/OGR version 3.2.2
 PROJ version 7.2.1
 EPSG Registry database version v10.008 (2020-12-16)
 GEOS version 3.9.0-CAPI-1.16.2
 SQLite version 3.34.1
 OS Ubuntu 21.04


နောက်ပိုင်းတွင် WMS တောင်းဆိုမှုများ ပြုလုပ်နည်းကို တွေ့ရမည်ဖြစ်သည်။

:abbr:`★★★ (Advanced level)` HTTP Server ပြင်ဆင်သတ်မှတ်ခြင်း (HTTP Server Configuration)
-----------------------------------------------------------------------------------------

Install ပြုလုပ်ထားသော QGIS server ကို Internet Browser တစ်ခုမှနေပြီး အသုံးပြုခွင့်ရရှိရန် HTTP server တစ်ခုကိုအသုံးပြုရန် လိုအပ်ပါသည်။ Apache HTTP Server installation လုပ်ငန်းစဉ်ကို :ref:`httpserver` အပိုင်းတွင် အသေးစိတ်ရှင်းပြထားပါသည်။

.. note::

 X Server (Linux Desktop ထဲတွင် ပါဝင်သော)တစ်ခုကို မ run ပဲ QGIS Server ကို install ပြုလုပ်ခဲ့ပြီး ``GetPrint`` command ကိုလည်း အသုံးပြုလိုလျှင် fake (အတုအယောင်) X Server တစ်ခုကို install ပြုလုပ်သင့်ပြီး ၎င်းအား QGIS Server မှအသုံးပြုရန် လုပ်ဆောင်ပေးသင့်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် :ref:`Xvfb installation process <xvfb>` အတိုင်းလိုက်လုပ်ကြည့်နိုင်ပါသည်။


:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ - နောက်ထပ် virtual host ဖန်တီးခြင်း (Follow Along: Create another virtual host)
------------------------------------------------------------------------------------------------------------------------------

QGIS Server သို့ဦးတည်သော နောက်ထပ် Apache virtual host ဖန်တီးကြည့်ပါမည်။ နှစ်သက်ရာအမည် (``coco.bango`` ၊ ``super.duper.training`` ၊
``example.com`` ၊ အစရှိသဖြင့်) ရွေးချယ်ပေးနိုင်ပါသည်၊ သို့သော် ရိုးရှင်းစေရန်အတွက် ``myhost`` ဟူသောအမည်ကို အသုံးပြုပါမည်။

* Localhost IP သို့ဦးတည်ရန် ``myhost`` အမည်ကို set up လုပ်ကြည့်ပါမည်၊ လုပ်ဆောင်ရာတွင် ``sh -c "echo '127.0.0.1 myhost' >> /etc/hosts"`` command ကိုအသုံးပြု၍ :file:`/etc/hosts` တွင် ``127.0.0.1 x`` ထည့်သွင်းပါ သို့မဟုတ် ``gedit /etc/hosts`` ဖြင့်ဖိုင်ကို edit ပြုလုပ်ပါ။
* ``myhost`` သည် localhost သို့ဦးတည်ခြင်းရှိမရှိကို terminal ထဲတွင် ``ping myhost`` command ဖြင့်စစ်ဆေးကြည့်နိုင်ပါသည်၊ output သည်အောက်ပါအတိုင်းဖြစ်ပါလိမ့်မည်-

.. code-block:: bash

   qgis@qgis:~$ ping myhost
   PING myhost (127.0.0.1) 56(84) bytes of data.
   64 bytes from localhost (127.0.0.1): icmp_seq=1 ttl=64 time=0.024 ms
   64 bytes from localhost (127.0.0.1): icmp_seq=2 ttl=64 time=0.029 ms

* ``myhost`` မှ QGIS Server အားရယူသုံးစွဲနိုင်ခြင်းရှိမရှိကို ``curl http://myhost/cgi-bin/qgis_mapserv.fcgi`` ကိုအသုံးပြု၍ဖြစ်စေ Debian box browser မှတဆင့် URL ကို ယူသုံး၍ဖြစ်စေ စမ်းသပ်ကြည့်နိုင်ပါသည်။ အောက်ပါအတိုင်း ပြန်ထုတ်ပေးကောင်း ပေးပါလိမ့်မည်-

.. code-block:: html

   <!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
   <html><head>
   <title>404 Not Found</title>
   </head><body>
   <h1>Not Found</h1>
   <p>The requested URL /cgi-bin/qgis_mapserv.fcgi was not found on this server.</p>
   <hr>
   <address>Apache/2.4.25 (Debian) Server at myhost Port 80</address>
   </body></html>

* Apache သည် ``myhost`` server သို့ဦးတည်သော request များကို သူကိုယ်တိုင်ဖြေရှင်းရမည်ကို မသိသေးပါ။ Virtual host ကို အရိုးရှင်းဆုံးနည်းလမ်းဖြင့် set up ပြုလုပ်ရန် :file:`qgis.demo.conf` နှင့်အကြောင်းအရာတူညီသော :file:`/etc/apache2/sites-available` ဖိုင်လမ်းကြောင်းထဲတွင် ``myhost.conf`` ဖိုင်တစ်ခုကို ပြုလုပ်ပေးရမည်ဖြစ်သည်၊ သို့သော် ``ServerName`` line တွင် ``ServerName myhost`` ဟူ၍ ဖြစ်သင့်ပါသည်။ Log (လုပ်ဆောင်မှုမှတ်တမ်း) များ ရှိမည့်နေရာကိုလည်း ပြောင်းလဲပေးနိုင်ပါသည်၊ သို့သော် ၎င်းကို မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ။
* ``a2ensite myhost.conf`` ဖြင့် virtual host ကို enable လုပ်ပေးပြီး ``service apache2 reload`` ဖြင့် Apache service အား reload လုပ်ပါ။
*  http://myhost/cgi-bin/qgis_mapserv.fcgi url အား အသုံးပြုနိုင်ပြီ ဖြစ်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

QGIS Server ဗားရှင်းအမျိုးမျိုးအား Debian အခြေခံသော Linux distros ပေါ်တွင် package များမှ install ပြုလုပ်နည်း၊ Apache အား QGIS Server ဖြင့်ပြင်ဆင်သတ်မှတ်နည်းကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်။ 

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ယခုဆိုလျှင် QGIS Server အား install ပြုလုပ်ပြီးဖြစ်ကာ HTTP protocol မှတဆင့် အသုံးပြုနိုင်ပြီဖြစ်ပါသည်၊ ၎င်းမှ လုပ်ဆောင်ပေးနိုင်သော service အချို့ကို မည်သို့ရယူသုံးစွဲရမည်ကို လေ့လာရန်လိုအပ်ပါသည်။ နောက်လာမည့်သင်ခန်းစာတွင် QGIS Server WMS service များကို မည်သို့ရယူသုံးစွဲရမည်ကို လေ့လာရမည်ဖြစ်သည်။
