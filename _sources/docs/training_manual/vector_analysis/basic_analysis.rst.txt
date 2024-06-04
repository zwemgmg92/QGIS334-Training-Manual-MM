သင်ခန်းစာ - Vector ဆန်းစစ်လေ့လာခြင်း (Lesson: Vector Analysis)
======================================================================

အမျိုးမျိုးသော feature များသည် တစ်ခုနှင့်တစ်ခု မည်သို့ အပြန်အလှန်တုံ့ပြန်နေသည်ကို ဖော်ထုတ်ရန်အတွက် vector data များကို ဆန်းစစ်လေ့လာနိုင်ပါသည်။ Analysis နှင့်ဆက်စပ်သော function များစွာရှိပါသည်၊ ထို့ကြောင့် ထို function အားလုံးအကြောင်းမရှင်းပြတော့ပါ။ ထိုအစား မေးခွန်းတစ်ခုထုတ်ပြီး ထို မေးခွန်းကို QGIS တွင်ရှိသော tool များကိုအသုံးပြုပြီး ဖြေရှင်းသွားမည်ဖြစ်သည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** မေးခွန်းတစ်ခုထုတ်ပြီး ၎င်းမေးခွန်းကို analysis tool များအသုံးပြုပြီး ဖြေရှင်းရန်


:abbr:`★☆☆ (Basic level)` GIS လုပ်ငန်းစဉ် (The GIS Process)
----------------------------------------------------------------------

မစတင်မီ ပြဿနာတစ်ခုကို ဖြေရှင်းရာတွင် အသုံးပြုနိုင်မည့် process ကို ခြုံငုံအနှစ်ချုပ် တစ်ခုပြုလုပ်ပါက ပိုအသုံးဝင်ပါမည်။ ထိုအတွက် နည်းလမ်းမှာ-

#. ပြဿနာကို ဖော်ထုတ်ခြင်း
#. Data များကို ရယူခြင်း
#. ပြဿနာကို ဆန်းစစ်လေ့လာခြင်း
#. ရလာဒ်များကို တင်ပြခြင်း


:abbr:`★☆☆ (Basic level)` ပြဿနာ (The Problem)
----------------------------------------------------------------------

ဖြေရှင်းရမည့် ပြဿနာတစ်ခုကို ဆုံးဖြတ်ပြီး process ကိုစတင်ကြည့်ပါမည်။ ဥပမာ- သင့်အနေဖြင့် အိမ်ခြံမြေပွဲစားတစ်ယောက်ဖြစ်ပြီး သင့်ဖောက်သည်များအတွက် |majorUrbanName| တွင် အောက်ပါသတ်မှတ်ချက်များနှင့်ကိုက်ညီသော လူနေအိမ်တစ်ခုကို ရှာဖွေနေပါသည်-

#. |majorUrbanName| ထဲတွင် တည်ရှိရန်လိုအပ်ပါသည်။
#. ကျောင်းနှင့် သင့်တော်သည့် အကွာအဝေးအတွင်း ရှိရပါမည် (၁ ကီလိုမီတာ ဆိုပါစို့)။
#. အရွယ်အစားအားဖြင့် ၁၀၀ စတုရန်းမီတာ ထက်ပိုကြီးရပါမည်။
#. အဓိကကားလမ်းမနှင့် ၅၀ မီတာအောက် ပိုနီးရပါမည်။
#. စားသောက်ဆိုင်နှင့် ၅၀၀ မီတာအောက် ပိုနီးရပါမည်။


:abbr:`★☆☆ (Basic level)` Data
----------------------------------------------------------------------

ထိုမေးခွန်းများကို ဖြေရှင်းရန် အောက်ပါ data များလိုအပ်ပါလိမ့်မည်-

#. ဧရိယာအတွင်းရှိ လူနေအိမ် (အဆောက်အဦများ)
#. မြို့ထဲနှင့် မြို့ပတ်လည်ရှိ လမ်းများ
#. ကျောင်းများနှင့် စားသောက်ဆိုင်များ၏ တည်နေရာများ
#. အဆောက်အဦများ၏ အရွယ်အစား

အဆိုပါ data များကို OSM မှတဆင့် ရယူနိုင်ပြီး ဤ manual တွင်အသုံးပြုနေဆဲ dataset များကိုလည်း ယခုသင်ခန်းစာအတွက် အသုံးပြုနိုင်ပါသည်။

အခြား ဧရိယာမှ data များကို download ရယူလိုလျှင် မည်သို့လုပ်ဆောင်ရမည်ကို :ref:`Introduction Chapter <tm_preparing_data>`  ကိုဖတ်ရှုပါ

.. note:: OSM မှ download ရယူသည်များသည် data field များ တသမတ်တည်းရှိသော်လည်း လွှမ်းခြုံမှုနှင့် အသေးစိတ်ကျမှုများ ကွဲပြားပါသည်။ ဥပမာအားဖြင့် သင်ရွေးချယ်လိုက်သော နေရာဒေသတွင် စားသောက်ဆိုင်များနှင့်ပတ်သက်သော အချက်အလက်များမပါရှိလျှင် အခြား နေရာဒေသတစ်ခုကို ရွေးချယ်ရန်လိုအပ်မည်ဖြစ်သည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- Project တစ်ခုစတင်ပြီး Data များကိုရယူပါ (Follow Along: Start a Project and get the Data)
-------------------------------------------------------------------------------------------------------------------------------------

အလုပ်လုပ်မည့် data များကို ဦးစွာ ထည့်သွင်းရန်လိုအပ်ပါသည်။

#. QGIS project အသစ်တစ်ခုကို စတင်ပါ
#. အလိုရှိလျှင် နောက်ခံမြေပုံတစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။ :guilabel:`Browser` ကိုဖွင့်ပြီး :guilabel:`XYZ Tiles` menu မှ :guilabel:`OSM` နောက်ခံမြေပုံကို ထည့်သွင်းပါ။

   .. figure:: img/osm_swellendam.png
      :align: center

#. :file:`training_data.gpkg` Geopackage database ထဲတွင် ဤသင်ခန်းစာတွင် အသုံးပြုမည့် dataset အများစုကို တွေ့ရမည်ဖြစ်သည်-

   #. ``buildings``
   #. ``roads``
   #. ``restaurants``
   #. ``schools``

   ၎င်းတို့ကို ထည့်သွင်းပါ၊ :file:`landuse.sqlite` ကိုလည်း ထည့်သွင်းပါ။

#. |majorUrbanName| ၊ South Africa ကိုမြင်ရမည့် layer extent သို့ zoom ချဲ့ပါ

   လုပ်ဆောင်မှုမစတင်မီ သီးခြား လမ်းအမျိုးအစားအချို့ကိုသာ ရရှိရန် :guilabel:`roads` layer ကို filter (စစ်ထုတ်) လုပ်ပါမည်။

   OSM dataset များထဲရှိ အချို့ လမ်းများသည် ``unclassified`` ၊ ``tracks`` ၊ ``path`` နှင့် ``footway`` များအဖြစ် ရှိနေပါသည်။ ၎င်းတို့ကို dataset ထဲမှ ဖယ်ချန်ထားပြီး ဤလေ့ကျင့်ခန်းအတွက် ပိုမိုသင့်တော်သော အခြားလမ်းအမျိုးအစားများကို အသုံးပြုမည်ဖြစ်သည်။

   ထို့အပြင် OSM data များသည် နေရာတိုင်းအတွက် update ဖြစ်နေသည်မဟုတ်သောကြောင့် ``NULL`` တန်ဖိုးများကိုလည်း ဖယ်ချန်ထားပါမည်။

#. ``roads`` layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Filter...` ကိုရွေးချယ်ပါ။
#. ပေါ်လာသော dialog ထဲတွင် အောက်ပါ expression ကိုအသုံးပြုပြီး အဆိုပါ feature များကို filter လုပ်ပါမည်-::

     "highway" NOT IN ('footway', 'path', 'unclassified', 'track') AND "highway" IS NOT NULL

   Operator ၂ ခုဖြစ်သော  ``NOT`` နှင့် ``IN`` ပေါင်းစပ်ခြင်းသည် ``highway`` field ထဲတွင် အဆိုပါ attribute တန်ဖိုးများပါရှိသော feature များအားလုံးကို ဖယ်ချန်ထားပေးမည်ဖြစ်သည်။

   ``AND`` operator နှင့်ပေါင်းစပ်အသုံးပြုသော  ``IS NOT NULL`` သည် ``highway`` field ထဲတွင် တန်ဖိုးမပါရှိသော လမ်းများကို ဖယ်ချန်ထားပေးမည်ဖြစ်သည်။

   :guilabel:`roads` layer ၏ဘေးရှိ |indicatorFilter| icon သည် အဆိုပါ layer တွင် filter လုပ်ထားသည်ကို ပြသပေးပါသည်၊ ထို့ကြောင့် project ထဲတွင် အချို့သော feature များအသုံးပြုနိုင်မည်မဟုတ်ပါ။

Data အားလုံးပါဝင်သော မြေပုံသည် အောက်ပါပုံစံအတိုင်း ဖြစ်နေသင့်ပါသည်-


.. figure:: img/osm_swellendam_2.png
   :align: center


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- Layer များ၏ CRS ကိုပြောင်းလဲပါ (Try Yourself: Convert Layers' CRS)
----------------------------------------------------------------------------------------------------------------------------

Layer များအတွင်း အကွာအဝေးတိုင်းတာမှုများပြုလုပ်မည်ဖြစ်သောကြောင့် layer များ၏ CRS ကို ပြောင်းလဲရန်လိုအပ်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် layer တစ်ခုချင်းစီကို တစ်လှည့်စီ ရွေးချယ်ပြီး projection အသစ်ဖြင့် layer အသစ်သိမ်းဆည်းရန် လိုအပ်ပါသည်။ ထို့နောက် မြေပုံထဲသို့ projection ပြောင်းထားသော layer အသစ်များကို ထည့်သွင်းပါ။

ရွေးချယ်စရာအမျိုးမျိုးရှိပါသည်၊ ဥပမာ- layer တစ်ခုချင်းစီကို ESRI Shapefile format dataset တစ်ခုအနေဖြင့် export လုပ်နိုင်သည်၊ ရှိနေပြီးသား GeoPackage ဖိုင်ထဲတွင် layer များကို append (ဆက်တွဲပေါင်းထည့်) ပြုလုပ်နိုင်သည်၊ သို့မဟုတ် အခြား GeoPackage ဖိုင်ကို ဖန်တီးပြီး projection ပြောင်းထားသော layer များဖြင့်ဖြည့်သွင်းထားနိုင်သည်။ နောက်ဆုံး ရွေးချယ်စရာကို ပြသပေးပါမည်၊ ထို့ကြောင့် :file:`training_data.gpkg` သည် ရှင်းလင်းနေပါလိမ့်မည်။ အကောင်းဆုံးဖြစ်မည့်အရာကို သင်ကိုယ်တိုင် ရွေးချယ်ကြည့်ပါ။

.. note:: ဤဥပမာတွင် *WGS 84 / UTM zone 34S* CRS ကိုအသုံးပြုနေသည်ဖြစ်သော်လည်း သင့်နေရာဒေသအတွက် ပိုမိုသင့်တော်သော UTM CRS တစ်ခုကို အသုံးပြုသင့်ပါသည်။

#. :guilabel:`Layers` panel ထဲရှိ :guilabel:`roads` layer ကို right-click နှိပ်ပါ
#. :guilabel:`Export --> Save Features As...` ကိုနှိပ်ပါ
#. :guilabel:`Save Vector Layer As` dialog ထဲတွင် :guilabel:`Format` အနေဖြင့် :guilabel:`GeoPackage` ကိုရွေးချယ်ပါ
#. :guilabel:`File name` အတွက် :guilabel:`...` ကိုနှိပ်ပြီး GeoPackage အသစ်ကို ``vector_analysis`` ဟု အမည်ပေးပါ
#. :guilabel:`Layer name` ကို ``roads_34S`` ဟုပြောင်းပါ
#. :guilabel:`CRS` ကို *WGS 84 / UTM zone 34S* သို့ပြောင်းပါ
#. :guilabel:`OK` ကိုနှိပ်ပါ-

   .. figure:: img/save_roads_34S.png
      :align: center

   ထိုသို့လုပ်ခြင်းသည် GeoPackage database အသစ်ကိုဖန်တီးပေးမည်ဖြစ်ပြီး ``roads_34S`` layer ကို ထည့်သွင်းပေးမည်ဖြစ်သည်။

#. Layer တစ်ခုချင်းစီအတွက် ထို process အတိုင်းထပ်ခါထပ်ခါလုပ်ဆောင်ပါ၊ :file:`vector_analysis.gpkg` GeoPackage ထဲတွင် မူရင်းအမည်နောက်၌ ``_34S`` တွဲဆက်ထားသော layer အသစ်တစ်ခုစီကို ဖန်တီးပေးပါသည်။
   
   MacOS တွင် ပေါ်လာသော dialog ထဲရှိ :guilabel:`Replace` ခလုတ်ကိုနှိပ်ခြင်းသည် ရှိနေပြီးသား GeoPackage ကို အစားထိုးလုပ်ဆောင်ပေး (overwrite) စေပါသည်။

   .. note:: ရှိနေပြီးသား GeoPackage တစ်ခုထဲသို့ layer တစ်ခုကိုသိမ်းဆည်းသောအခါ GeoPackage ထဲတွင် အမည်တူ layer ရှိမနေလျှင် QGIS သည် ရှိနေပြီးသား layer များနောက်တွင် သိမ်းဆည်းမည့် layer ကို *ထည့်သွင်း* ပေးပါလိမ့်မည်။

#. Project မှ layer အဟောင်းများတစ်ခုချင်းစီကို ဖယ်ရှားပါ
#. Layer များအားလုံးအတွက် process လုပ်ဆောင်ပြီးပါက layer တစ်ခုခုပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Zoom to layer extent` ကိုနှိပ်ပါ။

ယခုဆိုလျှင် OSM data များကို UTM projection တစ်ခုသို့ ပြောင်းလဲပြီးဖြစ်ပါသည်၊ ထို့ကြောင့် တွက်ချက်မှုများကို စတင်လုပ်ဆောင်နိုင်ပြီဖြစ်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- ပြဿနာကိုဆန်းစစ်လေ့လာခြင်း - ကျောင်းများနှင့် လမ်းများမှ အကွာအဝေးများ (Follow Along: Analyzing the Problem: Distances From Schools and Roads)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

QGIS တွင် မည်သည့် vector object နှစ်ခုအကြားရှိ အကွာအဝေးများကို တွက်ချက်နိုင်ပါသည်။

#. ``roads_34S`` နှင့် ``buildings_34S`` layer များကို မြင်ရနိုင်အောင် ဖွင့်ထားပါ (မြေပုံကို ကြည့်ရရှင်းလင်းစေရန်)
#. :menuselection:`Processing --> Toolbox` ကိုနှိပ်ပါ။ အခြေခံအားဖြင့် algorithm **အားလုံး** (vector **နှင့်** raster analysis အတွက်) သည် ဤ toolbox ထဲတွင် ရှိပါသည်။
#. :guilabel:`Buffer` algorithm ကိုအသုံးပြုပြီး ``roads_34S`` ပတ်လည်ရှိ ဧရိယာကို စတင် တွက်ချက်ပါမည်။ ထို algorithm ကို :menuselection:`Vector Geometry` အုပ်စုထဲတွင် ရှာဖွေနိုင်ပါသည်။

   .. figure:: img/processing_buffer_1.png
      :align: center

   သို့မဟုတ် toolbox ၏အပေါ်ဘက်ရှိ search menu ထဲတွင် ``buffer`` ဟုရိုက်ထည့်ပြီး ရှာဖွေနိုင်ပါသည်-

   .. figure:: img/processing_buffer_2.png
      :align: center

#. Algorithm dialog ကိုဖွင့်ရန် ၎င်းကို click ၂ ချက်နှိပ်ပါ။
#. :guilabel:`Input layer` အဖြစ် ``roads_34S`` ကိုရွေးချယ်ပါ၊ :guilabel:`Distance` ကို 50 သတ်မှတ်ပြီး ကျန်ရှိသော parameter များအတွက် default တန်ဖိုးများသာထားရှိပါ။

   .. figure:: img/vector_buffer_setup.png
      :align: center

#. Default :guilabel:`Distance` သည် မီတာဖြင့် ဖြစ်ပါသည်၊ အဘယ်ကြောင့်ဆိုသော် ထည့်သွင်းအသုံးပြုသော dataset သည် Projected Coordinate System တစ်ခုဖြင့်ဖြစ်ပြီး ၎င်း PCS ၏ အခြေခံအတိုင်းအတာယူနစ်သည် မီတာဖြစ်ပါသည်။ အခြား projected ယူနစ်များဖြစ်သော ကီလိုမီတာ၊ ကိုက်၊ အစရှိသည့် ယူနစ်များကို ရွေးချယ်ရန် combo box ကိုအသုံးပြုနိုင်ပါသည်။

   .. note:: Geographic Coordinate System ဖြင့် layer တစ်ခုတွင် buffer တစ်ခုပြုလုပ်ပါက Processing သည် သတိပေးလိမ့်မည်ဖြစ်ပြီး layer ကို မက်ထရစ် ကိုဩဒိနိတ်စနစ်တစ်ခုသို့ projection ပြောင်းရန်အကြံပြုပါလိမ့်မည်။

#. Default အားဖြင့် *Processing* သည် ယာယီ layer များကို ဖန်တီးပေးပြီး ၎င်းတို့ကို :guilabel:`Layers` panel ထဲသို့ ထည့်သွင်းပေးပါသည်။ အောက်ပါနည်းအတိုင်းလုပ်ခြင်းဖြင့် ရလာဒ်ကို  GeoPackage database ထဲသို့လည်း ပေါင်းထည့်ပေးနိုင်ပါသည်-
   
   #. :guilabel:`...` ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Save to GeoPackage...` ကိုရွေးပါ
   #. Layer အသစ်ကို ``roads_buffer_50m`` ဟုအမည်ပေးပါ
   #. ၎င်းကို :file:`vector_analysis.gpkg` ဖိုင်ထဲတွင် သိမ်းဆည်းပါ

   .. figure:: img/buffer_saving.png
      :align: center

#. :guilabel:`Run` ကိုနှိပ်ပြီးနောက် :guilabel:`Buffer` dialog ကိုပိတ်လိုက်ပါ

   ယခုအခါ မြေပုံသည် အောက်ပါပုံစံအတိုင်း ဖြစ်နေပါလိမ့်မည်-

   .. figure:: img/roads_buffer_result.png
      :align: center

Layer အသစ်သည် :guilabel:`Layers` စာရင်း၏ ထပ်ဆုံးတွင်ရှိလျှင် မြေပုံ၏နေရာတော်တော်များများကို ဖုံးအုပ်ကောင်း ဖုံးအုပ်နေပါလိမ့်မည်၊ သို့သော် လမ်း၏ 50 မီတာ အတွင်းရှိသော ဧရိယာများအားလုံးကို ပြသပေးမည်ဖြစ်သည်။

Buffer (ကြားခံဇုံ) အတွင်းတွင် သိသာထင်ရှားသော ဧရိယာများရှိသည်ကို သတိပြုကြည့်ပါ၊ ၎င်းသည် လမ်းတစ်ခုချင်းစီနှင့်သက်ဆိုင်နေပါသည်။ ထိုသို့သော ပြဿနာကို ရှောင်ရှားရန်-

#. :guilabel:`roads_buffer_50m` layer ကို အမှန်ခြစ်ဖြုတ်ပါ၊ :guilabel:`Dissolve results` ကိုအမှန်ခြစ်ထားပြီး buffer ကို ပြန်လည်ဖန်တီးပါ။

   .. figure:: img/dissolve_buffer_setup.png
      :align: center

#. Output ကို :guilabel:`roads_buffer_50m_dissolved` အနေဖြင့် သိမ်းဆည်းပါ
#. :guilabel:`Run` ကိုနှိပ်ပြီး :guilabel:`Buffer` dialog ကိုပိတ်ပါ။

:guilabel:`Layers` panel ထဲသို့ layer ကိုထည့်သွင်းပြီးသည်နှင့်တပြိုင်နက် အောက်ပါပုံစံအတိုင်း ပေါ်လာပါလိမ့်မည်-

.. figure:: img/dissolve_buffer_results.png
   :align: center

ယခုအခါ မလိုအပ်သော အကန့်အခွဲ (subdivision) များ မရှိတော့ပါ။

.. note:: Dialog ၏ညာဘက်ခြမ်းရှိ *Short Help*  သည် algorithm မည်သို့ အလုပ်လုပ်သည်ကို ရှင်းပြပေးပါသည်။ အချက်အလက်များပိုမိုသိလိုပါက အောက်ခြေရှိ :guilabel:`Help` ခလုတ်ကိုနှိပ်ပြီး algorithm ၏ပိုမိုအသေးစိတ်သော လမ်းညွှန်ချက်ကို ဖွင့်နိုင်ပါသည်။

.. _backlink-vector-analysis-basic-1:

:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- ကျောင်းများမှ အကွာအဝေး (Try Yourself: Distance from schools)
----------------------------------------------------------------------------------------------------------------------

အထက်ဖော်ပြပါ နည်းလမ်းကိုအသုံးပြုပြီး ကျောင်းများအတွက် buffer တစ်ခုကို ဖန်တီးပါ။

အချင်းဝက် သည် ``1 km`` ဖြစ်ပါလိမ့်မည်။ Layer အသစ်ကို :file:`vector_analysis.gpkg` ဖိုင်ထဲတွင် ``schools_buffer_1km_dissolved`` အနေဖြင့် သိမ်းဆည်းပါ။

.. admonition:: အဖြေ
   :class: dropdown

   * Buffer dialog သည် အောက်ပါပုံစံအတိုင်း ဖြစ်သင့်ပါသည်-

     .. figure:: img/schools_buffer_setup.png
        :align: center

   :guilabel:`Buffer distance` သည် :guilabel:`1` ကီလိုမီတာ ဖြစ်ပါသည်။

   * :guilabel:`Segments to approximate` တန်ဖိုးတွင် :guilabel:`20` ဟုသတ်မှတ်ပါ။ ၎င်းသည် မဖြစ်မနေလုပ်ဆောင်ရန်မလိုအပ်ပါ၊ သို့သော် ထည့်သွင်းရန် အကြံပြုပါသည်၊ အဘယ်ကြောင့်ဆိုသော် ရလာဒ် buffer ကို ပိုမိုချောမွေ့စေပါသည်။ အောက်ပါပုံ ၂ ပုံကို နှိုင်းယှဉ်ကြည့်ပါ-

     .. figure:: img/schools_buffer_5.png
        :align: center


     .. figure:: img/schools_buffer_6.png
        :align: center

   ပထမပုံသည် :guilabel:`Segments to approximate` တန်ဖိုး :guilabel:`5` ဖြင့် buffer ကိုပြသပြီး ဒုတိယပုံသည် :guilabel:`Segments to approximate` တန်ဖိုး :guilabel:`20` ဖြင့် buffer ကိုပြသပါသည်။ ယခုဥပမာတွင် ခြားနားချက်သည် သိပ်မသိသာသော်လည်း တန်ဖိုးမြင့်သည့် buffer ၏အစွန်းများသည် ပိုမိုပြီး ချောမွေ့သည်ကို တွေ့ရနိုင်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- ထပ်နေသော ဧရိယာများ (Follow Along: Overlapping Areas)
-------------------------------------------------------------------------------------------------

ယခုအခါ လမ်းနှင့် မီတာ ၅၀ အောက် ကွာဝေးသော ဧရိယာများနှင့် ၁ ကီလိုမီတာအတွင်း ကျောင်းရှိသော ဧရိယာများ (တိုက်ရိုက်မျဉ်း၊ လမ်းမှမဟုတ်) ကို ဖော်ထုတ်ပြီးဖြစ်ပါသည်။ သို့သော် ထို သတ်မှတ်ချက် (criteria) နှစ်ခုစလုံးနှင့် ကိုက်ညီသည့် ဧရိယာများကိုသာ လိုချင်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် :guilabel:`Intersect` tool ကိုအသုံးပြုပါမည်။ :guilabel:`Processing Toolbox` ထဲရှိ :menuselection:`Vector Overlay` အုပ်စုထဲတွင် ရှာဖွေနိုင်ပါသည်။

#. Buffer layer နှစ်ခုအား :guilabel:`Input layer` နှင့် :guilabel:`Overlay layer` အဖြစ် အသုံးပြုပါ၊ :guilabel:`Intersection` ထဲတွင် :file:`vector_analysis.gpkg` GeoPackage ကိုရွေးချယ်ပြီး :guilabel:`Layer name` ကို ``road_school_buffers_intersect`` ပေးပါ။ ကျန်သောအရာများကို default အတိုင်း ချန်ထားခဲ့ပါ။

   .. figure:: img/school_roads_intersect.png
      :align: center

#. :guilabel:`Run` ကိုနှိပ်ပါ။

   အောက်ပါပုံထဲတွင် အပြာရောင်ဧရိယာများသည် အကွာအဝေး criteria နှစ်ခုစလုံးနှင့်ကိုက်ညီသော ဧရိယာများဖြစ်သည်။

   .. figure:: img/intersect_result.png
      :align: center

#. ကျွန်ုပ်တို့ တကယ်လိုအပ်သည်မှာ ထပ်နေသောဧရိယာ layer ဖြစ်သောကြောင့် Buffer layer နှစ်ခုကို ဖယ်ရှားပြီး ထပ်နေသောဧရိယာကို ပြသသော layer ကိုသာ ဆက်လက်ထားရှိနိုင်ပါသည်-

   .. figure:: img/final_intersect_result.png
      :align: center

.. _select-by-location:

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- အဆောက်အဦများကို ထုတ်ယူခြင်း (Follow Along: Extract the Buildings)
--------------------------------------------------------------------------------------------------------------

ယခုဆိုလျှင် အဆောက်အဦများ ထပ်နေရမည့် ဧရိယာကို ရရှိပြီးဖြစ်ပါသည်။ နောက်တစ်ဆင့်အနေဖြင့် အဆိုပါ ဧရိယာထဲရှိ အဆောက်အဦများကို extract (ထုတ်ယူ) ပြုလုပ်မည်ဖြစ်သည်။

#. *Processing Toolbox* ထဲတွင် :menuselection:`Vector Selection --> Extract by location` ကိုရှာဖွေပါ။
#. :guilabel:`Extract features from` တွင် ``buildings_34S`` ကိုရွေးချယ်ပါ။ :guilabel:`Where the features (geometric predicate)` တွင် :guilabel:`intersect` ကိုအမှန်ခြစ်ပါ၊  :guilabel:`By comparing to the features from` တွင် buffer များကို intersect လုပ်ထားသော layer ကိုရွေးချယ်ပါ။ ရလာဒ် layer ၏အမည်ကို ``well_located_houses`` ဟုအမည်ပေးပြီး :file:`vector_analysis.gpkg` ဖိုင်တွင် သိမ်းဆည်းပါ။

   .. figure:: img/location_select_dialog.png
      :align: center

#. :guilabel:`Run` ကိုနှိပ်ပါ၊ dialog ကိုပိတ်ပါ
#. ကြီးကြီးမားမားပြောင်းလဲမှုမရှိသကဲ့သို့ တွေ့ရပါလိမ့်မည်။ သို့သော် Layer များစာရင်းထဲတွင် :guilabel:`well_located_houses` layer ကိုထိပ်သို့ရွှေ့လိုက်ပြီး zoom ချဲ့ကြည့်ပါ။

   .. figure:: img/select_zoom_result.png
      :align: center

   အနီရောင် အဆောက်အဦများသည် သတ်မှတ်ချက်များနှင့် ကိုက်ညီသော အဆောက်အဦများဖြစ်ပြီး အစိမ်းရောင် အဆောက်အဦများသည် သတ်မှတ်ချက်နှင့်မကိုက်ညီသည်များဖြစ်သည်။
#. ယခုအခါ သီးခြား layer နှစ်ခု ရရှိပြီဖြစ်ပြီး layer စာရင်းမှ ``buildings_34S`` ကိုဖယ်ရှားပစ်နိုင်ပါသည်။

:abbr:`★★☆ (Moderate level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- အဆောက်အဦများကို ထပ်မံ၍ စစ်ထုတ်ခြင်း (Try Yourself: Further Filter our Buildings)
---------------------------------------------------------------------------------------------------------------------------------------------

ယခုဆိုလျှင် ကျောင်းတစ်ကျောင်း၏ ၁ ကီလိုမီတာအတွင်း နှင့် လမ်း၏ ၅၀ မီတာ အတွင်းကျရောက်သော အဆောက်အဦများအားလုံးကို ပြသသော layer တစ်ခုရှိပြီဖြစ်ပါသည်။ ထပ်မံ၍ စားသောက်ဆိုင်တစ်ခု၏ ၅၀၀ မီတာအတွင်းကျရောက်သော အဆောက်အဦများကိုသာ ပြသလိုပါသည်။

စားသောက်ဆိုင်တစ်ခု၏ ၅၀၀ မီတာအတွင်းကျရောက်သော အဆောက်အဦများကိုသာ ပြသရန် :guilabel:`well_located_houses` layer ကိုထပ်မံ စစ်ထုတ်မည့် :guilabel:`houses_restaurants_500m` ဟုခေါ်သော layer အသစ်တစ်ခုကို အထက်တွင် ဖော်ပြခဲ့သော process များကိုအသုံးပြုပြီးဖန်တီးပါ။

.. admonition:: အဖြေ
   :class: dropdown

   :guilabel:`houses_restaurants_500m` layer အသစ်ကို ဖန်တီးရန် အဆင့် နှစ်ဆင့်ဖြင့် လုပ်ဆောင်ပါမည်-

   #. ဦးစွာ စားသောက်ဆိုင်များပတ်လည် ၅၀၀ မီတာ buffer တစ်ခုကိုဖန်တီးပြီး ၎င်း layer ကို မြေပုံထဲသို့ ထည့်သွင်းပါ-

      .. figure:: img/restaurants_buffer.png
         :align: center

      .. figure:: img/restaurants_buffer_result.png
         :align: center

   #. နောက်တစ်ဆင့်အနေဖြင့် အဆိုပါ buffer ဧရိယာအတွင်းရှိ အဆောက်အဦများကို extract လုပ်ပါ-

      .. figure:: img/select_within_restaurants.png
         :align: center

   ယခုဆိုလျှင် လမ်း၏ ၅၀ မီတာအတွင်းရှိပြီး ကျောင်းတစ်ကျောင်း၏ ၁ ကီလိုမီတာအတွင်းရှိကာ စားသောက်ဆိုင်တစ်ဆိုင်၏ ၅၀၀ မီတာအတွင်း ကျရောက်သော အဆောက်အဦများကိုသာ မြေပုံပေါ်တွင် ပြသပါလိမ့်မည်-

   .. figure:: img/restaurant_buffer_result.png
      :align: center

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- အရွယ်အစားမှန်ကန်သော အဆောက်အဦများကို ရွေးချယ်ပါ (Follow Along: Select Buildings of the Right Size)
----------------------------------------------------------------------------------------------------------------------------------------------

မည်သည့် အဆောက်အဦများသည် အရွယ်အစားအမှန် (၁၀၀ စတုရန်းမီတာထက်ကြီးသော) ရှိသည်ကို မြင်ရရန် အဆောက်အဦများ၏အရွယ်အစားကို တွက်ချက်ရန် လိုအပ်ပါသည်။

#. :guilabel:`houses_restaurants_500m` layer ကို ရွေးချယ်ပြီး main toolbar ထဲ သို့မဟုတ် attribute ဇယား ထဲရှိ |calculateField|
   :sup:`Open Field Calculator` ခလုတ်ကို နှိပ်ခြင်းဖြင့် *Field Calculator* ကိုဖွင့်ပါ
#. :guilabel:`Create a new field` ကိုရွေးပါ၊ :guilabel:`Output field name` တွင် ``AREA`` ဟုသတ်မှတ်ပါ၊ :guilabel:`Output field type` အဖြစ်  :guilabel:`Decimal number (real)` ကိုရွေးချယ်ပါ၊ ထို့နောက် :menuselection:`Geometry` အုပ်စုမှ ``$area`` ကိုရွေးချယ်ပါ။

   .. figure:: img/buildings_area_calculator.png
      :align: center

   ``AREA`` ဆိုသည့် field အသစ်တွင် အဆောက်အဦတစ်ခုချင်းစီ၏ ဧရိယာကို စတုရန်းမီတာဖြင့် ပြသပါလိမ့်မည်။
#. :guilabel:`OK` ကိုနှိပ်ပါ။
   Attribute ဇယား၏အဆုံးတွင် ``AREA`` field ကိုထည့်သွင်းပြီးဖြစ်ပါသည်။
#. Edit ပြုလုပ်ခြင်းကို အဆုံးသတ်ရန် |toggleEditing| :sup:`Toggle Editing` ခလုတ်ကိုနှိပ်ပြီး သတိပေးစာတိုပေါ်လာလျှင် edit လုပ်ထားသည်များကို သိမ်းဆည်းပါ။
#. Layer properties ၏ :menuselection:`Source` tab ထဲတွင် :guilabel:`Provider Feature Filter` ၌ ``"AREA" >= 100`` ဟုသတ်မှတ်ပါ။

   .. figure:: img/buildings_area_query.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ။

Criteria များနှင့်ကိုက်ညီပြီး အရွယ်အစားအားဖြင့် ၁၀၀ စတုရန်းမီတာထက်ကြီးသော အဆောက်အဦများကိုသာ မြေပုံတွင် ပြသပေးပါလိမ့်မည်။


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- (Try Yourself:)
----------------------------------------------------------------------

အထက်တွင် လေ့လာခဲ့ရသော နည်းလမ်းများကို အသုံးပြုပြီး မိမိဖြေရှင်းထားသည့်အရာကို layer အသစ်တစ်ခုအဖြစ် သိမ်းဆည်းပါ။ ဖိုင်ကို ``solution`` ဆိုသည့် အမည်ဖြင့် တူညီသော GeoPackage database ထဲတွင် သိမ်းဆည်းသင့်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
----------------------------------------------------------------------

GIS ဆိုင်ရာပြဿနာများဖြေရှင်းခြင်းနည်းလမ်းကို QGIS vector analysis tool များဖြင့် ပေါင်းစပ်အသုံးပြုခြင်းသည် များစွာသော သတ်မှတ်ချက် (criteria) များရှိသော ပြဿနာတစ်ခုကို လွယ်ကူလျင်မြန်စွာ ဖြေရှင်းပေးစေနိုင်ပါသည်။

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
----------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် point တစ်ခုမှ နောက်ထပ် point တစ်ခုသို့ ရောက်ရှိရန် လမ်းများတစ်လျှောက်အတိုဆုံး အကွာအဝေးကို တွက်ချက်ခြင်းနည်းကို သင်ကြားပေးမည်ဖြစ်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |indicatorFilter| image:: /static/common/mIndicatorFilter.png
   :width: 1.5em
.. |majorUrbanName| replace:: Swellendam
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
