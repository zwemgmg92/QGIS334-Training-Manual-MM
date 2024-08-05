သင်ခန်းစာ - WMS ဝန်ဆောင်မှုပေးခြင်း (Lesson: Serving WMS)
===============================================================================

ဤလေ့ကျင့်ခန်းအတွက် အသုံးပြုမည့် data များသည် သင်ဒေါင်းလုဒ်ပြုလုပ်ထားသော :ref:`training data <data_downloadlink>` ထဲရှိ :file:`qgis-server-tutorial-data` ထဲတွင် ရှိပါသည်။ အဆင်ပြေပြေဖြစ်စေရန်နှင့် သုံးစွဲခွင့်ပြဿနာများမရှိစေရန် ထိုဖိုင်များကို :file:`/home/qgis/projects` ထဲတွင် သိမ်းဆည်းထားသည်ဟု ယူဆပါမည်။ ထို့ကြောင့် အောက်ပါညွှန်ကြားချက်များအတိုင်း လုပ်ဆောင်ပါ။

နမူနာ data တွင် :file:`world.qgs` ဆိုသည့် QGIS project တစ်ခုပါဝင်ပြီး ထို project သည် QGIS Server ဖြင့် serve လုပ်ရန် ပြင်ဆင်ထားပြီးသားဖြစ်ပါသည်။ သင့်ကိုယ်ပိုင် project အားအသုံးပြုလိုလျှင် သို့မဟုတ် project တစ်ခုအားမည်သို့ ပြင်ဆင်ရမည်ကို လေ့လာရန် :ref:`Creatingwmsfromproject` တွင် ကြည့်ရှုပါ။

.. note::

 ဤမော်ဂျူးတွင် parameter များနှင့် parameter တန်ဖိုးများကို အလွယ်တကူခွဲခြားနိုင်စေရန် URL များကို တင်ပြထားပါသည်။ ပုံမှန် format သည်အောက်ပါအတိုင်းဖြစ်ပြီး-

 ::

   ...&field1=value1&field2=value2&field3=value3

 ယခု tutorial တွင်အသုံးပြုထားသည်မှာ-

 ::

   &field1=value1
   &field2=value2
   &field3=value3

 ၎င်းတို့ကို Mozilla Firefox ထဲတွင် ကူးထည့်ပါက ကောင်းမွန်စွာအလုပ်ဖြစ်သော်လည်း Chrome ကဲ့သို့ အခြား web browser များထဲတွင် ``field:parameter`` အတွဲများအကြား space အပိုများ ပါနိုင်ပါသည်။ ထို့ကြောင့် အဆိုပါပြဿနာမျိုးနှင့်ကြုံတွေ့ရပါက Firefox ကိုအသုံးပြုနိုင်သလို URL ကို line တစ်ခုတည်းဖြစ်အောင် မွမ်းမံပြင်ဆင်ပြီး အသုံးပြုနိုင်ပါသည်။

Web browser ထဲတွင် WMS GetCapabilities request တစ်ခုပြုလုပ်ကြည့်ပါမည်-

.. code-block:: bash

 http://qgisplatform.demo/cgi-bin/qgis_mapserv.fcgi
 ?SERVICE=WMS
 &VERSION=1.3.0
 &REQUEST=GetCapabilities
 &map=/home/qgis/projects/world.qgs

ယခင်သင်ခန်းစာထဲမှ Apache config ထဲတွင် ``QGIS_PROJECT_FILE`` variable သည် default project အား :file:`/home/qgis/projects/world.qgs` အဖြစ်သတ်မှတ်ပါသည်။ သို့သော် အထက်ဖော်ပြပါ request ထဲတွင် ရှင်းရှင်းလင်းလင်းဖြစ်စေရန်နှင့် ၎င်းအား မည်သည့် project မဆိုသို့ညွှန်းပေးရန်အသုံးပြုနိုင်ကြောင်း ပြသရန် **map** parameter ကိုအသုံးပြုထားပါသည်။ Request ထဲတွင် **map** parameter အားဖျက်လိုက်လျှင်လည်း QGIS Server သည် အတူတူပင် တုံ့ပြန်ပါလိမ့်မည်။

WMS client တစ်ခုခုအား ``GetCapabilities`` URL သို့ညွှန်ပေးခြင်းအားဖြင့် Web Map Server ၏အချက်အလက် meta များပါဝင်သော XML document တစ်ခုကိုရရှိမည်ဖြစ်သည်၊ ဥပမာ- serve လုပ်ထားသည့် layer များ၊ လွှမ်းခြုံသောနယ်နိမိတ်အတိုင်းအတာ၊ အသုံးပြုထားသည့် format ၊ WMS ဗားရှင်း ၊ အစရှိသည်တို့ ပါဝင်ပါသည်။

QGIS သည်လည်း :ref:`ogc-wms` တစ်ခုဖြစ်သောကြောင့် GetCapabilities url ဖြင့် WMS server connection တစ်ခုကိုဖန်တီးနိုင်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် :ref:`wms-services` သို့မဟုတ် :ref:`ogc-wms-servers` တွင် ကြည့်ပါ။

သင့် QGIS project ထဲသို့ ``countries`` WMS layer ကိုထည့်သွင်းသောအခါ အောက်ပါပုံအတိုင်း ရရှိပါလိမ့်မည်-

.. figure:: img/qgis_getmap_request.png
   :align: center

   QGIS Desktop တွင် QGIS Server countries layer WMS service ကိုအသုံးပြုထားပုံ

.. note::

 QGIS Server သည် :file:`world.qgs` project ထဲတွင် သတ်မှတ်ထားသော layer များကို serve လုပ်ပေးပါသည်။ QGIS တွင် project ကိုဖွင့်ခြင်းအားဖြင့် countries layer အတွက် style များစွာကို မြင်တွေ့နိုင်ပါသည်။ QGIS Server သည် ထိုကိစ္စကိုလည်း ဂရုပြုလုပ်ဆောင်ပေးပြီး request ထဲတွင် လိုချင်သည့် style ကို ရွေးချယ်ပေးနိုင်ပါသည်။ အထက်ဖော်ပြပါပုံတွင် ``classified_by_population`` style ကိုရွေးချယ်ထားပါသည်။

မှတ်တမ်း (Logging)
-------------------

Server တစ်ခုကို set up လုပ်သောအခါ မည်သည့်အရာများဖြစ်ပျက်နေသည်ကို ပြသရန် log (မှတ်တမ်း) များသည် အမြဲတမ်းအရေးကြီးပါသည်။ :file:`*.conf` ဖိုင်ထဲတွင် အောက်ပါ log များကို set up လုပ်ထားပါသည်-

* QGIS Server log အား :file:`/logs/qgisserver.log` တွင်
* ``qgisplatform.demo`` Apache access log အား :file:`qgisplatform.demo.access.log` တွင်
* ``qgisplatform.demo`` Apache error log အား :file:`qgisplatform.demo.error.log` တွင်

Log ဖိုင်များသည် ရိုးရိုးစာသားဖိုင်များသာဖြစ်ပြီး ၎င်းတို့ကို text editor အသုံးပြုပြီး စစ်ဆေးကြည့်နိုင်ပါသည်။ Terminal ထဲတွင်လည်း ``tail`` command ကိုအသုံးပြုနိုင်ပါသည်- ``sudo tail -f /logs/qgisserver.log``

ထိုသို့လုပ်ခြင်းဖြင့် log ဖိုင်ထဲတွင် ရေးသားသည်များကို terminal ထဲတွင် output ထုတ်ပေးပါလိမ့်မည်။ Log ဖိုင် တစ်ခုချင်းစီအတွက် အောက်ပါအတိုင်း terminal ၃ ခုကိုလည်း ဖွင့်ထားနိုင်ပါသည်-

.. figure:: img/terminal_tail_log.jpg
   :align: center

   QGIS Server logs output များကို မြင်ရနိုင်စေရန် ``tail`` command အားအသုံးပြုခြင်း

QGIS Server WMS service များအား QGIS Desktop တွင် အသုံးပြုသောအခါ QGIS မှ Server သို့ပေးပို့သော request များအားလုံးကို access log ထဲတွင်လည်းကောင်း၊ QGIS Server ၏ error များကို QGIS Server log ထဲတွင်လည်းကောင်း အစရှိသဖြင့် တွေ့နိုင်ပါသည်။

.. note::

 * အောက်ပါအပိုင်းများထဲမှ log များကို ကြည့်ပါက ပိုမိုနားလည်သဘောပေါက်မည်ဖြစ်သည်။
 * QGIS Server log ကိုကြည့်နေစဉ်တွင် Apache ကို ပြန်လည်စတင်ပါက မည်သို့အလုပ်လုပ်ဆောင်နေသည်ကို မြင်တွေ့ရနိုင်ပါသည်။

GetMap requests
-------------------------------------------------------------------------------

QGIS Desktop တွင် ``countries`` layer ကိုပြသရန် အခြား WMS client များကဲ့သို့ ``GetMap`` request ကိုအသုံးပြုပါသည်။

ရိုးရှင်းသော request တစ်ခု၏ပုံစံမှာ-

.. code-block:: bash

 http://qgisplatform.demo/cgi-bin/qgis_mapserv.fcgi
 ?MAP=/home/qgis/projects/world.qgs
 &SERVICE=WMS
 &VERSION=1.3.0
 &REQUEST=GetMap
 &BBOX=-432786,4372992,3358959,7513746
 &SRS=EPSG:3857
 &WIDTH=665
 &HEIGHT=551
 &LAYERS=countries
 &FORMAT=image/jpeg

အထက်ဖော်ပြပါ request သည် အောက်ပါပုံကို ထုတ်ပေးပါလိမ့်မည်-

**Figure: simple GetMap request to QGIS Server**

.. figure:: img/getmap_simple_request.jpg
   :align: center

   ရိုးရှင်းသော GetMap request တစ်ခုအား QGIS Server မှ တုံ့ပြန်ပုံ

:abbr:`★★☆ (Moderate level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - Image နှင့် Layer parameter များပြောင်းလဲခြင်း (Try Yourself: Change the Image and Layers parameters)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

အထက်ဖော်ပြပါ request ကိုအခြေခံ၍  ``countries`` layer အား နောက်ထပ် layer တစ်ခုဖြင့် အစားထိုးကြည့်ပါမည်။

အခြား ရရှိနိုင်သည့် layer များကိုကြည့်ရန် QGIS ထဲတွင် :file:`world.qgs` project ကိုဖွင့်ပြီး ၎င်းတွင်ပါဝင်သည်များကို ကြည့်နိုင်ပါသည်။ စိတ်ထဲမှတ်သားထားရမည်မှာ WMS client များသည် QGIS project ထဲသို့ဝင်ရောက်သုံးစွဲခွင့်မရှိပါ၊ ၎င်းတို့သည် အကြောင်းအရာများကိုသာ ကြည့်ရှုခြင်းဖြစ်သည်။

ထို့အပြင် WMS service လုပ်ဆောင်နေစဉ်တွင် QGIS project ထဲရှိ layer အချို့ကို QGIS မှလျစ်လျူရှုစေရန်အတွက် configuration option တစ်ခုလည်းရှိပါသည်။

ထို့ကြောင့် QGIS Desktop ကို ``GetCapabilities`` URL သို့ညွှန်းပေးသောအခါ layer စာရင်းတွင်ကြည့်နိုင်သလို ``GetCapabilities`` XML ထဲတွင် အခြား layer အမည်များကို ကိုယ်တိုင်ရှာဖွေနိုင်ပါသည်။

Layer အမည်များထဲမှ တစ်ခုသည် ``countries_shapeburst`` ဖြစ်ပါသည်။ အခြား layer များကိုရှာဖွေနိုင်သော်လည်း အချို့ layer များသည် စကေးငယ်သောအခြေအနေတွင် မြင်ရနိုင်မည်မဟုတ်ပဲ ဗလာ image တစ်ခုကိုသာ ပြန်ထုတ်ပေးပါလိမ့်မည်။

အထက်တွင်ဖော်ပြထားသော အခြား parameter များကိုလည်း ပြောင်းလဲကြည့်နိုင်ပါသည်၊ ဥပမာ- ပြန်ထုတ်ပေးမည့် image အမျိုးအစားကို ``image/png`` သို့ပြောင်းလဲပေးခြင်းဖြစ်သည်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ - စစ်ထုတ်ခြင်း ၊ အလင်းပိတ်နှုန်းနှင့် Style သတ်မှတ်ချက်များ အသုံးပြုခြင်း (Follow Along: Use Filter, Opacities and Styles parameters)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

နောက်ထပ် layer တစ်ခု ၊ :ref:`အခြေခံ parameter များ <services_basics>` ၊ **FILTER** နှင့် **OPACITIES** များထည့်သွင်းရန် နောက်ထပ် request တစ်ခုလုပ်ကြည့်ပါမည်။ စံ STYLE parameter ကိုလည်း အသုံးပြုမည်ဖြစ်ပါသည်။

.. code-block:: bash

 http://qgisplatform.demo/cgi-bin/qgis_mapserv.fcgi
 ?MAP=/home/qgis/projects/world.qgs
 &SERVICE=WMS
 &VERSION=1.3.0
 &REQUEST=GetMap
 &BBOX=-432786,4372992,3358959,7513746
 &SRS=EPSG:3857
 &WIDTH=665
 &HEIGHT=551
 &FORMAT=image/jpeg
 &LAYERS=countries,countries_shapeburst
 &STYLES=classified_by_name,blue
 &OPACITIES=255,30
 &FILTER=countries:"name" IN ( 'Germany' , 'Italy' )

အောက်ပါ image အတိုင်း output ရပါလိမ့်မည်-

.. figure:: img/getmap_filter_opacities.jpg
   :align: center

   FILTER နှင့် OPACITIES parameter များပါဝင်သော GetMap request တစ်ခု၏ တုံ့ပြန်ပုံ

အထက်ပါပုံတွင် မြင်တွေ့ရသည့်အတိုင်း countries layer မှ **Germany** နှင့် **Italy** ကိုသာ ပုံဖော်ပြသရန် QGIS Server အား ပြောလိုက်ခြင်းဖြစ်သည်။ 

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ - Redlining အသုံးပြုခြင်း (Follow Along: Use Redlining)
------------------------------------------------------------------------------------------------------

:ref:`အခြေခံများ <services_basics>` အပိုင်းတွင် အသေးစိတ်ဖော်ပြထားသော :ref:`redlining <wms_redlining>` feature နှင့် **SELECTION** parameter အသုံးပြုရန် နောက်ထပ် GetMap request တစ်ခုလုပ်ကြည့်ပါမည်-

.. code-block:: bash

 http://qgisplatform.demo/cgi-bin/qgis_mapserv.fcgi
 ?MAP=/home/qgis/projects/world.qgs
 &SERVICE=WMS
 &VERSION=1.3.0
 &REQUEST=GetMap
 &BBOX=-432786,4372992,3358959,7513746
 &SRS=EPSG:3857
 &WIDTH=665
 &HEIGHT=551
 &LAYERS=countries,countries_shapeburst
 &FORMAT=image/jpeg
 &HIGHLIGHT_GEOM=POLYGON((590000 6900000, 590000 7363000, 2500000 7363000, 2500000 6900000, 590000 6900000))
 &HIGHLIGHT_SYMBOL=<StyledLayerDescriptor><UserStyle><Name>Highlight</Name><FeatureTypeStyle><Rule><Name>Symbol</Name><LineSymbolizer><Stroke><SvgParameter name="stroke">%233a093a</SvgParameter><SvgParameter name="stroke-opacity">1</SvgParameter><SvgParameter name="stroke-width">1.6</SvgParameter></Stroke></LineSymbolizer></Rule></FeatureTypeStyle></UserStyle></StyledLayerDescriptor>
 &HIGHLIGHT_LABELSTRING=QGIS Tutorial
 &HIGHLIGHT_LABELSIZE=30
 &HIGHLIGHT_LABELCOLOR=%23000000
 &HIGHLIGHT_LABELBUFFERCOLOR=%23FFFFFF
 &HIGHLIGHT_LABELBUFFERSIZE=3
 &SELECTION=countries:171,65

အထက်ပါ request အား web browser ထဲတွင် ကူးထည့်ပါက အောက်ပါပုံအတိုင်း ပြန်ထုတ်ပေးပါလိမ့်မည်-

.. figure:: img/getmap_redlining_selection.jpg
   :align: center

   REDLINING feature နှင့် SELECTION parameter ပါဝင်သော request တစ်ခုမှ တုံ့ပြန်ပုံ

အထက်ပါပုံတွင် မြင်ရသည့်အတိုင်း id 171 နှင့် id 65 ရှိသော နိုင်ငံများ (Romania နှင့် France) ကို အဝါရောင်ဖြင့် highlight ပြရန် **SELECTION** parameter ကိုအသုံးပြုခြင်းဖြစ်ပြီး **QGIS Tutorial** ဆိုသည့် label ပါရှိသော ထောင့်မှန်စတုဂံအကွက်အတွက် **REDLINING** feature ကိုအသုံးပြုခဲ့ပါသည်။

GetPrint requests
-------------------

QGIS Server ၏အလွန်ကောင်းမွန်သောအရာတစ်ခုသည် QGIS Desktop print layout များကို ပြုလုပ်နိုင်ခြင်းဖြစ်သည်။ ထိုအကြောင်းကို :ref:`wms_getprint` အပိုင်းတွင် လေ့လာနိုင်ပါသည်။

:file:`world.qgs` project အား QGIS Desktop ဖြင့်ဖွင့်လျှင် ``Population distribution`` ဟုအမည်ပေးထားသော print layout တစ်ခုကို တွေ့ရပါလိမ့်မည်။ ရိုးရှင်းသော ``GetPrint``
request တစ်ခုမှာ-

.. code-block:: bash

 http://qgisplatform.demo/cgi-bin/qgis_mapserv.fcgi
 ?map=/home/qgis/projects/world.qgs
 &SERVICE=WMS
 &VERSION=1.3.0&
 REQUEST=GetPrint
 &FORMAT=pdf
 &TRANSPARENT=true
 &SRS=EPSG:3857
 &DPI=300
 &TEMPLATE=Population distribution
 &map0:extent=-432786,4372992,3358959,7513746
 &LAYERS=countries

.. figure:: img/getprint.jpg
   :align: center

   အထက်ပါ GetPrint request မှရရှိလာသော Pdf ရလာဒ်ကို ပြသပုံ 

ပုံမှန်အားဖြင့် ``GetMap`` ၊ ``GetPrint`` အစရှိသည့် request များကို ရေးသားရန် ခက်ခဲပါသည်။

`QGIS Web Client <https://github.com/qgis/qgis-web-client>`_ သို့မဟုတ် QWC သည် Web client project တစ်ခုဖြစ်ပြီး QGIS Server နှင့်တွဲဖက်အလုပ်လုပ်နိုင်သည့်အတွက် သင်၏ project များကို Web ပေါ်တွင် ဖြန့်ချိနိုင်မည်ဖြစ်ပါသည်၊ သို့မဟုတ် ပိုမိုနားလည်သဘောပေါက်စေရန်အတွက် QGIS Server request များဖန်တီးရာတွင် ကူညီပေးနိုင်ပါသည်။

၎င်းကို အောက်ပါအတိုင်း install ပြုလုပ်နိုင်ပါသည်-

* ``qgis`` ဆိုသည့် user အနေဖြင့် ``cd /home/qgis`` ဖိုင်လမ်းကြောင်းသို့သွားပါ။
* `ဤနေရာ <https://github.com/qgis/QGIS-Web-Client/archive/master.zip>`_ မှ QWC project ကို ဒေါင်းလုဒ်ရယူပြီး zip ဖြည်ပါ။
* ``/var/www/html`` ဖိုင်ကြောင်းသို့ညွှန်းသော ကိုယ်စားပြုလင့်ခ် တစ်ခုပြုလုပ်ပါ၊ အဘယ်ကြောင့်ဆိုသော် ၎င်းသည် virtual host configuration ထဲတွင် setup ပြုလုပ်ထားသော ``DocumentRoot`` ဖြစ်သောကြောင့်ဖြစ်သည်။ Archive အား :file:`/home/qgis/Downloads/QGIS-Web-Client-master` အောက်တွင် zip ဖြည်လျှင် ``sudo ln -s /home/qgis/Downloads/QGIS-Web-Client-master /var/www/html/`` ကိုအသုံးပြုပြီးပြုလုပ်နိုင်ပါသည်။
* Web browser တွင် http://qgisplatform.demo/QGIS-Web-Client-master/site/qgiswebclient.html?map=/home/qgis/projects/world.qgs ကိုဖွင့်ပါ။

ယခုအခါ အောက်ပါပုံအတိုင်း မြေပုံကို မြင်ရပါလိမ့်မည်-

.. figure:: img/qwc.jpg
   :align: center

   world.qgs project ကိုအသုံးပြုထားသော QGIS Web Client

QWC ထဲတွင် Print ခလုတ်ကိုနှိပ်လျှင် ``GetPrint`` request ကိုဖန်တီးနိုင်မည်ဖြစ်ပါသည်။ QWC ထဲတွင် ``?`` icon ကိုနှိပ်ပြီးလည်း အကူအညီများကို ရယူနိုင်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

WMS Service များရယူရန် QGIS Server အားမည်သို့အသုံးပြုရမည်ကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် လူသိများသော GRASS GIS အတွက် frontend တစ်ခုအဖြစ် QGIS အားမည်သို့အသုံးပြုရမည်ကို လေ့လာရမည်ဖြစ်သည်။ 
