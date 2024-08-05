.. _tm_start_modeler:

Model designer စတင်အသုံးပြုခြင်း (Starting with the model designer)
========================================================================

.. note:: Workflow တစ်ခုကိုသတ်မှတ်ရန်နှင့် algorithm များကိုတစ်ခုနှင့်တစ်ခုချိတ်ဆက် run ရာတွင်အသုံးပြုနိုင်သည့် model designer ကို ဤသင်ခန်းစာတွင် အသုံးပြုသွားပါမည်။

Processing tool များဖြင့်လုပ်ဆောင်သော သာမန်အပိုင်းများတွင် algorithm တစ်ခုထက်ပိုပြီး run ရခြင်းများ ပါဝင်ပါသည်။ ရလာဒ်တစ်ခုကိုရရှိရန် algorithm များစွာကို run ပေးရပြီး ထို algorithm များမှရရှိသော output များကို အခြားသော algorithm များတွင် input အနေဖြင့် အသုံးပြုကြပါသည်။

Model designer ကိုအသုံးပြုပါက model တစ်ခုထဲတွင် လုပ်ဆောင်ရမည့် workflow ကိုထည့်သွင်းပေးနိုင်ပြီး လိုအပ်သော algorithm များအားလုံးကို တစ်ကြိမ်တည်း run နိုင်မည်ဖြစ်ပါသည်။ ထို့ကြောင့် လုပ်ငန်းစဉ်တစ်ခုလုံးကို ရိုးရှင်းစေပြီး အလိုအလျောက်လုပ်ဆောင်စေနိုင်ပါသည်။

ဤသင်ခန်းစာအစတွင် Topographic Wetness Index ဟုခေါ်သော parameter တစ်ခုကို တွက်ချက်ပါမည်။ ထို parameter ကိုတွက်ချက်မည့် algorithm ကို :guilabel:`Topographic wetness index (twi)` ဟုခေါ်ပါသည်။

.. figure:: img/modeler_twi/twi.png

မြင်တွေ့ရသည့်အတိုင်း မဖြစ်မနေထည့်သွင်းပေးရမည့် input နှစ်ခုရှိပါသည်- *Slope* နှင့် *Catchment area* တို့ဖြစ်ပါသည်။ Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုသော) input တစ်ခုလည်း ရှိပါသေးသည်၊ သို့သော် ၎င်းကို အသုံးပြုမည်မဟုတ်သည့်အတွက် ချန်ထားခဲ့နိုင်ပါသည်။

ဤသင်ခန်းစာအတွက် DEM data တစ်ခုသာပါဝင်ပါသည်၊ ထို့ကြောင့် ကျွန်ုပ်တို့တွင် လိုအပ်သော input များမရှိသေးပါ။ သို့သော် slope နှင့် catchment area ကိုတွက်ချက်ရန် algorithm များကို လေ့လာခဲ့ပြီးဖြစ်သောကြောင့် DEM မှ ၎င်းတို့နှစ်ခုကို တွက်ချက်သည့်နည်းကို သိရှိပြီးဖြစ်ပါသည်။ ထို့ကြောင့် ထို layer နှစ်ခုကို ဦးစွာတွက်ချက်ပြီး TWI algorithm ထဲတွင် ထည့်သွင်းအသုံးပြုမည်ဖြစ်ပါသည်။

ထို လိုအပ်သည့် input layer နှစ်ခုကို တွက်ချက်ရန် အသုံးပြုသင့်သည့် parameter များမှ အောက်ပါအတိုင်းဖြစ်ပါသည်။

.. note:: Slope ကို radians ဖြင့် တွက်ချက်ရမည်ဖြစ်ပါသည်၊ degrees ဖြင့်မတွက်ချက်ရပါ။

.. figure:: img/modeler_twi/slope.png

.. figure:: img/modeler_twi/area.png

TWI algorithm တွင်သတ်မှတ်ပေးရမည့် parameter များမှာ အောက်ပါအတိုင်းဖြစ်ပါသည်။

.. figure:: img/modeler_twi/twi_filled.png


ရရှိလာမည့် ရလာဒ်သည် အောက်ပါအတိုင်းဖြစ်ပါသည် (ပုံဖော်ပြသရန်အတွက် default ဖြစ်သော singleband pseudocolor inverted palette ကိုအသုံးပြုထားပါသည်)။ ပေးထားသော :file:`twi.qml` style ကိုအသုံးပြုနိုင်ပါသည်။

.. figure:: img/modeler_twi/twi_layer.png

What we will try to do now is to create an algorithm that calculates the TWI from a DEM in just one single step. That will save us work in case we later have to compute a TWI layer from another DEM, since we will need just one single step to do it instead of the three above. All the processes that we need are found in the  toolbox, so what we have to do is to define the workflow to wrap them. This is where the model designer comes in.
ယခုအခါ DEM တစ်ခုမှ TWI ကို အဆင့်တစ်ဆင့်တည်းဖြင့် တွက်ချက်ရန် algorithm တစ်ခုကိုဖန်တီးမည်ဖြစ်ပါသည်။ အဆင့် ၃ ဆင့်လုပ်ဆောင်ရမည့်အစား အဆင့်တစ်ဆင့်တည်းဖြင့်လုပ်ဆောင်နိုင်သောကြောင့် နောက်ပိုင်းတွင် အခြားသော DEM တစ်ခုမှ TWI တွက်ချက်ရန်ရှိပါက လွယ်ကူစေမည်ဖြစ်ပါသည်။ လိုအပ်သော လုပ်ငန်းစဉ်များအားလုံးကို toolbox ထဲတွင်တွေ့နိုင်ပြီး ၎င်းတို့ကိုစုစည်းပြီး workflow ကိုသတ်မှတ်ရပါမည်။ Model designer ကိုဖွင့်ရန်-

#. Processing menu ထဲမှ modeler ကိုဖွင့်ပါ။

   .. figure:: img/modeler_twi/modeler.png

   Model တစ်ခုဖန်တီးရန် အချက်နှစ်ချက် လိုအပ်ပါသည်- လိုအပ်သော input များကို သတ်မှတ်ခြင်းနှင့် algorithm ကိုသတ်မှတ်ခြင်းဖြစ်ပါသည်။ Model window ၏ ဘယ်ဘက်ခြမ်းရှိ :guilabel:`Inputs` နှင့် :guilabel:`Algorithms` tab နှစ်ခုမှ ထို element နှစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။

#. Input ကိုအရင်ထည့်သွင်းပါမည်။ ဤဥပမာတွင် input များစွာ ထည့်သွင်းရန်မလိုပါ။ တစ်ခုတည်းသော Input data အဖြစ် DEM raster layer ကိုသာ လိုအပ်ပါသည်။

#. :guilabel:`Raster layer` input ကို click နှစ်ချက်နှိပ်ပါက အောက်ပါ dialog ကိုတွေ့ရပါမည်။

   .. figure:: img/modeler_twi/raster_input.png

#. ဤနေရာတွင် လိုချင်သော input ကို သတ်မှတ်ပေးရပါမည်-

   #. DEM raster layer ကိုထည့်သွင်းလိုသောကြောင့် ``DEM`` ဟုနာမည်ပေးပါမည်။ ၎င်းနာမည်သည် model တွင်မြင်တွေ့ရမည့်နာမည်ဖြစ်ပါသည်။
   #. ထို layer ဖြင့်အလုပ်လုပ်ဆောင်ရန် လိုအပ်သောကြောင့် ၎င်းကို mandatory (မဖြစ်မနေလိုအပ်သော) layer အဖြစ်သတ်မှတ်ပါမည်။

   အောက်ပါအတိုင်း dialog တွင် သတ်မှတ်သင့်ပါသည်။

   .. figure:: img/modeler_twi/raster_input_filled.png

#. :guilabel:`OK` ကိုနှိပ်ပါက input သည် modeler canvas ထဲတွင် ပေါ်လာပါလိမ့်မည်။

   .. figure:: img/modeler_twi/canvas_1.png

#. :guilabel:`Algorithms` tab ကိုနှိပ်ပါ။
#. ပထမဦးဆုံး run ရမည့် algorithm သည် :guilabel:`Slope, aspect, curvature` algorithm ဖြစ်ပါသည်။ Algorithm စာရင်းထဲတွင် ၎င်းကိုရှာဖွေပြီး click နှစ်ချက်နှိပ်ပါ၊ အောက်ပါ dialog ကိုမြင်တွေ့ရပါမည်။

   .. figure:: img/modeler_twi/slope_modeler.png

   ဤ dialog သည် toolbox မှ algorithm ကို run သောအခါတွေ့ရသည့် dialog နှင့် များစွာဆင်တူပါသည်၊ သို့သော် parameter တန်ဖိုးများအဖြစ် အသုံးပြုနိုင်သည့် element များသည် လက်ရှိ QGIS project မှ ယူထားခြင်းမဟုတ်ပါ၊ model ထဲမှ ယူထားခြင်းဖြစ်ပါသည်။ ဆိုလိုသည်မှာ *Elevation* field အတွက်ထည့်သွင်းရာတွင် project ထဲတွင်ရှိသော raster layer များအားလုံးကိုအသုံးပြုနိုင်မည်မဟုတ်ပဲ model ထဲတွင်သတ်မှတ်ပေးထားသော raster layer များကိုသာ အသုံးပြုနိုင်ပါမည်။ Model ထဲတွင် ``DEM`` ဟုနာမည်ပေးထားသော raster input တစ်ခုတည်းသာရှိသည့်အတွက် :guilabel:`Elevation` parameter ထဲတွင် ထို DEM raster layer ကိုသာ မြင်တွေ့ရမည်ဖြစ်သည်။

   Algorithm ကို model တစ်ခု၏ အစိတ်အပိုင်းတစ်ခုအဖြစ်အသုံးပြုသောအခါ algorithm မှထွက်လာသော output ကို ကိုင်တွယ်ပုံသည် အနည်းငယ်ကွဲပြားပါသည်။ Output တစ်ခုချင်းစီကိုသိမ်းဆည်းရန် ဖိုင်လမ်းကြောင်းရွေးချယ်ပေးရမည့်အစား ထို output သည် intermediate layer တစ်ခု (ကြားအဆင့်တွင် လိုအပ်သော layer) ဟုတ်/မဟုတ် သို့မဟုတ် နောက်ဆုံး output တစ်ခု ဟုတ်/မဟုတ်ကိုသာ သတ်မှတ်ပေးရမည်ဖြစ်သည်။ ဤဥပမာတွင် ယခု algorithm မှထွက်လာသော layer များအားလုံးသည် intermediate layer များဖြစ်ပါသည်။ ၎င်း layer များထဲမှ တစ်ခု (slope layer) ကိုသာ အသုံးပြုမည်ဖြစ်ပြီး ထို layer ကို သိမ်းဆည်းမထားလိုပါ၊ ထို layer သည် နောက်ဆုံးရလာဒ်ဖြစ်သည့် TWI layer ကိုတွက်ချက်ရန်အတွက်သာ လိုအပ်သောကြောင့်ဖြစ်သည်။

   Layer များသည် နောက်ဆုံးရလာဒ်တစ်ခုမဟုတ်သောအခါ သက်ဆိုင်ရာ field များကို ဒီအတိုင်းသာ ချန်ထားခဲ့သင့်ပါသည်။ ထိုသို့မဟုတ်ပါက နောက်ပိုင်း model ကို run သောအခါပြသပေးမည့် parameter dialog ထဲတွင် layer ကိုသတ်မှတ်ပေးရန် နာမည်တစ်ခုကို ထည့်သွင်းပေးနေရပါမည်။

#. Model ထဲတွင် layer (DEM input) တစ်ခုသာရှိသောကြောင့် ပထမဆုံး dialog ထဲတွင် ရွေးချယ်ပေးရန် များစွာ မရှိပါ။ ဤဥပမာတွင် Dialog ၏ default configuration သည်မှန်ကန်သောကြောင့် :guilabel:`OK` ကိုသာနှိပ်ပါ။ Modeler canvas ထဲတွင် အောက်ပါအတိုင်းရရှိပါလိမ့်မည်။

   .. figure:: img/modeler_twi/canvas_2.png

#. Model ထဲသို့ ထည့်သွင်းရမည့် ဒုတိယ algorithm သည် catchment area algorithm ဖြစ်ပါသည်။ *Catchment area (Paralell)* ဟုခေါ်သော algorithm ကိုအသုံးပြုပါမည်။ Input အနေဖြင့် DEM layer ကိုထပ်မံအသုံးပြုမည်ဖြစ်ပြီး ထွက်ရှိလာမည့် output များသည် နောက်ဆုံးရလာဒ်မဟုတ်သေးပါ၊ ထို့ကြောင့် သက်ဆိုင်ရာ dialog ထဲတွင် အောက်ပါအတိုင်း ဖြည့်ပေးရပါမည်။

   .. figure:: img/modeler_twi/area_modeler.png

   Model သည်အောက်ပါပုံစံအတိုင်းဖြစ်သင့်ပါသည်။

   .. figure:: img/modeler_twi/canvas_3.png

#. နောက်ဆုံးအဆင့်အနေဖြင့် :guilabel:`Topographic wetness index` algorithm ကို အောက်ပါ configuration များဖြင့် ထည့်သွင်းရပါမည်။

   .. figure:: img/modeler_twi/twi_modeler.png

   ဤအဆင့်တွင် DEM ကို input အနေဖြင့် အသုံးပြုမည်မဟုတ်ပဲ slope နှင့် catchment area layer များကို input အဖြစ်အသုံးပြုမည်ဖြစ်ပါသည်။ Algorithm အသစ်များကို ထည့်သွင်းထားသောကြောင့် ၎င်းတို့မှ ထွက်လာသော output များကို အခြားသော algorithm များအတွက် အချိတ်အဆက်အဖြစ် အသုံးပြုနိုင်ပြီး workflow ကိုဖန်တီးပေးမည်ဖြစ်ပါသည်။

#. Output ``TWI`` layer သည် နောက်ဆုံးရလာဒ် layer ဖြစ်ပါသည်၊ ထို့ကြောင့် သက်ဆိုင်ရာ စာသား box ထဲတွင် output အတွက် ပြသပေးလိုသည့် နာမည်ကို ထည့်သွင်းပေးရပါမည်။

   ယခုအခါ model သည် ပြီးဆုံးပြီဖြစ်ကာ အောက်ပါပုံစံအတိုင်း ဖြစ်သင့်ပါသည်။

   .. figure:: img/modeler_twi/canvas_4.png


#. Model window ၏ အပေါ်ပိုင်းတွင် နာမည်တစ်ခုနှင့် အုပ်စုနာမည်တစ်ခုကို ထည့်ပေးပါ။

   .. figure:: img/modeler_twi/model_name.png

#. :guilabel:`Save` ခလုတ်ကိုနှိပ်၍ model ကိုသိမ်းဆည်းပါ။ ကြိုက်နှစ်သက်သည့်နေရာတွင် သိမ်းဆည်းနိုင်ပြီး နောက်ပိုင်းတွင် ပြန်ဖွင့်နိုင်ပါသည်၊ သို့သော် ၎င်းကို models folder (ဖိုင်သိမ်းဆည်းခြင်း dialog ပေါ်လာသောအခါ မြင်ရမည့် folder လမ်းကြောင်း) ထဲတွင်သိမ်းဆည်းပါက model ကို toolbox ထဲတွင်လည်း တွေ့ရမည်ဖြစ်ပါသည်။ ထို့ကြောင့် model ကို ထို folder ထဲတွင် သိမ်းဆည်းပြီး ကြိုက်နှစ်သက်ရာနာမည်ပေးပါ။

#. Modeler dialog ကိုပိတ်ပြီး toolbox ကိုဖွင့်ကြည့်ပါ။ :guilabel:`Models` ထဲတွင် သင်သိမ်းဆည်းထားသော model ကိုတွေ့ရမည်ဖြစ်ပါသည်။

   .. figure:: img/modeler_twi/toolbox.png

#. သာမာန် algorithm များကဲ့သို့ပင် model ကို click နှစ်ချက်နှိပ်ပြီး run နိုင်ပါသည်။

   .. figure:: img/modeler_twi/model_dialog.png

   မြင်တွေ့ရသည့်အတိုင်း parameter dialog တွင် model ထဲသို့ထည့်သွင်းထားသော input နှင့်အတူ နောက်ဆုံးရလာဒ်အဖြစ်သတ်မှတ်ထားသော output ပါဝင်မည်ဖြစ်သည်။ 

#. DEM ကို input အဖြစ်ထည့်သွင်းပြီး algorithm ကို run ပါက အဆင့်တစ်ဆင့်တည်းဖြင့် TWI layer ကို ရရှိမည်ဖြစ်ပါသည်။
