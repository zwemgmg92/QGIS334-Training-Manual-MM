Model တစ်ခုဖန်တီးရန်အတွက် modeler ထဲတွင်သာရှိသော tool များအသုံးပြုခြင်း (Using modeler-only tools for creating a model)
========================================================================================================================

.. note:: ဤသင်ခန်းစာတွင် model များ၌ ထပ်ဆောင်းလုပ်ဆောင်မှုများပြုလုပ်နိုင်ရန် modeler ထဲတွင်သာရရှိနိုင်သော algorithm အချို့အသုံးပြုပုံကို လေ့လာရမည်ဖြစ်ပါသည်။

ဤသင်ခန်းစာ၏ရည်ရွယ်ချက်မှာ လက်ရှိ selection ကိုအသုံးပြုသည့် interpolation algorithm တစ်ခုကို ဖန်တီးရန် modeler ကိုအသုံးပြုခြင်းဖြစ်ပါသည်။ Interpolate (သွယ်ဝိုက်တွက်ချက်ခြင်း) ပြုလုပ်ထားသော raster layer ကိုဖန်တီးရာတွင် select ပြုလုပ်ထားသော feature များကိုသာမက အဆိုပါ selection ၏ extent ကိုပါ အသုံးပြုမည်ဖြစ်သည်။

Interpolation လုပ်ငန်းစဉ်တွင် အဆင့် ၂ ဆင့်ပါဝင်ပါသည်၊ ယခင်သင်ခန်းစာများတွင် ရှင်းပြခဲ့သည့်အတိုင်း point layer ကို raster အဖြစ်သို့ပြောင်းလဲခြင်းနှင့် ထို raster ပြောင်းလဲထားသော layer ထဲရှိ no-data တန်ဖိုးများကို ဖြည့်ပေးခြင်း တို့ဖြစ်ပါသည်။ Point layer ထဲတွင် selection ပြုလုပ်ထားလျှင် select ပြုလုပ်ထားသော point များကိုသာ အသုံးပြုမည်ဖြစ်ပါသည်၊ သို့သော် output ၏ extent ကို အလိုအလျောက် ချိန်ညှိရန် သတ်မှတ်ပါက layer ၏ extent အပြည့် ကိုအသုံးပြုပါလိမ့်မည်။ ဆိုလိုသည်မှာ Layer ၏ extent ကို feature များအားလုံး၏ extent အပြည့်အဖြစ် အမြဲတမ်းမှတ်ယူမည်ဖြစ်ပြီး select ပြုလုပ်ထားသော feature များ၏ extent ကိုသာ အသုံးပြုမည်မဟုတ်ပါ။ Model ထဲတွင် tool အချို့အသုံးပြုပြီး ထိုအရာကို ပြင်ဆင်ကြည့်ပါမည်။

Modeler ကိုဖွင့်ပြီး လိုအပ်သော input များထည့်သွင်းပြီး model ကိုစတင်ပါ။ ထို model တွင် vector layer (point များသာ) တစ်ခုနှင့် raster ပြောင်းလဲရန်အတွက်အသုံးပြုမည့်တန်ဖိုးများပါရှိသော ထို layer မှ attribute တစ်ခုလိုအပ်ပါသည်။

.. figure:: img/modeler_only/inputs.png

နောက်တစ်ဆင့်အနေဖြင့် select ပြုလုပ်ထားသော feature များ၏ extent ကိုတွက်ချက်ရန်ဖြစ်ပါသည်။ ထိုသို့တွက်ချက်ရန် *Vector layer bounds* ဟုခေါ်သော model-only tool ကိုအသုံးပြုနိုင်ပါသည်။ ပထမဦးစွာ select ပြုလုပ်ထားသော feature များ၏ extent ပါရှိသော layer တစ်ခုကို ဖန်တီးရပါမည်။ ထို့နောက် tool ထဲတွင် ထို layer ကိုထည့်သုံးနိုင်မည်ဖြစ်ပါသည်။

Select ပြုလုပ်ထားသော feature များ၏ extent ပါရှိသော layer တစ်ခုကို ဖန်တီးရန် လွယ်ကူသောနည်းလမ်းသည် input point layer ၏ convex hull တစ်ခုကိုတွက်ချက်ရန်ဖြစ်ပါသည်။ Convex hull တွင် selection နှင့်တူညီသော bounding box (အတိုင်းအတာနယ်နိမိတ်) ရှိစေရန် select ပြုလုပ်ထားသော point ကိုသာ အသုံးပြုပါလိမ့်မည်။ ထို့နောက် *Vector layer bounds* algorithm ကိုထည့်သွင်းပြီး convex hull layer ကို input အဖြစ်အသုံးပြုပါ။ Modeler canvas ထဲတွင် အောက်ပါပုံစံအတိုင်း ဖြစ်သင့်ပါသည်-

.. figure:: img/modeler_only/convexhull_and_extent.png

*Vector layer bounds* မှရလာဒ်သည် ကိန်းဂဏန်းတန်ဖိုး ၄ ခုပါဝင်သောအစုတစ်ခုနှင့် extent object တစ်ခုဖြစ်ပါသည်။ ဤလေ့ကျင့်ခန်းအတွက် ကိန်းဂဏန်းရလာဒ်များနှင့် extent နှစ်ခုစလုံးကို အသုံးပြုပါမည်။

.. figure:: img/modeler_only/extent_outputs.png

ယခုအခါ vector layer ကို raster အဖြစ်သို့ပြောင်းလဲပေးမည့် algorithm ကိုထည့်သွင်းကာ *Vector layer bounds* algorithm မှ extent ကို input အနေဖြင့် အသုံးပြုပါမည်။

Algorithm ၏ parameter များတွင် အောက်ပါအတိုင်း ဖြည့်သွင်းပါ-

.. figure:: img/modeler_only/rasterize.png

ယခုအခါ canvas ထဲတွင် အောက်ပါပုံစံအတိုင်း ဖြစ်သင့်ပါသည်။

.. figure:: img/modeler_only/canvas_rasterize.png

နောက်ဆုံးအဆင့်အနေဖြင့် *Close gaps* algorithm အသုံးပြုပြီး raster layer ၏ no-data တန်ဖိုးများကို ဖြည့်ပါမည်။

.. figure:: img/modeler_only/close_gaps.png

Algorithm ကို သိမ်းဆည်းပြီး toolbox ထဲသို့ ထည့်သွင်းနိုင်ပြီဖြစ်ပါသည်။ Algorithm ကို run နိုင်ပြီဖြစ်ပြီး input layer ထဲရှိ select ပြုလုပ်ထားသော point များမှ interpolate ပြုလုပ်ထားသည့် raster layer တစ်ခုကိုထုတ်ပေးပါလိမ့်မည်၊ layer ၏ extent သည် select ပြုလုပ်ထားသည့် extent အတိုင်းအတူတူဖြစ်နေပါလိမ့်မည်။

Algorithm ကို အဆင့်မြှင့်သည့်အနေဖြင့် raster ပြောင်းလဲသောအခါ cellsize အတွက် တန်ဖိုးတစ်ခုကို အသုံးပြုထားပါသည်။ ထိုတန်ဖိုးသည် ယခုစမ်းသပ်သော input layer အတွက်ကောင်းမွန်သော်လည်း အခြားသောကိစ္စများအတွက် ကောင်းမွန်ချင်မှ ကောင်းမွန်ပါလိမ့်မည်။ အသုံးပြုသူမှ အလိုရှိသော တန်ဖိုးကို ထည့်သွင်းနိုင်ရန်အတွက် parameter အသစ်တစ်ခုကို ထည့်သွင်းပေးနိုင်ပါသည်၊ သို့သော် တန်ဖိုးကို အလိုအလျောက်တွက်ချက်ခြင်းသည် ပိုမိုကောင်းမွန်ပါသည်။

Modeler-only calculator ကိုအသုံးပြုနိုင်ပြီး extent ကိုဩဒိနိတ်မှ တန်ဖိုးကို တွက်ချက်ပေးနိုင်ပါသည်။ ဥပမာအားဖြင့် ပုံသေအကျယ် 100 pixel ရှိသော layer တစ်ခုကို ဖန်တီးရန် အောက်ပါ formula ကို calculator ထဲတွင် ထည့်သွင်းအသုံးပြုနိုင်ပါသည်။

.. figure:: img/modeler_only/calculator.png

ယခုအခါ ပုံသေတန်ဖိုးအစား calculator မှထွက်လာသော output ကိုအသုံးပြုနိုင်စေရန်အတွက် rasterize algorithm ကို edit ပြုလုပ်ရပါမည်။ 

နောက်ဆုံး algorithm သည် အောက်ပါပုံစံအတိုင်းဖြစ်သင့်ပါသည်-

.. figure:: img/modeler_only/final.png
