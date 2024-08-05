Vector ဂဏန်းတွက်စက် (Vector calculator)
============================================================


.. note:: ဤသင်ခန်းစာတွင် vector calculator အသုံးပြုပြီး သင်္ချာ expression တစ်ခုပေါ်အခြေခံကာ vector layer တစ်ခုထဲသို့ attribute အသစ်များထည့်သွင်းနည်းကို လေ့လာရမည်ဖြစ်ပါသည်။

သင်္ချာ expression များဖြင့် raster layer များကိုဖန်တီးရန် raster calculator အသုံးပြုနည်းကို သိရှိခဲ့ပြီးဖြစ်ပါသည်။ Vector layer များအတွက်လည်း ဆင်တူသော algorithm တစ်ခုရှိပါသည်၊ ထို algorithm သည် input layer ၏ attribute များအပြင် expression ရလာဒ်အတွက် attribute တစ်ခု ပါဝင်သော layer အသစ်တစ်ခုကို ထုတ်ပေးပါသည်။ Algorithm ကို *Field calculator* ဟုခေါ်ဆိုပြီး အောက်ပါ parameter များပါဝင်ပါသည်။

.. figure:: img/vector_calculator/field_calculator.png

.. note:: ဗားရှင်းအသစ်များတွင် interface ပြောင်းလဲသွားပြီး ပိုမိုအသုံးရလွယ်ကူစေပါသည်။

*Field calculator* algorithm အသုံးပြုခြင်း ဥပမာအချို့ကို အောက်တွင်ဖော်ပြထားပါသည်။

ပထမဦးစွာ polygon တစ်ခုချင်းစီ၌ရှိသော လူဖြူများ၏ population density (လူဦးရေသိပ်သည်းမှု) ကိုတွက်ချက်ကြည့်ပါမည်။ Attribute ဇယားထဲတွင် field နှစ်ခုပါရှိပြီး ``WHITE`` နှင့် ``SHAPE_AREA`` ဟုအမည်ပေးထားပါသည်။ ထိုနှစ်ခုကို စား (divide) ပြီး တစ်သန်း ဖြင့်မြှောက် (multiply) ပေးရမည်ဖြစ်သည် (၁ စတုရန်းကီလိုမီတာရှိ သိပ်သည်းမှုကိုရရှိရန်)၊ ထို့ကြောင့် အောက်ပါ formula ကိုအသုံးပြုနိုင်ပါသည်

::

	( "WHITE" / "SHAPE_AREA" ) * 1000000

Parameter dialog တွင် အောက်ဖော်ပြပါအတိုင်း ဖြည့်သွင်းပါ။

.. figure:: img/vector_calculator/density.png

``WHITE_DENS`` ဟုအမည်ရှိသော field အသစ်တစ်ခုကို ထုတ်ပေးပါလိမ့်မည်။

ယခုအခါ ``MALES`` နှင့် ``FEMALES`` field နှစ်ခုကြားရှိ အချိုး ကိုတွက်ချက်မည်ဖြစ်ပြီး male (အမျိုးသား) လူဦးရေသည် အရေအတွက်အားဖြင့် female (အမျိုးသမီး) လူဦးရေ အပေါ်လွှမ်းမိုးမှုရှိ/မရှိကို ဖော်ပြပေးသည့် field အသစ်တစ်ခုကို ဖန်တီးမည်ဖြစ်ပါသည်။

အောက်ပါ formula ကိုထည့်သွင်းပါ

::

	"MALES" / "FEMALES" 


*OK* ခလုတ်ကိုမနှိပ်မီတွင် parameter window သည် အောက်ပါပုံစံအတိုင်းဖြစ်နေသင့်ပါသည်။

.. figure:: img/vector_calculator/ratio.png


အစောပိုင်းဗားရှင်းများတွင် field နှစ်ခုစလုံးသည် integer (ကိန်းပြည့်) အမျိုးအစားများဖြစ်သောကြောင့် ရလာဒ်သည် integer ဖြစ်ပါလိမ့်မည်။ ဤဥပမာတွင် ရလာဒ်ကို floating point number (ဒဿမကိန်းဂဏန်း) ဖြင့် ဖော်ပြလိုသော်ကြောင့် foumula သည် ``1.0 *  "MALES"  /  "FEMALES"`` ဖြစ်သင့်ပါသည်။

အချိုး (ratio) တန်ဖိုးအစား ``male`` သို့မဟုတ် ``female`` စာသားများပါဝင်သော field အသစ်တစ်ခုရရှိရန် conditional function များကိုအသုံးပြုနိုင်ပါသည်၊ အောက်ပါ formula ကိုအသုံးပြုနိုင်ပါသည်::

	CASE WHEN  "MALES" > "FEMALES"  THEN 'male' ELSE 'female' END

Parameter window သည် အောက်ပါပုံစံအတိုင်း ဖြစ်သင့်ပါသည်။

.. figure:: img/vector_calculator/predominance.png

*Advanced Python field calculator* ထဲတွင် python field calculator တစ်ခုပါရှိပြီး ဒီသင်ခန်းစာတွင် အသေးစိတ်ရှင်းပြထားခြင်းမရှိပါ။

.. figure:: img/vector_calculator/advanced.png
