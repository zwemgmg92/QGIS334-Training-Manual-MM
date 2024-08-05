သင်ခန်းစာ - GRASS Setup (Lesson: GRASS Setup)
===============================================================================

QGIS ထဲတွင် GRASS အသုံးပြုသောအခါ interface သည် အနည်းငယ်ကွဲပြားနေပါလိမ့်မည်။ QGIS ထဲတွင်တိုက်ရိုက်အလုပ်လုပ်နေခြင်းမဟုတ်ပဲ QGIS *မှတဆင့်* GRASS ထဲတွင် အလုပ်လုပ်နေခြင်းဖြစ်သည်ကို မှတ်သားထားပါ။ ထို့ကြောင့် GRASS အသုံးပြုနိုင်သော QGIS Desktop ကို install ပြုလုပ်ထားပါ။

|win| Window တွင် GRASS ဖြင့် QGIS ကိုဖွင့်ရန် ``QGIS Desktop with GRASS`` icon ကိုနှိပ်ပါ။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** QGIS ထဲတွင် GRASS project တစ်ခုအစပြုရန်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS Session အသစ်တစ်ခုစတင်ခြင်း (Follow Along: Start a New GRASS Session)
------------------------------------------------------------------------------------------------------------------------

QGIS အတွင်းမှ GRASS ကိုစတင်အသုံးပြုရန် အခြား plugin များကဲ့သို့ activate လုပ်ပေးရန်လိုအပ်ပါသည်-

#. ဦးစွာ QGIS project အသစ်တစ်ခုကိုဖွင့်ပါ။
#. :guilabel:`Plugin Manager` ထဲတွင် :guilabel:`GRASS` ကိုဖွင့်ပေးပါ-

   .. figure:: img/enable_grass.png
      :align: center


   GRASS toolbar နှင့် GRASS panel ပေါ်လာပါလိမ့်မည်-

   .. figure:: img/grass_toolbar.png
      :align: center

      GRASS toolbar

   .. figure:: img/grass_panel.png
      :align: center

      GRASS Panel

GRASS ကိုအသုံးမပြုမီတွင် ``Mapset`` တစ်ခုကိုဖန်တီးထားရန် လိုအပ်ပါသည်။ GRASS သည် database environment တစ်ခုထဲတွင် အလုပ်လုပ်ဆောင်ခြင်းဖြစ်ပြီး သင်အသုံးပြုလိုသည့် data များအားလုံးကို GRASS database တစ်ခုထဲသို့ ထည့်သွင်းထားရန်လိုအပ်ပါသည်။

GRASS database တစ်ခုကို စစချင်းကြည့်ပါက အလွန်ရှုပ်ထွေးသည်ဟုထင်ရသော်လည်း ၎င်း၏ ဖွဲ့စည်းပုံသည် ရိုးရှင်းပါသည်။ သင်သိထားရမည့် အရေးအကြီးဆုံးအရာသည် database ၏ ထိပ်ပိုင်းအဆင့်သည် ``Location`` ဖြစ်ပါသည်။ ``Location`` တစ်ခုချင်းစီတွင် မတူညီသော ``Mapset`` များပါဝင်နိုင်ပါသည်၊ ``Mapset`` တိုင်းတွင် ``PERMANENT`` Mapset ကိုတွေ့ရမည်ဖြစ်ပြီး ၎င်းကို GRASS မှ default အနေဖြင့် ဖန်တီးပေးထားခြင်းဖြစ်သည်။ ``Mapset`` တစ်ခုချင်းစီတွင် သီးခြားဖွဲ့စည်းပုံဖြင့် data (raster ၊ vector အစရှိသဖြင့်) များပါဝင်ပြီး GRASS မှ ၎င်း data များကို ကိုင်တွယ်မည်ဖြစ်သည်။

မှတ်သားထားရမည်မှာ ``Location`` တွင် data များပါရှိသော ``Mapset`` ပါဝင်ပါသည်။ နောက်ထပ်အချက်အလက်များအတွက် `GRASS website <https://grass.osgeo.org/grass82/manuals/grass_database.html>`_ တွင်ကြည့်ရှုပါ။

.. figure:: img/grass_database.png
   :align: center

   GRASS database ဖွဲ့စည်းပုံ (GRASS docs မှ)

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS Project အသစ်တစ်ခုစတင်ခြင်း (Follow Along: Start a New GRASS Project)
------------------------------------------------------------------------------------------------------------------------

#. :menuselection:`Plugins --> GRASS --> New Mapset` menu ကိုနှိပ်ပါ-

   .. figure:: img/grass_menu.png
      :align: center

   GRASS database ၏ တည်နေရာကိုရွေးချယ်ပေးရန် မေးမြန်းပါလိမ့်မည်။

#. GRASS မှ ၎င်း၏ database ကို set up ပြုလုပ်ရာတွင် အသုံးပြုမည့် ဖိုင်လမ်းကြောင်းအနေဖြင့် သတ်မှတ်ပါ-

   .. figure:: img/grass_folder.png
      :align: center

#. :guilabel:`Next` ကိုနှိပ်ပါ။

GRASS သည် ``Location`` တစ်ခုကိုဖန်တီးရန်လိုအပ်ပါသည်၊ ၎င်း ``Location`` သည် အလုပ်လုပ်ဆောင်မည့် ပထဝီဝင်ဧရိယာ၏ အများဆုံးနယ်ပယ်အကျယ်အဝန်းကို ဖော်ပြပေးပြီး  Grass ``Region`` ဟုလည်း‌ ခေါ်ဆိုပါသည်။

.. note:: Region သည် GRASS အတွက် အလွန်အရေးကြီးပါသည်၊ အကြောင်းမှာ Region သည် ဧရိယာကိုဖော်ပြပေးပြီး ထိုဧရိယာထဲတွင် layer များအားလုံးကို GRASS အတွက်ထည့်သွင်းစဉ်းစားပေးမည်ဖြစ်သည်။ အပြင်ဘက်တွင်ရှိသော အရာများအားလုံးကို ထည့်သွင်းစဉ်းစားမည်မဟုတ်ပါ။ Location ကိုဖန်တီးပြီးနောက် GRASS Region ၏ နယ်ပယ်အကျယ်အဝန်းကို ပြောင်းလဲပေးနိုင်ပါသည်။

#. Location အသစ် ``SouthAfrica`` ကိုခေါ်ပါ- 

   .. figure:: img/new_location.png
      :align: center

#. :guilabel:`Next` ကိုနှိပ်ပါ။
#. ``WGS 84`` ကိုအသုံးပြုမည်ဖြစ်သော်ကြောင့် ထို CRS ကိုရှာပြီး ရွေးချယ်ပေးပါ-

   .. figure:: img/wgs_84_selected.png
      :align: center

#. :guilabel:`Next` ကိုနှိပ်ပါ။
#. Dropdown မှ :guilabel:`South Africa` region ကိုရွေးချယ်ပေးပြီး :guilabel:`Set` ကိုနှိပ်ပါ-

   .. figure:: img/set_south_africa.png
      :align: center

#. :guilabel:`Next` ကိုနှိပ်ပါ။
#. Mapset တစ်ခုကိုဖန်တီးပါ၊ ၎င်းသည် အလုပ်လုပ်ဆောင်ရမည့် map ဖိုင်ဖြစ်ပါသည်။

   .. figure:: img/grass_mapset.png
      :align: center

   ဖန်တီးပြီးသွားသောအခါ ထည့်သွင်းထားသည့် အချက်အလက်များအားလုံး၏အကျဉ်းချုပ်ပါဝင်သော မေးမြန်းသည့် dialog တစ်ခုကိုတွေ့ရပါလိမ့်မည်။

   .. figure:: img/grass_final.png
     :align: center

#. :guilabel:`Finish` ကိုနှိပ်ပါ။
#. Success dialog ပေါ်လာလျှင် :guilabel:`OK` ကိုနှိပ်ပါ။

GRASS Panel သည် active ဖြစ်လာသည်ကို မြင်တွေ့ရမည်ဖြစ်ပြီး GRASS tool များအားလုံးကို အသုံးပြုနိုင်ပြီဖြစ်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS ထဲသို့ Vector Data များထည့်သွင်းခြင်း (Follow Along: Loading Vector Data into GRASS)
----------------------------------------------------------------------------------------------------------------------------------------

ယခုဆိုလျှင် မြေပုံအလွတ်တစ်ခုရှိနေမည်ဖြစ်ပြီး GRASS tool များအားလုံးကို အသုံးမပြုမီတွင် GRASS database ထဲသို့ data များ ထည့်သွင်းရမည်ဖြစ်သည်၊ အထူးသဖြင့် ``Mapset`` ထဲသို့ထည့်သွင်းရမည်ဖြစ်သည်။ GRASS ``Mapset`` တစ်ခုထဲသို့ မထည့်သွင်းထားသော layer များကို GRASS tool များဖြင့် အသုံးပြုနိုင်မည်မဟုတ်ပါ။ 

GRASS database ထဲသို့ data များထည့်သွင်းရန် နည်းလမ်းအမျိုးမျိုးရှိပါသည်။ ပထမဦးဆုံး တစ်ခုဖြင့် စတင်လုပ်ဆောင်ကြည့်ပါမည်။


.. _grass_browser:

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - QGIS Browser အသုံးပြု၍ Data များထည့်သွင်းခြင်း (Follow Along: Load data using the QGIS Browser)
.............................................................................................................................................

QGIS ထဲသို့ data များထည့်သွင်းရန် အလွယ်ကူဆုံးနှင့်အမြန်ဆုံးနည်းလမ်းသည် Browser Panel ဖြစ်သည်ကို :ref:`browser_panel_tm` အပိုင်းတွင် တွေ့မြင်ခဲ့ပြီးဖြစ်ပါသည်။ 

GRASS data များကို *real* GRASS data များအနေဖြင့် QGIS Browser မှ အသိအမှတ်ပြုပါသည်၊ GRASS Mapset ဘေးတွင် GRASS icon ကိုမြင်တွေ့နေရမည်ဖြစ်သည်။ ထို့အပြင် ဖွင့်ထားသော Mapset ဘေးတွင် |grassMapsetOpen| icon ကို မြင်တွေ့ရမည်ဖြစ်သည်။

.. figure:: img/grass_browser.png
   :align: center

.. note:: GRASS Location အပွားတစ်ခုကို သာမန် folder အနေဖြင့် မြင်တွေ့ရမည်ဖြစ်သည်- GRASS ``Mapset`` data များသည် |grassLogo| folder ထဲတွင် ရှိသော data များဖြစ်ပါသည်။

Folder တစ်ခုထဲမှ layer များကို click နှိပ်ဖိဆွဲကာ GRASS Mapset ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။

``SouthAfrica`` Location ၏ ``grass_mapset`` Mapset ထဲသို့ :file:`roads` layer ကိုထည့်သွင်းကြည့်ပါမည်။

Browser သို့သွားပြီး :file:`training_data.gpkg` GeoPackage ဖိုင်မှ :file:`roads` layer ကို ဖိဆွဲကာ ``grass_mapset`` Mapset ထဲသို့ ထည့်သွင်းပါ။

.. figure:: img/grass_browser_import.png
   :align: center

Mapset ကိုဖြန့်ကြည့်ပါက ထည့်သွင်းထားသော :file:`roads` layer ကိုမြင်တွေ့ရပါမည်။ ထိုထည့်သွင်းထားသော layer ကို QGIS ထဲသို့ အခြား layer များကဲ့သို့ပင် ထည့်သွင်းနိုင်ပါသည်။ 

.. tip:: Layer Legend Panel မှ layer များကို Browser Panel ထဲရှိ Mapset ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။ ထိုသို့လုပ်ဆောင်ခြင်းဖြင့် အလုပ်လုပ်ရာတွင် မြန်ဆန်စေပါလိမ့်မည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS Panel အသုံးပြု၍ Data ထည့်သွင်းခြင်း (Follow Along: Load data using the GRASS Panel)
.......................................................................................................................................

:file:`rivers.shp` layer ကို ထိုတူညီသော Mapset ထဲသို့ထည့်သွင်းရန် *long* နည်းလမ်းကို အသုံးပြုပါမည်။

#. ခါတိုင်းလိုပင် QGIS ထဲသို့ data များထည့်သွင်းပါ။ :file:`rivers.shp` dataset (:file:`exercise_data/shapefile/` folder ထဲတွင် တွေ့ရပါမည်) ကိုအသုံးပြုပါ။
#. ၎င်းကို ထည့်သွင်းပြီးသည်နှင့် ``GRASS Panel`` ၏ :guilabel:`Filter` box ကို click နှိပ်ပြီး ``v.in.ogr.qgis`` ဆိုသည့် စာသားကိုရိုက်ပေးပြီး vector import tool ကိုရှာဖွေပါ-

   .. warning:: ဆင်တူဖြစ်သော tool နှစ်ခုရှိပါသည်- ``v.in.ogr.qgis`` နှင့် ``v.in.ogr.qgis.loc`` တို့ဖြစ်ပါသည်။ **ပထမ** တစ်ခုကို ရှာဖွေမည်ဖြစ်ပါသည်။

   .. figure:: img/grass_panel_import.png
      :align: center

   ``v`` သည် *vector* အတွက် ကိုယ်စားပြုပြီး ``in`` သည် GRASS database ထဲသို့ data ထည့်သွင်းမည့် function တစ်ခုဖြစ်ပါသည်၊ ``ogr`` သည် vector data ကိုဖတ်ရန်အသုံးပြုသည့် software library ဖြစ်ပြီး ``qgis`` သည် QGIS ထဲသို့ထည့်သွင်းထားပြီးသော vector များအနက်မှ vector တစ်ခုကို tool မှရှာဖွေလိမ့်မည်ဟု အဓိပ္ပါယ်ရပါသည်။

#. အဆိုပါ tool ကိုရှာတွေ့ပါက ၎င်းပေါ်တွင် click နှိပ်ပြီးဖွင့်ပါ။ :guilabel:`Loaded Layer` box ထဲတွင် :guilabel:`rivers` layer ကိုရွေးချယ်ပြီး ၎င်းကို :file:`g_rivers` ဟုအမည်ပေးပါ-

   .. figure:: img/grass_tool_selected.png
      :align: center

   .. note:: :abbr:`★★★ (Advanced level)` :guilabel:`Advanced Options` အောက်တွင် အပိုဆောင်းထည့်သွင်းမှုဆိုင်ရာ option များရှိပါသည်။ ထို option များထဲတွင် data များထည့်သွင်းရန်အတွက် အသုံးပြုသည့် SQL query အတွက် WHERE clause တစ်ခုကိုထည့်ပေးနိုင်သည့် လုပ်နိုင်စွမ်းပါရှိပါသည်။

#. ထည့်သွင်းမှုကိုစတင်ရန် :guilabel:`Run` ကိုနှိပ်ပါ။
#. လုပ်ဆောင်မှုပြီးသွားသောအခါ အသစ်ထည့်သွင်းထားသော GRASS layer ကို မြေပုံထဲတွင်မြင်တွေ့နိုင်ရန် :guilabel:`View output` ခလုတ်ကိုနှိပ်ပါ။
#. Import tool ကို ဦးစွာ ပိတ်ပါ (:guilabel:`View output` ၏ ညာဘက်ရှိ :guilabel:`Close` ခလုတ်)၊ ထို့နောက် :guilabel:`GRASS
   Tools` window ကိုပိတ်ပါ။
#. မူလ :guilabel:`rivers` layer ကိုဖယ်ရှားပါ။

QGIS မြေပုံထဲတွင် ထည့်သွင်းထားသော GRASS layer ကိုသာ ပြသနေပါလိမ့်မည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS ထဲသို့ Raster Data ထည့်သွင်းခြင်း (Follow Along: Loading Raster Data into GRASS)
------------------------------------------------------------------------------------------------------------------------------------

Vector layer များထည့်သွင်းသည့်အတိုင်း raster layer တစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။

|srtmFileName| layer ကို GRASS Mapset ထဲသို့ ထည့်သွင်းပါမည်။

.. note:: Raster layer သည် CRS အမှန် ``WGS 84`` တွင် ရှိနေပြီးသားဖြစ်ပါသည်။ CRS မတူညီသော layer များပါရှိလျှင် ၎င်းတို့ကို GRASS Mapset ၏ CRS နှင့်တူညီအောင် projection ပြောင်းပေးရပါမည်။


#. QGIS ထဲသို့ |srtmFileName| layer ကိုထည့်သွင်းပါ
#. :guilabel:`GRASS Tools` dialog ကို ထပ်ဖွင့်ပါ။
#. :guilabel:`Modules List` tab ကို click နှိပ်ပါ။
#. ``r.in.gdal.qgis`` ကိုရှာဖွေပြီး tool ကို click နှစ်ချက်နှိပ်ပါ။
#. Input layer တွင် |srtmFileName| ဟုသတ်မှတ်ပြီး output တွင် :file:`g_dem` ဟုသတ်မှတ်ပါ။

   .. figure:: img/g_dem_settings.png
      :align: center

#. :guilabel:`Run` ကိုနှိပ်ပါ။
#. လုပ်ငန်းစဉ် ပြီးဆုံးသွားသောအခါ :guilabel:`View output` ကို click နှိပ်ပါ။
#. လက်ရှိပွင့်နေသော tab ကိုပိတ်ပါ၊ ထို့နောက် dialog တစ်ခုလုံးကို ပိတ်ပါ။

   .. figure:: img/g_dem_result.png
      :align: center

#. မူလ |srtmFileName| layer ကိုဖယ်ရှားပစ်နိုင်ပါသည်။


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - Mapset ထဲသို့ layer များထည့်သွင်းခြင်း (Try Yourself: Add Layers to Mapset)
--------------------------------------------------------------------------------------------------------------------------------------

:file:`exercise_data/shapefile/` folder ထဲမှ :file:`water.shp` နှင့် :file:`places.shp` vector layer များကို GRASS Mapset ထဲသို့ထည့်သွင်းကြည့်ပါ။ :file:`rivers` layer အတွက် ပြုလုပ်ခဲ့သလိုပင် ထည့်သွင်းလိုက်သော layer များကို :file:`g_water` နှင့်  :file:`g_places` အဖြစ် အမည်ပြောင်းလဲပေးပါ။

.. admonition:: အဖြေ
   :class: dropdown

   Layer များ (vector နှင့် raster နှစ်မျိုးလုံး) ကို Browser ထဲတွင် click နှိပ်ဖိဆွဲပြီး GRASS Mapset တစ်ခုထဲသို့ ထည့်သွင်းနိုင်ပါသည်၊ သို့မဟုတ် vector layer များအတွက် ``v.in.gdal.qgis`` နှင့် raster layer များအတွက် ``r.in.gdal.qgis`` ကိုအသုံးပြုပြီး ထည့်သွင်းနိုင်ပါသည်။

:abbr:`★☆☆ (Basic level)` ရှိနေပြီးသား GRASS Mapset တစ်ခုကို ဖွင့်ခြင်း (Open an existing GRASS Mapset)
--------------------------------------------------------------------------------------------------------

GRASS Mapset တစ်ခုရှိနေပြီးသားဖြစ်လျှင် ၎င်းကို အခြား QGIS session တွင် အလွယ်တကူပြန်ဖွင့်နိုင်ပါသည်။

GRASS Mapset တစ်ခုကို ဖွင့်ရန် နည်းလမ်းများစွာရှိပါသည်၊ နည်းလမ်းအချို့ကို လေ့လာကြည့်ကြပါမည်။

:guilabel:`GRASS Tools` window ၏ :guilabel:`Close Mapset` ခလုတ်ကိုနှိပ်ပြီး Mapset ကိုပိတ်ကြည့်ပါမည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - GRASS plugin အသုံးပြုခြင်း (Follow Along: Using the GRASS plugin)
...............................................................................................................

#. ယခင်သင်ခန်းစာထဲတွင် တွေ့ခဲ့ရသော :guilabel:`Plugins --> GRASS --> New Mapset` menu ဘေးရှိ :guilabel:`Plugins --> GRASS --> Open Mapset` menu ပေါ်တွင် click နှိပ်ပါ။

#. GRASS database folder ကိုဖွင့်ပါ- သတိထားရမည်မှာ GRASS Mapset တစ်ခုကိုရွေးချယ်ရမည်မဟုတ်ပဲ parent (ပင်မ) folder ကိုရွေးချယ်ရမည်ဖြစ်သည်။ GRASS သည် database ၏ ``Locations`` များအားလုံးနှင့် ``Locations`` တစ်ခုချင်းစီ၏ ``Mapsets`` များအားလုံးကို ဖတ်ရှုမည်ဖြစ်ပါသည်-

   .. figure:: img/grass_open_mapset.png
      :align: center

#. ``Location`` တွင် :guilabel:`SouthAfrica` ကိုရွေးချယ်ပြီး ``Mapset`` တွင် ယခင်ကဖန်တီးခဲ့သော :guilabel:`grass_mapset` ကိုရွေးချယ်ပါ။

GRASS Panel သည် active ဖြစ်လာမည်ဖြစ်သည်၊ အဓိပ္ပါယ်မှာ Mapset ကိုမှန်ကန်စွာဖွင့်ပြီးကြောင်း ဆိုလိုခြင်းဖြစ်သည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - QGIS Browser အသုံးပြုခြင်း (Follow Along: Using the QGIS Browser)
...............................................................................................................

QGIS Browser အသုံးပြု၍ ``Mapset`` တစ်ခုကိုဖွင့်ခြင်းသည် မြန်ဆန်လွယ်ကူစေပါသည်-

#. :guilabel:`GRASS Tools` window ၏ :guilabel:`Close Mapset` ခလုတ်ကိုနှိပ်ပြီး Mapset ကိုပိတ်ပါ (အကယ်၍ Mapset သည်ပွင့်နေလျှင်)။
#. QGIS Browser ထဲတွင် GRASS database ၏ folder ကိုဖွင့်ပါ။
#. Mapset ပေါ်တွင် right-click နှိပ်ပါ (Mapset ဘေးတွင် |grassLogo| GRASS icon ပါရှိသည်)။ Option အချို့ကို မြင်တွေ့ရပါမည်။
#. :guilabel:`Open mapset` ပေါ်တွင် click နှိပ်ပါ-

   .. figure:: img/grass_open_mapset_browser.png
      :align: center

Mapset ပွင့်လာမည်ဖြစ်ပြီး ၎င်းကိုအသုံးပြုနိုင်ပြီဖြစ်ပါသည်။

.. tip:: GRASS Mapset တစ်ခုပေါ်တွင် right-click နှိပ်ပါက အမျိုးမျိုးသော setting များကို တွေ့ရပါမည်။ ၎င်းတို့ကို စူးစမ်းလေ့လာကြည့်ပြီး အသုံးဝင်သော option များအားလုံးကို ကြည့်ရှုပါ။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

GRASS တွင် data ထည့်သွင်းခြင်းသည် QGIS နှင့် အနည်းငယ်ကွဲပြားပါသည်၊ အဘယ့်ကြောင့်ဆိုသော် GRASS သည် ၎င်း၏ data များကို spatial database ဖွဲ့စည်းပုံတစ်ခုထဲသို့ ထည့်သွင်းသောကြောင့်ဖြစ်ပါသည်။ သို့သော် QGIS ကို frontend (GUI) တစ်ခုအဖြစ်အသုံးပြုခြင်းအားဖြင့် QGIS ထဲရှိ ရှိနေပြီးသား layer များကို GRASS အတွက် data source များအဖြစ်အသုံးပြုနိုင်သောကြောင့် GRASS mapset တစ်ခုကို အလွယ်တကူ setup ပြုလုပ်နိုင်မည်ဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ယခုဆိုလျှင် data ကို GRASS ထဲသို့ ထည့်သွင်းပြီးဖြစ်ပါသည်၊ GRASS တွင်လုပ်ဆောင်နိုင်သော အဆင့်မြင့် analysis လုပ်ဆောင်ချက်များကို ကြည့်ရှုနိုင်ပြီဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |grassLogo| image:: /static/common/grasslogo.png
   :width: 1.5em
.. |grassMapsetOpen| image:: /static/common/grass_mapset_open.png
   :width: 1.5em
.. |srtmFileName| replace:: :file:`srtm_41_19_4326.tif`
.. |win| image:: /static/common/win.png
   :width: 1em
