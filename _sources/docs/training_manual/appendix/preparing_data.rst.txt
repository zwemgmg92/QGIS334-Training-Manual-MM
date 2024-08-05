.. _tm_preparing_data:

လေ့ကျင့်ခန်းအတွက် Data များပြင်ဆင်ခြင်း (Preparing Exercise Data)
==================================================================

.. important:: ဤလုပ်ငန်းစဉ်ကို သင်တန်းအတွက် နမူနာ dataset များဖန်တီးလိုသော သင်တန်းအကြီးအမှူးများ၊ သို့မဟုတ် အတွေ့အကြုံပိုများသော QGIS အသုံးပြုသူများအတွက် ရည်ရွယ်ပါသည်။ Default dataset များသည် Training Manual နှင့်အတူပါရှိပါသည်၊ သို့သော် default dataset များအစား အခြား dataset များကိုအသုံးပြုလိုပါက ဤလမ်းညွှန်ချက်များအတိုင်း လိုက်နာလုပ်ဆောင်နိုင်ပါသည်။

Training Manual နှင့်အတူပါရှိသော :ref:`နမူနာ data <data_downloadlink>` သည် |majorUrbanName| မြို့နှင့် ပတ်ဝန်းကျင်နေရာများအတွက်ဖြစ်ပါသည်။ |majorUrbanName| သည် တောင်အာဖရိက၏ Western Cape ထဲရှိ Cape Town မှ ၂ နာရီခန့်သွားရသော နေရာတွင် တည်ရှိပါသည်။ Dataset ထဲတွင်ပါရှိသော feature နာမည်များသည် အင်္ဂလိပ် နှင့် အာဖရီကန်ဘာသာစကား နှစ်မျိုးလုံးဖြင့် ပါရှိပါသည်။

ဤ dataset ကို လူတိုင်း အလွယ်တကူအသုံးပြုနိုင်ပါသည်၊ သို့သော် သင့်နိုင်ငံ သို့မဟုတ် သင့်မြို့မှ data ကိုအသုံးပြုလိုပါက မော်ဂျူး ၃ မှ မော်ဂျူး ၇.၂ အထိ သင်ခန်းစာများအားလုံးအတွက် သင့်ကိုယ်ပိုင် data များကို အသုံးပြုနိုင်ပါလိမ့်သည်။ နောက်ပိုင်း မော်ဂျူးများတွင် အသုံးပြုထားသော data များသည် ပိုမိုရှုပ်ထွေးသော data ရင်းမြစ်များဖြစ်ပြီး သင့်ဒေသအတွက် ရှိနိုင်မှ ရှိနိုင်ပါလိမ့်မည်။

.. note:: ဤညွှန်ကြားချက်များသည် သင့်တွင် QGIS ဗဟုသုတကောင်းကောင်းရှိသည်ဟု ယူဆထားပြီး ၎င်းတို့ကို သင်ထောက်ကူအနေဖြင့် အသုံးပြုရန် မရည်ရွယ်ထားပါ။

Vector ဖိုင်များပေါ်အခြေခံသော OSM ဖန်တီးခြင်း (Create OSM based vector files)
--------------------------------------------------------------------------------

Default dataset ကို သင့်ကိုယ်ပိုင် data ဖြင့်အစားထိုးအသုံးပြုလိုပါက QGIS တွင်ပါရှိသော tool များဖြင့် အလွယ်တကူလုပ်ဆောင်နိုင်ပါသည်။ အသုံးပြုရန် သင်ရွေးချယ်ထားသောဒေသတွင် မြို့ပြနှင့် ကျေးလက်ဧရိယာများရောနှောပါဝင်နေသင့်ပြီး အမျိုးအစားကွဲပြားသောလမ်းများ၊ ဧရိယာနယ်နိမိတ်များ (သဘာဝကာကွယ်တောများ သို့မဟုတ် စိုက်ပျိုးမြေများကဲ့သို့) နှင့် မြစ်ချောင်းများကဲ့သို့ ရေမျက်နှာပြင် များပါဝင်သင့်ပါသည်။ 

#. QGIS project အသစ်တစ်ခုကို ဖွင့်ပါ။
#. :menuselection:`Layer --> Data Source Manager` ကိုရွေးပါ၊ :guilabel:`Data Source Manager` dialog ပွင့်လာပါမည်။
#. :guilabel:`Browser` tab ထဲတွင် :guilabel:`XYZ Tiles` ကိုအကျယ်ဖြန့်ပြီး :guilabel:`OpenStreetMap` item ကို click နှစ်ချက်နှိပ်ပါ။

   .. figure:: img/browser_xyztiles.png
      :align: center
      :scale: 60

   ကမ္ဘာ့မြေပုံတစ်ခုကို မြေပုံ canvas ပေါ်တွင် မြင်ရမည်ဖြစ်သည်။
#. :guilabel:`Data Source Manager` dialog ကိုပိတ်လိုက်ပါ။
#. Study area အဖြစ် အသုံးပြုလိုသော ဧရိယာသို့ နေရာရွှေ့ပါ။

   .. figure:: img/swellendam_neighborhood.png
      :align: center
      :scale: 60

ယခုအခါ data ထုတ်ယူလိုသော ဧရိယာကို ရရှိပြီဖြစ်ပါသည်၊ data ထုတ်ယူခြင်း tool များကို ဖွင့်ပေးပါမည်။

#. :menuselection:`Plugins --> Manage/Install Plugins...` သို့သွားပါ
#. :guilabel:`All` tab ထဲရှိ search box တွင် ``QuickOSM`` ဟုရိုက်ထည့်ပါ
#. QuickOSM plugin ကိုရွေးချယ်ပါ၊ :guilabel:`Install Plugin` ကိုနှိပ်ပါ၊ ထို့နောက်တွင် dialog ကိုပိတ်ရန် :guilabel:`Close` ကိုနှိပ်ပါ။ 

   .. figure:: img/quickosm_plugin_download.png
      :align: center

#. :menuselection:`Vector --> QuickOSM --> QuickOSM...` menu မှ plugin အသစ်ကို ဖွင့်ပါ
#. :guilabel:`Quick query` tab ထဲရှိ  :guilabel:`Key` drop-down menu ထဲတွင် ``building`` ကိုရွေးချယ်ပါ
#. :guilabel:`Value` field ကို အလွတ်အတိုင်းထားရှိပါ၊ building များအားလုံးကို query လုပ်မည်ဟု ဆိုလိုပါသည်။
#. အောက်ရှိ drop-down menu ထဲတွင် :guilabel:`Canvas Extent` ကိုရွေးချယ်ပါ
#. :guilabel:`Advanced` အုပ်စုကို ဖြန့်ကြည့်ပြီး ညာဘက်ရှိ ဂျီဩမေတြီအမျိုးအစားများထဲတွင် :guilabel:`Multipolygons` မှလွဲ၍ ကျန်အမျိုးအစားများကို အမှန်ခြစ်ဖြုတ်ပါ။
#. :guilabel:`Run query` ကိုနှိပ်ပါ

   .. figure:: img/building_query_builder.png
      :align: center

   :guilabel:`Layers` panel ထဲတွင် ``building`` layer အသစ်တစ်ခုကို ထည့်သွင်းပေးမည်ဖြစ်ပြီး ရွေးချယ်ထားသော extent အတွင်းရှိ building များအားလုံးကို ပြသပေးမည်ဖြစ်ပါသည်။
#. အခြားသော data များကိုထုတ်ယူရန် အထက်ဖော်ပြပါအတိုင်း လုပ်ဆောင်ပါ-

   #. ``Key = landuse`` နှင့် ``Multipolygons`` ဂျီဩမေတြီအမျိုးအစား
   #. ``Key = boundary`` ၊ ``Value = protected_area`` နှင့် ``Multipolygons``
      ဂျီဩမေတြီအမျိုးအစား
   #. ``Key = natural`` ၊ ``Value = water`` နှင့် ``Multipolygons`` ဂျီဩမေတြီအမျိုးအစား
   #. ``Key = highway`` နှင့် ``Lines`` နှင့် ``Multilines`` ဂျီဩမေတြီအမျိုးအစားကို အမှန်ခြစ်ပါ
   #. ``Key = waterway`` ၊ ``Value = river`` နှင့် ``Lines`` နှင့် ``Multilines``
      ဂျီဩမေတြီအမျိုးအစားကို အမှန်ခြစ်ပါ
   #. ``Key = place`` နှင့် ``Points`` ဂျီဩမေတြီအမျိုးအစား

ဤလုပ်ငန်းစဉ်သည် layer များကို ယာယီဖိုင်များအဖြစ် ထည့်သွင်းပေးပါသည် (layer နာမည်များဘေးတွင် |indicatorMemory| icon ဖြင့် ဖော်ပြထားပါသည်)။

.. figure:: img/osm_data_loaded.png
   :align: center

သင့်ဒေသသည် မည်သို့သော ရလာဒ်အမျိုးအစားများ ထုတ်ပေးမည်ကို ကြည့်ရှုနိုင်ရန် သင့်ဒေသတွင်ပါရှိသော data များကို နမူနာယူနိုင်ပါသည်။

ရလာဒ် data များကို သင်၏သင်တန်းအတွင်း အသုံးပြုနိုင်ရန်အတွက် သိမ်းဆည်းထားရန်လိုအပ်ပါသည်။ Data ပေါ်မူတည်၍ ESRI Shapefile ၊ GeoPackage နှင့် SpatiaLite format များကို အသုံးပြုပါမည်။

:guilabel:`place` ယာယီ layer ကို အခြား format သို့ ပြောင်းလဲရန်-

#. :guilabel:`place` layer ၏ဘေးရှိ |indicatorMemory| icon ကိုနှိပ်ပါ၊ :guilabel:`Save Scratch Layer` dialog ပွင့်လာပါမည်။

   .. note:: ယာယီ layer တစ်ခုခု၏ ဂုဏ်သတ္တိများ (CRS ၊ extent ၊ field အစရှိသည်တို့) ကိုပြောင်းလဲရန် လိုအပ်ပါက :menuselection:`Export
     --> Save Features as...` ကိုအသုံးပြုပြီး :guilabel:`Add
     saved file to map` option ကိုအမှန်ခြစ်ထားပါ။ ထိုသို့လုပ်ခြင်းဖြင့် Layer အသစ်တစ်ခုကို ထည့်သွင်းပေးပါသည်။

#. :guilabel:`ESRI Shapefile` format ကိုရွေးချယ်ပါ
#. :guilabel:`...` ခလုတ်ကိုနှိပ်ပြီး :file:`exercise_data/shapefile/` folder ကိုဖွင့်ကာ ဖိုင်ကို :file:`places.shp` အနေဖြင့် သိမ်းဆည်းပါ။

   .. figure:: img/save_osm_place.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ

   :guilabel:`Layers` panel ထဲတွင် ယာယီ :guilabel:`place` layer ကို သိမ်းဆည်းထားသော :guilabel:`places` shapefile layer ဖြင့် အစားထိုးပေးမည်ဖြစ်ပြီး ယာယီ icon ကိုဖယ်ရှားပေးမည်ဖြစ်သည်။
#. Layer ကို click နှစ်ချက်နှိပ်ပြီး :menuselection:`Layer Properties -->
   Source` tab ကိုဖွင့်ပြီး :guilabel:`Layer name` property ကို ဖိုင်နာမည်နှင့် ကိုက်ညီစေရန် update လုပ်ပါ။

#. အခြားသော layer များအတွက် ထိုအတိုင်းလုပ်ဆောင်ပြီး ၎င်းတို့ကို အောက်ပါအတိုင်း နာမည်ပြောင်းပေးပါ-

   * ``natural_water`` ကို ``water`` သို့
   * ``waterway_river`` ကို ``rivers`` သို့
   * ``boundary_protected_area`` ကို ``protected_areas`` သို့

   ရလာဒ် dataset တစ်ခုချင်းစီကို :file:`exercise_data/shapefile/` ဖိုင်လမ်းကြောင်းထဲတွင် သိမ်းဆည်းထားသင့်ပါသည်။

နောက်တစ်ဆင့်အနေဖြင့် သင်တန်းအတွင်းအသုံးပြုရန် :guilabel:`building` layer မှ GeoPackage ဖိုင်တစ်ခုဖန်တီးရန် ဖြစ်ပါသည်-

#. :guilabel:`building` layer ၏ဘေးရှိ |indicatorMemory| icon ကိုနှိပ်ပါ
#. :guilabel:`GeoPackage` format ကိုရွေးချယ်ပါ
#. ဖိုင်ကို :file:`exercise_data/` folder အောက်တွင် :file:`training_data.gpkg` အနေဖြင့် သိမ်းဆည်းပါ
#. Default အားဖြင့် :guilabel:`Layer name` ကို ဖိုင်နာမည်အတိုင်း ဖြည့်ပေးပါသည်။ ၎င်း :guilabel:`Layer name` ကို ``buildings`` ဟုပြောင်းပါ။

   .. figure:: img/save_osm_building.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ
#. Layer ၏ property dialog ထဲတွင် layer ကို နာမည်ပြောင်းပါ
#. :guilabel:`highway` layer တွင်လည်း ထိုလုပ်ငန်းစဉ်အတိုင်းလုပ်ဆောင်ပြီး တူညီသော GeoPackage database ထဲတွင် ``roads`` အနေဖြင့် သိမ်းဆည်းပါ။

နောက်ဆုံးအဆင့်အနေဖြင့် ကျန်ရှိနေသော ယာယီဖိုင်ကို SpatiaLite ဖိုင်အဖြစ် သိမ်းဆည်းရန်ဖြစ်ပါသည်။

#. :guilabel:`landuse` layer ၏ဘေးရှိ |indicatorMemory| icon ကိုနှိပ်ပါ
#. :guilabel:`SpatiaLite` format ကိုရွေးချယ်ပါ
#. ဖိုင်ကို :file:`exercise_data/` folder အောက်တွင် :file:`landuse.sqlite` အဖြစ် သိမ်းဆည်းပါ။ Default အားဖြင့် :guilabel:`Layer name` ကို ဖိုင်နာမည်အတိုင်း ဖြည့်ပေးပါသည်။ ၎င်းကို မပြောင်းလဲပါနှင့်။

   .. figure:: img/save_osm_landuse.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ။

ယခုအခါ အောက်ပါပုံစံအတိုင်း မြေပုံတစ်ခုကို ရရှိသင့်ပါသည် (Layer များကို မြေပုံထဲသို့ထည့်သွင်းသောအခါ QGIS သည် အရောင်များကျပန်းသတ်မှတ်သောကြောင့် သင်္ကေတသည် ကွဲပြားပါလိမ့်မည်)-

.. figure:: img/post_osm_import.png
   :align: center

အထက်တွင်ပြထားသော အဆိုပါ layer ၇ ခုရရှိမည်ဖြစ်ပြီး ထို layer များအားလုံးတွင် data အချို့ရှိရန် အရေးကြီပါသည်။

SRTM DEM tiff ဖိုင်များဖန်တီးခြင်း (Create SRTM DEM tiff files)
--------------------------------------------------------------------------------

:ref:`tm_create_vector_data` နှင့်  :ref:`tm_rasters` မော်ဂျူးများအတွက် သင်ရွေးချယ်ထားသောဒေသကို လွှမ်းခြုံသည့် raster image (SRTM DEM) ကိုလည်း လိုအပ်ပါလိမ့်မည်။

`CGIAR-CGI <https://srtm.csi.cgiar.org/>`_ သည် SRTM DEM အချို့ကို ထောက်ပံ့ပေးထားပြီး https://srtm.csi.cgiar.org/srtmdata/ မှ ဒေါင်းလုဒ်ပြုလုပ်နိုင်ပါသည်။


သင်ရွေးချယ်ထားသော ဒေသတစ်ခုလုံးကို လွှမ်းခြုံသော image များလိုအပ်ပါသည်။ Extent ကိုဩဒိနိတ်များကိုရှာဖွေရန်  QGIS ထဲတွင် အကြီးဆုံး layer ၏ extent ကို |zoomToLayer| zoom ပြုလုပ်ပြီး status bar ၏ |extents| :guilabel:`Extents` အကွက်ထဲရှိ တန်ဖိုးများကို ရယူပါ။ :file:`GeoTiff` format ဖြင့်ထားပါ။ Form ကိုဖြည့်သွင်းပြီးသည်နှင့် :guilabel:`Click here to Begin Search >>` ခလုတ်ကိုနှိပ်ပြီး ဖိုင်(များ)ကို ဒေါင်းလုပ်ပြုလုပ်ပါ။

လိုအပ်သောဖိုင်(များ)ကို ဒေါင်းလုဒ်ပြုလုပ်ပြီးသည်နှင့် ဖိုင်များကို :file:`exercise_data` ဖိုင်လမ်းကြောင်းထဲရှိ :file:`raster/SRTM` folder အခွဲအောက်တွင် သိမ်းဆည်းသင့်ပါသည်။

Imagery tiff ဖိုင်များဖန်တီးခြင်း (Create imagery tiff files)
--------------------------------------------------------------------------------


:ref:`tm_create_vector_data` မော်ဂျူးထဲတွင် :ref:`tm_datasources` သင်ခန်းစာသည် ကျောင်းသားများကို digitize ပြုလုပ်ခိုင်းသော ကျောင်းအားကစားကွင်း ၃ ခု၏ အနီးကပ် image များကို ပြသပါသည်။ ထို့ကြောင့် သင်၏ SRTM DEM tiff ဖိုင်(များ) ကိုအသုံးပြုပြီး အဆိုပါ image များကို ပြန်လည်ထုတ်ယူရန် လိုအပ်ပါလိမ့်မည်။ ကျောင်းအားကစားကွင်းများကိုသာ အသုံးပြုရမည်ဟု မကန့်သတ်ထားပါ- မည်သည့် ကျောင်း land-use အမျိုးအစားများ (ဥပမာ- မတူညီသော ကျောင်းအဆောက်အဦများ၊ ကစားကွင်းများ သို့မဟုတ် ကားပါကင်များ) ၃ ခုကိုမဆို အသုံးပြုနိုင်ပါသည်။

အကိုးအကားပြုရန်အတွက် ဥပမာ data ထဲရှိ image သည်-

.. figure:: img/field_outlines.png
   :align: center


တိုကင်များ အစားထိုးလဲလှယ်ခြင်း (Replace tokens)
--------------------------------------------------------------------------------

သင့်ဒေသအတွက် dataset ကိုဖန်တီးပြီးပါက နောက်ဆုံးအဆင့်အနေဖြင့် :file:`substitutions.txt` ဖိုင်ထဲတွင် တိုကင်များကို အစားထိုးလဲလှယ်ရန်ဖြစ်ပါသည်၊ သို့မှသာ သင့်ကိုယ်ပိုင် Training Manual ဗားရှင်းတွင် သင့်လျော်သောနာမည်များ ပေါ်နေပါလိမ့်မည်။

အစားထိုးလဲလှယ်ရန် လိုအပ်သည့် တိုကင်များမှာ အောက်ပါအတိုင်းဖြစ်သည်-

* ``majorUrbanName`` - Default အားဖြင့် "Swellendam" မြို့ ဖြစ်ပါသည်။ ၎င်းကို သင့်ဒေသရှိ အဓိကမြို့နာမည်ဖြင့် အစားထိုးလဲလှယ်ပါ။
* ``schoolAreaType1`` - Default အားဖြင့် "athletics field" ဖြစ်ပါသည်။ ၎င်းးကို သင့်ဒေသရှိ အကြီးဆုံးကျောင်းဧရိယာအမျိုးအစား၏နာမည်ဖြင့် အစားထိုးလဲလှယ်ပါ။
* ``largeLandUseArea`` - Default အားဖြင့် "Bontebok National Park" ဖြစ်ပါသည်။ ၎င်းကို သင့်ဒေသရှိ ကြီးမားသော landuse polygon တစ်ခု၏နာမည်ဖြင့် အစားထိုးလဲလှယ်ပါ။
* ``srtmFileName`` - Default အားဖြင့် :file:`srtm_41_19.tif` ဖိုင်ဖြစ်ပါသည်။ ၎င်းကို သင်၏ SRTM DEM ဖိုင်နာမည်ဖြင့် အစားထိုးလဲလှယ်ပါ။
* ``localCRS`` - Default အားဖြင့် ``WGS 84 / UTM 34S`` CRS ဖြစ်ပါသည်။ ၎င်းကို သင့်ဒေသအတွက် မှန်ကန်သော CRS ဖြင့် အစားထိုးလဲလှယ်သင့်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |extents| image:: /static/common/extents.png
   :width: 1.5em
.. |indicatorMemory| image:: /static/common/mIndicatorMemory.png
   :width: 1.5em
.. |majorUrbanName| replace:: Swellendam
.. |zoomToLayer| image:: /static/common/mActionZoomToLayer.png
   :width: 1.5em
