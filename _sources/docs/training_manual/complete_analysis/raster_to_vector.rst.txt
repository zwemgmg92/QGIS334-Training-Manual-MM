သင်ခန်းစာ- Raster မှ Vector သို့အမျိုးအစားပြောင်းခြင်း (Lesson: Raster to Vector Conversion)
=============================================================================================

Raster format နှင့် Vector format များအကြား ပြောင်းလဲခြင်းသည် GIS ပြဿနာတစ်ခုကို ဖြေရှင်းသောအခါသာမက ထိုပထဝီဝင်ဆိုင်ရာ data ပုံစံ ၂ မျိုးအတွက် အမျိုးမျိုးသော လေ့လာဆန်းစစ်ခြင်းနည်းလမ်းများကိုအသုံးပြုသောအခါ raster နှင့် vector data နှစ်မျိုးစလုံးကို သုံးစွဲနိုင်စေပါသည်။ ထိုအရာသည် GIS ပြဿနာတစ်ခုကိုဖြေရှင်းရန်အတွက် data ရင်းမြစ်များနှင့် လုပ်ဆောင်မည့်နည်းလမ်းများကို ထည့်သွင်းစဉ်းစားရာတွင် များစွာ လိုက်လျောညီထွေဖြစ်စေပါသည်။

Raster analysis တစ်ခုနှင့် Vector analysis တစ်ခုကို ပေါင်းစပ်သောအခါ တစ်ခု၏ data အမျိုးအစားကို အခြားတစ်ခု၏ data အမျိုးအစားသို့ ပြောင်းလဲရန်လိုအပ်ပါသည်။ ယခင်သင်ခန်းစာမှ raster ရလာဒ်ကို vector တစ်ခုအဖြစ်သို့ ပြောင်းကြည့်ကြရအောင်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Raster ရလာဒ်ကို Analysis ပြီးမြောက်ရန်အသုံးပြုနိုင်သော vector တစ်ခုအဖြစ် ရရှိရန်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- :guilabel:`Raster to Vector` Tool (Follow Along: The :guilabel:`Raster to Vector` Tool)
---------------------------------------------------------------------------------------------------------------------------------------

နောက်ဆုံးမော်ဂျူးမှ မြေပုံ :kbd:`raster_analysis.qgs` ဖြင့် စတင်ပါ။ ပြီးခဲ့သော လေ့ကျင့်ခန်းများအတွင်း တွက်ချက်ထားသော :kbd:`all_conditions_simple.tif` ဖိုင် ရှိပါမည်။

* :menuselection:`Raster --> Conversion --> Polygonize (Raster to Vector)` ကိုနှိပ်ပါ။ Tool dialog ပေါ်လာပါလိမ့်မည်။ 
* အောက်ပါအတိုင်း ပြင်ဆင်သတ်မှတ်ပါ-

  .. figure:: img/polygonize_raster.png
     :align: center

* Field အမည် (Raster တန်ဖိုးများကို ဖော်ပြနေသော) ကို :guilabel:`suitable` ဟုပြောင်းပါ။
* Layer ကို :file:`exercise_data/residential_development` အောက်တွင် :file:`all_terrain.shp` အဖြစ်သိမ်းဆည်းပါ။

ယခုဆိုလျှင် raster ၏တန်ဖိုးများအားလုံးပါဝင်သော vector ဖိုင်တစ်ခုကို ရရှိပြီဖြစ်ပါသည်၊ သို့သော် သင်စိတ်ဝင်စားသည့်ဧရိယာများသည် "suitable" ဧရိယာများဖြစ်ပါသည်၊ ဆိုလိုသည်မှာ :guilabel:`suitable` တန်ဖိုး ``1`` ဖြစ်သော polygon များဖြစ်သည်။ ပိုမိုရှင်းရှင်းလင်းလင်းမြင်ရလိုလျှင် ထို layer ၏ style ကို ပြောင်းလဲနိုင်ပါသည်။

:abbr:`★★☆ (Moderate level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- (Try Yourself:)
-------------------------------------------------------------------------------

Vector analysis မော်ဂျူးကို ပြန်လည်ကိုးကားပါ။

* :guilabel:`suitable` တန်ဖိုး ``1`` ရှိသော polygon များသာပါဝင်သော vector ဖိုင်အသစ်တစ်ခုကို ဖန်တီးပါ။

* ဖိုင်အသစ်ကို :file:`exercise_data/residential_development/` အောက်တွင် :file:`suitable_terrain.shp` အဖြစ်သိမ်းဆည်းပါ။

.. admonition:: အဖြေ
  :class: dropdown

   #. :guilabel:`Layers` panel ထဲရှိ :guilabel:`all_terrain` layer ပေါ်တွင် right-click နှိပ်ပြီး :menuselection:`Properties --> Source` tab ကိုရွေးချယ်ပြီး :guilabel:`Query Builder` ကိုဖွင့်ပါ။
   #. ထို့နောက် ``"suitable" = 1`` ဟူ၍ query ကိုတည်ဆောက်ပါ။
   #. ပေးထားသော query နှင့်မကိုက်ညီသော polygon များအားလုံးကို ဖယ်ကာစစ်ထုတ်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။ မူရင်း raster ကိုပြန်ကြည့်သောအခါ ဧရိယာများသည် အတိအကျထပ်နေရပါမည်-

      .. figure:: img/polygonize_raster.png
         :align: center

   #. :guilabel:`Layers` panel ထဲရှိ :guilabel:`all_terrain` layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Save As...` ကိုရွေးခြင်းဖြင့် layer ကို သိမ်းဆည်းနိုင်ပါသည်။ ထို့နောက် ညွှန်ကြားချက်တစ်ခုချင်းအတိုင်း ဆက်လက်လုပ်ဆောင်ပါ။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- :guilabel:`Vector to Raster` Tool (Follow Along: The :guilabel:`Vector to Raster` Tool)
---------------------------------------------------------------------------------------------------------------------------------------

လက်ရှိတွင် မလိုအပ်သေးသော်လည်း အထက်တွင်လုပ်ခဲ့သော Raster မှ Vector သို့အမျိုးအစားပြောင်းခြင်း၏ဆန့်ကျင်ဘက် Vector မှ Raster သို့အမျိုးအစားပြောင်းခြင်းအကြောင်းကို သိထားသင့်ပါသည်။ ပြီးခဲ့သည့်အဆင့်များတွင် ဖန်တီးခဲ့သော :file:`suitable_terrain.shp` vector ဖိုင်ကို raster အဖြစ်သို့အမျိုးအစားပြောင်းပါ။

* ဤ tool ကိုစတင်ရန် :menuselection:`Raster --> Conversion --> Rasterize (Vector to Raster)` ကိုနှိပ်ပြီး အောက်ပါပုံထဲတွင်ပြထားသည့်အတိုင်း သတ်မှတ်ပြင်ဆင်ပါ-

.. figure:: img/vector_to_raster.png
   :align: center

* :guilabel:`Input layer` သည် :guilabel:`all_terrain` ဖြစ်သည်။
* Field name သည် :guilabel:`suitable` ဖြစ်သည်။ 
* :guilabel:`Output raster size units` သည် :guilabel:`Pixels` ဖြစ်သည်။
* :guilabel:`Width` နှင့် :guilabel:`Height` တို့သည် ``837`` နှင့် ``661`` အသီးသီးဖြစ်ကြသည်။
* :guilabel:`Output extent` ကို :guilabel:`all_terrain` layer မှ ရယူပါ။
* ရလာဒ်ဖိုင် :guilabel:`Rasterized` ကို :file:`exercise_data/residential_development/raster_conversion.tif` ဟုသတ်မှတ်ပါ။

.. note::  ရလာဒ် image ၏အရွယ်အစားသည် vector သို့အမျိုးအစားပြောင်းထားသော မူရင်း raster ဖိုင်နှင့်အတူတူပင်ဖြစ်သည်။ Image တစ်ခု၏ အတိုင်းအတာများကို ကြည့်ရန် ထို image ၏ metadata ကိုဖွင့်ကြည့်ပါ ( :guilabel:`Layer Properties` ထဲရှိ :guilabel:`Metadata` tab )

* အမျိုးအစားပြောင်းခြင်းလုပ်ငန်းစဉ်ကို စတင်ရန် Dialog တွင် :guilabel:`OK` ကိုနှိပ်ပါ။
* ပြီးဆုံးသွားသောအခါ ရရှိလာသော raster အသစ်ကို မူရင်း raster နှင့်နှိုင်းယှဉ်ကြည့်ပါ။ Pixel တစ်ခုချင်းအလိုက် အတိအကျ ကိုက်ညီနေသင့်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Raster format နှင့် vector format များအကြား အမျိုးအစားပြောင်းခြင်းသည် data ကို ကျယ်ကျယ်ပြန့်ပြန့်အသုံးပြုနိုင်ပြီး data များပျက်စီးဆုံးရှုံးခြင်း မဖြစ်နိုင်ပါ။

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
-------------------------------------------------------------------------------

ယခုဆိုလျှင် မြေပြင်လေ့လာဆန်းစစ်မှုရလာဒ်များကို vector format ဖြင့် ရှိနေပြီဖြစ်ပါသည်။ ၎င်းတို့ကို လူနေအိမ်များတိုးချဲ့ဆောက်လုပ်ရေးအတွက် မည်သည့်အဆောက်အဦများကို ထည့်သွင်းစဉ်းစားသင့်သည်ဆိုသည့် ပြဿနာကို ဖြေရှင်းရာတွင် အသုံးပြုနိုင်ပါသည်။