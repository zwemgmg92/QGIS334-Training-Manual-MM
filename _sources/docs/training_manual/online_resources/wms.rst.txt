.. _`wms-services`:

သင်ခန်းစာ - Web Mapping Services (Lesson: Web Mapping Services)
===============================================================================

Web Mapping Service (WMS) တစ်ခုသည် remote server တစ်ခုပေါ်တွင်ရှိသော ဝန်ဆောင်မှုတစ်ခုဖြစ်ပါသည်။ ဝက်ဘ်ဆိုဒ် တစ်ခုနှင့်ဆင်တူပြီး server နှင့်အချိတ်အဆက်ရှိနေသမျှ ၎င်းကိုအသုံးပြုနိုင်မည်ဖြစ်သည်။ QGIS ကိုအသုံးပြု၍ သင်၏လက်ရှိ မြေပုံထဲသို့ WMS တစ်ခုကို တိုက်ရိုက်ထည့်သွင်းနိုင်ပါသည်။

Plugin များသင်ခန်းစာတွင် Google မှ raster image အသစ်တစ်ခုကို ထည့်သွင်းနိုင်သည်ကို သင်မှတ်မိပါလိမ့်မည်။ သို့သော် ၎င်းသည် တစ်ကြိမ်ထဲသာအပြီးဖြစ်ပြီး image ကိုဒေါင်းလုဒ်ပြုလုပ်ပြီးသည်နှင့် ပြောင်းလဲမှုမရှိတော့ပါ။ WMS သည် ၎င်းနှင့်မတူပဲ တိုက်ရိုက်ဝန်ဆောင်မှုတစ်ခုဖြစ်ပြီး မြေပုံပေါ်တွင် မြင်ကွင်းရွှေ့ခြင်း သို့မဟုတ် zoom အချုံ့/အချဲ့ပြုလုပ်ပါက အလိုအလျောက် refresh ဖြစ်သွားပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** WMS တစ်ခုကို အသုံးပြုတတ်စေရန်နှင့် ၎င်း၏ အကန့်အသတ်များကို နားလည်စေရန်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - WMS layer တစ်ခုထည့်သွင်းခြင်း (Follow Along: Loading a WMS Layer)
---------------------------------------------------------------------------------------------------------------

ဤလေ့ကျင့်ခန်းအတွက် သင်တန်းအစတွင် သင်ဖန်တီးခဲ့သော အခြေခံမြေပုံကိုအသုံးပြုနိုင်သလို မြေပုံအသစ်တစ်ခုစတင်ပြီး ရှိပြီးသား layer များကိုလည်း ထည့်သွင်းနိုင်ပါသည်။ ဤဥပမာတွင် မြေပုံအသစ်တစ်ခုကို အသုံးပြုပြီး မူရင်း :guilabel:`places` ၊ :guilabel:`landuse` နှင့် :guilabel:`protected_areas` layer များကိုထည့်သွင်းကာ သင်္ကေတများချိန်ညှိခဲ့ပါသည်-

.. figure:: img/new_map.png
   :align: center
   :width: 100%

#. အဆိုပါ layer များကို မြေပုံအသစ်တစ်ခုထဲသို့ ထည့်သွင်းပါ၊ သို့မဟုတ် သင့်မူရင်းမြေပုံကိုအသုံးပြုပြီး အဆိုပါ layer များကိုသာ မြင်နိုင်အောင် ဖွင့်ထားပါ။
#. WMS layer အား စတင်မထည့်သွင်းမီ "on the fly" projection (:menuselection:`Project --> Properties... --> CRS` tab ၊ :guilabel:`No CRS (or unknown/non-Earth projection)` ကိုအမှန်ခြစ်ပါ) အား ပိတ်ထားပါ။ ထိုသို့လုပ်ခြင်းသည် layer များကို မှန်ကန်စွာ ထပ်နေစေမည်တော့မဟုတ်ပါ၊ သို့သော် စိတ်ပူရန်မလိုပါ- နောက်ပိုင်းတွင် ပြန်လည်ပြင်ဆင်မည်ဖြစ်ပါသည်။
#. WMS layer များကို ထည့်သွင်းရန် |dataSourceManager| ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Data Source Manager` dialog ကိုဖွင့်ပါ၊ |addWmsLayer|
   :guilabel:`WMS/WMTS` tab ကိုဖွင့်ပေးပါ။

   .. figure:: img/datasourcemanager_wms.png
      :align: center

   သင်တန်း၏အစတွင် SpatiaLite သို့မဟုတ် GeoPackage database တစ်ခုနှင့်ချိတ်ဆက်နည်းကို သတိရပါ။ :guilabel:`landuse` ၊ :guilabel:`buildings` နှင့်
   :guilabel:`roads` layer များကို database တစ်ခုထဲတွင် သိမ်းဆည်းထားပါသည်။ အဆိုပါ layer များကိုအသုံးပြုရန် database နှင့်ဦးစွာ ချိတ်ဆက်ရန် လိုအပ်ပါသည်။ WMS တစ်ခုကိုအသုံးပြုခြင်းသည်လည်း layer များ remote server တစ်ခုထဲတွင် ရှိနေသည်မှလွဲ၍ ထိုနည်းတူပင်ဖြစ်သည်။

#. WMS တစ်ခုနှင့် ချိတ်ဆက်မှုအသစ်တစ်ခုဖန်တီးရန် :guilabel:`New` ခလုတ်ကိုနှိပ်ပါ။

   ဆက်လက်လုပ်ဆောင်ရန်အတွက် WMS address တစ်ခုလိုအပ်ပါသည်။ အင်တာနက်တွင် အခမဲ့ WMS server များစွာ ရှိပါသည်။ ၎င်းတို့ထဲမှ တစ်ခုသည် `terrestris
   <https://ows.terrestris.de/osm/service>`_ ဖြစ်ပြီး `OpenStreetMap
   <https://wiki.openstreetmap.org/wiki/Main_Page>`_ dataset များကိုအသုံးပြုထားပါသည်။

#. အဆိုပါ WMS ကိုအသုံးပြုရန် လက်ရှိ dialog ထဲတွင် ၎င်းကို အောက်ပါအတိုင်းသတ်မှတ်ပေးပါ-

   .. figure:: img/new_wms_connection.png
      :align: center

   * :guilabel:`Name` field တွင် ``terrestris`` ဖြစ်သင့်ပါသည်။
   * :guilabel:`URL` field တွင် ``https://ows.terrestris.de/osm/service`` ဖြစ်သင့်ပါသည်။
#. :guilabel:`OK` ကိုနှိပ်ပါ။ WMS server အသစ် ဝင်လာပါလိမ့်မည်-

   .. figure:: img/new_connection_listed.png
      :align: center

#. :guilabel:`Connect` ကိုနှိပ်ပါ။ စာရင်းထဲတွင် အောက်ပါ entry အသစ်များထည့်သွင်းပေးသွားမည်ဖြစ်သည်-

   .. figure:: img/new_wms_entries.png
      :align: center

   အဆိုပါ layer များအားလုံးသည် ဤ WMS server တွင်ရှိသော layer များဖြစ်သည်။

#. :guilabel:`OSM-WMS` layer ပေါ်တွင် click တစ်ချက်နှိပ်ပါ။ ထိုအခါ အသုံးပြုထားသော default :guilabel:`Coordinate Reference System` ကိုပြသလိမ့်မည်ဖြစ်ပြီး dataset မှအသုံးပြုနိုင်သော CRS အရေအတွက်ကို ပြသပေးပါလိမ့်မည်-

   .. figure:: img/osm_wms_selected.png
      :align: center

   ကျွန်ုပ်တို့မြေပုံအတွက် ``EPSG:4326 - WGS 84`` ကိုအသုံးပြုမည်မဟုတ်သည့်အတွက် အခြားကိုက်ညီမည့် CRS တစ်ခုကို ရှာဖွေကြည့်ပါမည်။

   #. |setProjection|:sup:`Select CRS` ခလုတ်ကိုနှိပ်ပါ။ Data နှင့်အတူပါလာသော CRS များအားလုံးကို ပြသပေးသည့် :guilabel:`Coordinate Reference System Selector` dialog တစ်ခုကိုတွေ့ရပါလိမ့်မည်။
   #. *Projected* CRS တစ်ခုကို လိုချင်သည့်အတွက် ``EPSG:3857`` ဖြင့် :guilabel:`WGS 84 / Pseudo-Mercator` ကိုရွေးချယ်ပါမည်။ အပေါ်ဘက်ရှိ |search| :guilabel:`Filter` widget ကိုလည်း အသုံးပြုနိုင်ပါသည်။

         .. figure:: img/pseudo_mercator_selected.png
            :align: center

      #. :guilabel:`OK` ကိုနှိပ်ပါ။ Coordinate Reference System ပြောင်းသွားပါလိမ့်မည်။

#. :guilabel:`Layer name` (Default သည် :guilabel:`OpenStreetMap WMS - by terrestris` ဖြစ်ပါသည်) ကိုအသုံးပြုပြီး project ထဲသို့ layer ကိုထည့်သွင်းရန် :guilabel:`Add` ကိုနှိပ်ပါ။
#. :guilabel:`Data Source Manager` dialog ကိုပိတ်ပါ။
#. :guilabel:`Layers` panel ထဲတွင် ၎င်း WMS layer ကို အောက်ဆုံးသို့ ဖိဆွဲ၍ရွှေ့ပါ။
#. Layer များကို တစ်ကမ္ဘာလုံးအတိုင်းအတာ မြင်ရနိုင်စေရန် zoom ချုံ့ကြည့်ပါ။ Layer များသည် တည်နေရာမှန်မှန်ကန်ကန် ရှိမနေသည်ကို မြင်ရပါလိမ့်မည် (အာဖရိက၏ အနောက်ဘက် အနား)။ ထိုသို့ဖြစ်ရသည်မှာ "on the fly" projection ကိုပိတ်ထားသောကြောင့်ဖြစ်သည်။

   .. figure:: img/reprojection_off.png
      :align: center
      :width: 100%

#. Projection ထပ်မံ၍ ပြောင်းကြည့်ပါမည်၊ :guilabel:`OpenStreetMap WMS` layer ၏ projection ဖြစ်သော :guilabel:`WGS 84 / Pseudo Mercator` အတိုင်းအတူတူအသုံးပြုပါမည်။

   #. :menuselection:`Project --> Properties... --> CRS` tab ကိုဖွင့်ပါ
   #. :guilabel:`No CRS (or unknown/non-Earth projection)` ကိုအမှန်ခြစ်ဖြုတ်ပါ
   #. စာရင်းထဲမှ :guilabel:`WGS 84 / Pseudo Mercator` ကိုရွေးပါ။

      .. figure:: img/enable_projection.png
         :align: center

   #. :guilabel:`OK` ကိုနှိပ်ပါ။
#. :guilabel:`Layers` panel ထဲရှိ မိမိ၏ကိုယ်ပိုင် layer တစ်ခုပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Zoom to layer(s)` ကိုနှိပ်ပါ။ |majorUrbanName| ဧရိယာကို မြင်တွေ့ရမည်ဖြစ်သည်-

   .. figure:: img/wms_result.png
      :align: center
      :width: 100%

WMS layer ၏ လမ်းများနှင့် မိမိ၏ကိုယ်ပိုင် လမ်း layer သည် ထပ်သွားသည်ကို တွေ့ရပါမည်။

WMS ၏သဘောသဘာဝနှင့် အကန့်အသတ်များ (The nature and limitations of WMS)
...............................................................................

ဤ WMS layer ထဲတွင် feature များစွာ ပါရှိသည်ကို သတိပြုမိပါလိမ့်မည်။ လမ်းများ၊ မြစ်များ၊ သဘာဝကာကွယ်တောများ၊ အစရှိသဖြင့် ပါရှိနေပါသည်။ ၎င်းသည် vector များဖြင့် ဖွဲ့စည်းထားသော်လည်း raster တစ်ခုဖြစ်ပုံရပါသည်၊ သို့သော် ၎င်း၏ သင်္ကေတများကို မပြောင်းလဲနိုင်ပါ။ ဘာကြောင့်ပါလဲ။

ဤအရာသည် WMS တစ်ခု၏ အလုပ်လုပ်ပုံဖြစ်ပါသည်- ၎င်းသည် image တစ်ခုအနေဖြင့်သာ ရရှိသော မြေပုံတစ်ခုဖြစ်ပြီး စာရွက်ပေါ်ရှိ ပုံမှန်မြေပုံတစ်ခုနှင့်ဆင်တူပါသည်။ သင့်တွင် vector layer များရှိသောအခါ QGIS သည် မြေပုံတစ်ခုအဖြစ် ပုံဖော်ပြသပေးပါသည်၊ သို့သော် WMS အသုံးပြုခြင်းတွင် အဆိုပါ vector layer များသည် WMS server ပေါ်တွင် ရှိပြီး ၎င်းတို့ကို မြေပုံတစ်ခုအဖြစ်ပုံဖော်ပြသပြီး ထိုမြေပုံကို သင့်ဆီသို့ image တစ်ခုအနေဖြင့် ပြန်ပို့ပေးခြင်းဖြစ်သည်။ QGIS သည် ထို image ကိုပြသပေးနိုင်သော်လည်း ၎င်း၏ သင်္ကေတများကိုမပြောင်းလဲနိုင်ပါ၊ ထိုသို့ဖြစ်ရခြင်းမှာ အားလုံးကို server ပေါ်တွင် ကိုင်တွယ်လုပ်ဆောင်သောကြောင့်ဖြစ်သည်။

သင်္ကေတနှင့်ပတ်သက်ပြီး စိတ်ပူရန်မလိုအပ်သည့်အတွက် အကျိုးများစွာတော့ရှိပါသည်။ ထိုအတွက် လုပ်ဆောင်ထားပြီးဖြစ်ကာ ကောင်းမွန်စွာဒီဇိုင်းလုပ်ထားသော WMS တစ်ခုခုကို ရှာဖွေကြည့်လျှင်ပိုကောင်းမည်ဖြစ်သည်။

တစ်နည်းအားဖြင့်ဆိုရလျှင် သင့်အနေဖြင့် သင်္ကေတကို မနှစ်သက်လျှင် ပြောင်းလဲ၍မရနိုင်ပါ၊ WMS server ပေါ်တွင် ပြောင်းလဲမှုပြုလုပ်ပါက သင့်မြေပုံတွင်လည်း ပြောင်းလဲသွားမည်ဖြစ်ပါသည်။ ထိုအတွက်ကြောင့် တစ်ခါတရံတွင် WMS အစား  Web Feature Service (WFS) ကိုအသုံးပြုလိုခြင်းဖြစ်သည်၊ WFS သည် WMS-style မြေပုံ၏အစိတ်အပိုင်းအဖြစ်မဟုတ်ပဲ vector layer များကို သီးခြားပေးထားပါသည်။

ထိုအကြောင်းကို နောက်သင်ခန်းစာတွင် လေ့လာရမည်ဖြစ်သည်။ ဦးစွာ နောက်ထပ် WMS layer ကိုထည့်သွင်းကြည့်ပါမည်။


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:)
-------------------------------------------------------------------------------

#. ``https://maps.eatlas.org.au/maps/wms`` URL မှ ``eAtlas`` WMS server ကိုထည့်သွင်းပါ။
#. :guilabel:`World: Hillshading` layer ကိုမြေပုံထဲသို့ ထည့်သွင်းပါ။
#. မြန်ဆန်စေရန်အတွက် :guilabel:`Encoding` တွင် :guilabel:`JPEG` ဟုသတ်မှတ်ပြီး :guilabel:`Tile size` တွင် ``200`` by ``200`` ထားပါ၊ 
#. သင့်မြေပုံသည် အောက်ပါပုံစံအတိုင်းဖြစ်သင့်ပါသည် (layer များကို order ပြန်စီပြီး အလင်းဖောက်နှုန်းအချို့ သုံးပေးရန် လိုအပ်နိုင်ပါသည်)-

      .. figure:: img/world_hillshading_result.png
         :align: center
         :width: 100%

.. admonition:: အဖြေ
   :class: dropdown

   #. Data Source Manager ထဲရှိ WMS / WMTS tab ထဲတွင် ချိတ်ဆက်မှုအသစ်တစ်ခုဖန်တီးပါ။
   #. |search| စာသား box ကိုအသုံးပြုပြီး layer များစာရင်းကို filter လုပ်ကာ သက်ဆိုင်ရာ layer ကိုရွေးချယ်ပါ
   #. ၎င်း၏ CRS ကို မြေပုံ၏အခြား layer များအတိုင်း :guilabel:`EPSG:3857 - WGS 84 / Pseudo Mercator` အဖြစ်ပြောင်းလဲရန် မမေ့ပါနှင့်။

      .. figure:: img/add_world_hillshading_layer.png
         :align: center
         :width: 100%

   #. Layer ကိုထည့်သွင်းပြီးနောက် ၎င်း၏ :guilabel:`Opacity` တန်ဖိုးကို ပြင်ဆင်နိုင်ပါသည် (:guilabel:`Transparency` properties tab အောက်တွင်)

:abbr:`★★★ (Advanced level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:)
-------------------------------------------------------------------------------

WMS အသုံးပြုရခြင်း၏ အခက်အခဲတစ်စိတ်တစ်ပိုင်းသည် ကောင်းမွန်သော (အခမဲ့ဖြစ်သော) server တစ်ခုရှာဖွေရခြင်းဖြစ်သည်။

* `directory.spatineo.com <https://directory.spatineo.com/>`_ (သို့မဟုတ် အွန်လိုင်းတစ်နေရာရာမှ) မှ WMS အသစ်တစ်ခုကို ရှာပါ။ အခကြေးငွေပေးရခြင်း သို့မဟုတ် တားမြစ်ချက်များ မရှိစေရပါ၊ |majorUrbanName| ဧရိယာကို လွှမ်းခြုံရမည်ဖြစ်သည်။

  မှတ်ထားရမည်မှာ WMS တစ်ခုကိုအသုံးပြုရန် ၎င်း၏ URL သာလိုအပ်ပါသည် (လိုအပ်လျှင် ဖော်ပြချက်အချို့ ထည့်ပေးနိုင်ပါသည်)။

.. admonition:: အဖြေ
   :class: dropdown

   Spatineo သည် OGC data ရှာဖွေပေးနိုင်သော နေရာများထဲမှ တစ်ခုဖြစ်ပါသည်။ ရလာဒ်များရမရ ကြည့်ရှုရန် စာသားဧရိယာထဲတွင် အမည်၊ Keyword၊ စိတ်ဝင်စားသည့်တည်နေရာ ရိုက်ထည့်ကြည့်ပါ။ ဤသင်ခန်းစာအတွက် WMS သာပါဝင်သော ရလာဒ်များကိုသာ filter လုပ်လိုပါသည်။

   WMS server များစွာသည် အမြဲတမ်းအသုံးမပြုနိုင်သည်ကို သတိထားမိပါလိမ့်မည်။ တစ်ခါတရံတွင် ယာယီသာဖြစ်ပြီး တစ်ခါတရံတွင် အမြဲတမ်းဖြစ်ပါသည်။ မှတ်တမ်းရေးသားနေချိန်တွင် အလုပ်လုပ်နေသော WMS server ဥပမာတစ်ခုပြောရလျှင် :guilabel:`MapServer Demonstration Server` WMS ဖြစ်ပြီး https://demo.mapserver.org/cgi-bin/wms?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities URL တွင်ရှိပါသည်။ ၎င်းသည် အခကြေးငွေပေးရန်မလိုအပ်သလို သုံးစွဲခွင့်ကန့်သတ်ချက်များလည်း မရှိပါ၊ တစ်ကမ္ဘာလုံးအတွက် အသုံးပြုနိုင်ပါသည်။ ထို့ကြောင့် ၎င်းသည် လိုအပ်ချက်များနှင့်ကိုက်ညီပြီး သုံးစွဲရ အဆင်ပြေပါသည်။ စိတ်ထဲမှတ်သားထားရမည်မှာ ၎င်း WMS သည် ဥပမာတစ်ခုသာဖြစ်ပြီး အခြားရွေးချယ်နိုင်သည့် WMS server များစွာရှိပါသေးသည်။


:abbr:`★★★ (Advanced level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:)
-------------------------------------------------------------------------------

* :guilabel:`MapServer Demonstration Server` မှ :guilabel:`bluemarble` layer ကိုထည့်သွင်းပါ။ ၎င်းသည် ကျွန်ုပ်တို့ study area အတွက် သင့်လျော်သော dataset တစ်ခုဖြစ်ပါသလား?

.. admonition:: အဖြေ
   :class: dropdown

   #. ပုံဖော်ပြသရန်မလိုအပ်သော အခြား WMS layer များအားလုံးကို ဖျောက်ထားပါ။
   #. အထက်တွင်ပြသထားသည့်နည်းအတိုင်း server အသစ်ကိုထည့်သွင်းပြီး ထို server ၌ရှိသော သင့်လျော်သော layer ကိုထည့်သွင်းပါ-

      .. figure:: img/add_bluemarble_layer.png
         :align: center

   #. |majorUrbanName| ဧရိယာသို့ zomm ချဲ့ကြည့်လျှင် ဤ dataset သည် resolution နိမ့်နေသည်ကို သင်သတိထားမိပါလိမ့်မည်-

      .. figure:: img/low_resolution_dataset.png
         :align: center

      ထို့ကြောင့် ဤ data ကို လက်ရှိမြေပုံအတွက် အသုံးမပြုလျှင်ပိုကောင်းပါသည်။ Blue Marble data သည် ကမ္ဘာအဆင့် စကေးများနှင့် နိုင်ငံအဆင့် စကေးများတွင်သာ ပိုမိုသင့်တော်ပါသည်။


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

WMS တစ်ခုကိုအသုံးပြုခြင်းဖြင့် သင့် လက်ရှိမြေပုံ data အတွက် နောက်ခံအနေဖြင့် ပြောင်းလဲမှုမရှိသောမြေပုံများ ထည့်သွင်းနိုင်မည်ဖြစ်ပါသည်။

နောက်ထပ်ဖတ်ရှုရမည်များ (Further Reading)
-------------------------------------------------------------------------------

* `Spatineo Directory <https://directory.spatineo.com/>`_
* `OpenStreetMap.org list of WMS servers
  <https://wiki.openstreetmap.org/wiki/WMS>`_

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ယခုဆိုလျှင် နောက်ခံအနေဖြင့် ပြောင်းလဲမှုမရှိသောမြေပုံတစ်ခုထည့်သွင်းပြီးဖြစ်ပါသည်၊ feature များကိုလည်း ထည့်သွင်းနိုင်ပါသေးသည် (အခြား vector layer များထည့်သွင်းသကဲ့သို့)။ Web Feature Service (WFS) တစ်ခုအသုံးပြုပြီး Remote server များမှ feature များထည့်သွင်းနိုင်ပါသည်။ ထိုအကြောင်းကို နောက်လာမည့် သင်ခန်းစာတွင် သင်ကြားပေးမည်ဖြစ်ပါသည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addWmsLayer| image:: /static/common/mActionAddWmsLayer.png
   :width: 1.5em
.. |dataSourceManager| image:: /static/common/mActionDataSourceManager.png
   :width: 1.5em
.. |majorUrbanName| replace:: Swellendam
.. |search| image:: /static/common/search.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
