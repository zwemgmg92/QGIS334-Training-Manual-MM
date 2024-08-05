Raster layer များဖြတ်တိခြင်းနှင့် ပေါင်းစည်းခြင်း (Clipping and merging raster layers)
=======================================================================================

.. note:: Real world ဖြစ်စဉ်များတွင် geoalgorithm များကို ဆက်လက်အသုံးပြုနိုင်ရန် spatial data များပြင်ဆင်ခြင်း ဥပမာကို ဤသင်ခန်းစာတွင် လေ့လာရပါမည်။

ဤသင်ခန်းစာတွင် City ဧရိယာတစ်ခုပတ်လည်ရှိ ဧရိယာတစ်ခုအတွက် slope layer တစ်ခုကို တွက်ချက်မည်ဖြစ်ပါသည်။ DEM layer များသည် raster layer နှစ်ခုဖြစ်နေပြီး city ပတ်လည်ရှိဧရိယာထက် များစွာ ပိုကြီးနေပါသည်။ ဤသင်ခန်းစာနှင့်သက်ဆိုင်သော QGIS project ဖိုင်ကို ဖွင့်ကြည့်ပါက အောက်ပါအတိုင်းမြင်တွေ့ရပါမည်။

.. figure:: img/cutting_merging/medfordarea.png

DEM layer များတွင် ပြဿနာ နှစ်ခု ရှိနေပါသည်-

* ဧရိယာသည် ကျွန်ုပ်တို့လိုချင်သည့်ဧရိယာထက် များစွာပိုကြီးနေပါသည် (city center ပတ်လည်ရှိ ဧရိယာအသေးကိုသာ စိတ်ဝင်စားပါသည်)
* Raster ဖိုင် နှစ်ခုဖြစ်နေပါသည် (city ဧရိယာသည် raster ဖိုင်တစ်ခုထဲတွင်သာ ကျရောက်သော်လည်း city ဧရိယာပတ်လည် ဧရိယာအပိုကိုလည်း လိုချင်ပါသည်)

ထိုပြဿနာနှစ်ခုစလုံးကို သင့်လျော်သော geoalgorithm များဖြင့် ဖြေရှင်းနိုင်ပါသည်။

ပထမဦးစွာ လိုချင်သောဧရိယာကိုသတ်မှတ်ပေးမည့် ထောင့်မှန်စတုဂံတစ်ခုကို ဖန်တီးရပါမည်။ ထိုသို့လုပ်ဆောင်ရန် city ဧရိယာ၏ နယ်နိမိတ်အတိုင်းအတာ ပါဝင်သော layer တစ်ခုကိုဖန်တီးပါ၊ ထို့နောက် city ဧရိယာ၏နယ်နိမိတ်အတိုင်းအတာထက် ပိုများသောဧရိယာကို လွှမ်းခြုံသော raster layer တစ်ခုကိုရရှိရန် ၎င်းကို buffer ပြုလုပ်ပါ။

Bounding box (နယ်နိမိတ်အတိုင်းအတာ) ကိုတွက်ချက်ရန် *Polygon from layer extent* algorithm ကိုအသုံးပြုနိုင်ပါသည်။

.. figure:: img/cutting_merging/bbox.png

Buffer ပြုလုပ်ရန် အောက်ပါ parameter တန်ဖိုးများဖြင့် *Fixed distance buffer* algorithm ကိုအသုံးပြုပါမည်။

.. figure:: img/cutting_merging/buffer_dialog.png

.. warning:: လက်တလောထွက်ရှိသော ဗားရှင်းများတွင် Syntax များပြောင်းလဲထားပါသည်- Distance နှင့် Arc vertex နှစ်ခုစလုံးတွင် .25 ဟုသတ်မှတ်ပါ

အထက်ဖော်ပြပါ prameter များအသုံးပြု၍ ရရှိလာသော ရလာဒ် bounding box သည် အောက်ပါအတိုင်းဖြစ်ပါသည်

.. figure:: img/cutting_merging/buffer.png

၎င်းသည် လုံးဝန်းသော box တစ်ခုဖြစ်ပါသည်၊ သို့သော် *Polygon from layer extent* algorithm အသုံးပြုပြီး စတုရန်း box ကိုအလွယ်တကူ ရရှိနိုင်ပါသည်။ City နယ်နိမိတ်ကို ဦးစွာ buffer ပြုလုပ်ပြီးနောက် extent rectangle ကိုတွက်ချက်ပါက လုပ်ဆောင်သည့်အဆင့်တစ်ဆင့် လျှော့ချနိုင်ပါသည်။

.. figure:: img/cutting_merging/buffer_squared.png

Raster များသည် vector layer နှင့် projection မတူညီသည်ကို သတိထားမိပါလိမ့်မည်။ ထို့ကြောင့် ဆက်လက်မလုပ်ဆောင်မီ *Warp (reproject)* tool ကိုအသုံးပြုပြီး ၎င်းတို့ကို projection ပြောင်းလဲပေးသင့်ပါသည်။

.. figure:: img/cutting_merging/warp.png

.. note:: လက်တလောထွက်ရှိထားသော ဗားရှင်းများတွင် interface သည် ပိုမိုရှုပ်ထွေးပါသည်။ အနည်းဆုံးတော့ Compression နည်းလမ်းတစ်ခုကို ရွေးချယ်ပေးထားပါ။

လိုချင်သော bounding box ပါရှိသည့် vector layer ဖြင့် *Clip raster with
polygon* algorithm ကိုအသုံးပြုပြီး raster layer နှစ်ခုစလုံးကို ဖြတ်တိ (crop) နိုင်ပါသည်။

.. figure:: img/cutting_merging/clip.png 

ဖြတ်တိထားသော layer များကို SAGA *Mosaic raster layers* algorithm အသုံးပြုပြီး ပေါင်းစည်းပေးနိုင်ပါသည်။

.. figure:: img/cutting_merging/merge.png

.. note:: Merge (ပေါင်းစည်းခြင်း) အရင်ပြုလုပ်ပြီးမှ crop (ဖြတ်တိခြင်း) လုပ်ဆောင်ပါက အချိန်ကုန်သက်သာစေနိုင်ပြီး clipping algorithm ကို နှစ်ကြိမ် အသုံးပြုရန်မလိုတော့ပါ။ သို့သော် merge ပြုလုပ်ရမည့် layer များစွာရှိနေပြီး ဖိုင်အရွယ်အစားကြီးနေပါက ရလာဒ် layer သည် အရွယ်အစားကြီးနေပြီး နောက်ပိုင်းလုပ်ဆောင်မှုများတွင် အခက်အခဲတွေ့နိုင်ပါသည်။ ထိုသို့သောကိစ္စမျိုးတွင် clipping algorithm ကို အကြိမ်များစွာလုပ်ဆောင်နေရမည်ဖြစ်ပြီး အချိန်ကုန်စေနိုင်ပါသည်၊ သို့သော် ထိုသို့သောလုပ်ဆောင်မှုကို အလိုအလျောက်လုပ်ဆောင်ပေးမည့် tool အချို့ကို နောက်ပိုင်းသင်ခန်းစာတွင် လေ့လာရပါမည်။ ဤဥပမာတွင် layer နှစ်ခုသာရှိသည့်အတွက် စိုးရိမ်စရာမလိုပါ။

ကျွန်ုပ်တို့လိုချင်သော DEM ကိုရရှိပြီဖြစ်ပါသည်။

.. figure:: img/cutting_merging/finaldem.png

ယခုအခါ slope layer ကိုတွက်ချက်ပါမည်။

Slope layer ကို *Slope, Aspect, Curvature* algorithm အသုံးပြုပြီး တွက်ချက်နိုင်ပါသည်၊ သို့သော် နောက်ဆုံးအဆင့်တွင်ရရှိလာသော DEM ၏ elevation တန်ဖိုးများသည် မီတာ ဖြစ်နေပြီး cellsize ကို မီတာဖြင့် ဖော်ပြထားခြင်းမရှိသောကြောင့် (layer သည် geographic coordinates CRS ကိုအသုံးပြုထားပါသည်) ၎င်း DEM ကို input အနေဖြင့်အသုံးပြုရန် မသင့်လျော်ပါ။ Projection ပြောင်းလဲရန် လိုအပ်ပါသည်။ Raster layer တစ်ခုကို projection ပြောင်းလဲရန် *Warp (reproject)* algorithm ကိုပင် ထပ်မံအသုံးပြုနိုင်ပါသည်။ SAGA သို့မဟုတ် GDAL အသုံးပြုပြီး slope ကို မှန်မှန်ကန်ကန်တွက်ချက်နိုင်ရန် မီတာယူနစ်ရှိသော CRS တစ်ခု (ဥပမာ- 3857) သို့ projection ပြောင်းလဲပေးပါမည်။

ရရှိလာသော DEM အသစ်ဖြင့် slope ကိုတွက်ချက်နိုင်ပြီဖြစ်ပါသည်။

.. figure:: img/cutting_merging/slope.png

ရလာဒ် slope layer သည် အောက်ပါအတိုင်းဖြစ်ပါသည်။

.. figure:: img/cutting_merging/slopereproj.png

*Slope, Aspect, Curvature* algorithm ဖြင့်တွက်ထုတ်ထားသော slope ကို degrees သို့မဟုတ် radians ဖြင့်ဖော်ပြပေးနိုင်ပါသည်- degrees သည် ပိုမိုလက်တွေ့ကျပြီး အသုံးများသော ယူနစ်တစ်ခုဖြစ်ပါသည်။ Radians ဖြင့်တွက်ချက်ပါက conversion (ယူနစ်တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲခြင်း) လုပ်ဆောင်ရန် *Metric conversions* algorithm ကိုအသုံးပြုနိုင်ပါသည် (အဆိုပါ algorithm ရှိသည်ကို မသိရှိပါက raster calculator ကိုအသုံးပြုနိုင်ပါသည်)။

.. figure:: img/cutting_merging/metricconversions.png

ယူနစ်ပြောင်းလဲထားသော slope layer ကို *Reproject raster layer* အသုံးပြုပြီး projection ပြန်ပြောင်းပါက ကျွန်ုပ်တို့လိုချင်သော နောက်ဆုံးရလာဒ်ကို ရရှိပါမည်။

.. warning:: todo: Add image

Projection ပြောင်းလဲခြင်းလုပ်ငန်းစဉ်များကြောင့် နောက်ဆုံးရလာဒ် layer တွင် bounding box ၏အပြင်ဘက်ရှိ data များပါရှိနေနိုင်ပါသည်။ ထိုပြဿနာကို clipping ထပ်မံလုပ်ဆောင်ခြင်းဖြင့် ဖြေရှင်းပေးနိုင်ပါသည်။
