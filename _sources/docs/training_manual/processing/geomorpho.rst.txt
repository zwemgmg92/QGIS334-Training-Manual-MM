မြေပြိုမှုများခန့်မှန်းခြင်း (Predicting landslides)
=====================================================

မော်ဂျူးကို Paolo Cavallini - `Faunalia <https://www.faunalia.eu/en>`_ မှ ပါဝင်ကူညီထားပါသည်။

.. note:: ဤသင်ခန်းစာတွင် မြေပြိုမှုများဖြစ်နိုင်ချေကို ခန့်မှန်းရန် အလွန်ရိုးရှင်းသော model တစ်ခုဖန်တီးနည်းကို လေ့လာရပါမည်။

ပထမဦးစွာ slope ကိုတွက်ချက်ပါသည် (စိတ်ဝင်စားပါက အမျိုးမျိုးသော backend များကိုရွေးချယ်ကြည့်ပြီး output များအကြား ခြားနားချက်ကို တွက်ချက်နိုင်ပါသည်)-

* :menuselection:`GRASS --> r.slope`
* :menuselection:`SAGA --> Slope, Aspect, Curvature`
* :menuselection:`GDAL Slope`

ထို့နောက် မိုးရေချိန်တိုင်းတာသောစခန်းများ၌ရှိသော မိုးရေချိန်တန်ဖိုးများဖြင့် interpolation ပြုလုပ်ထားသော ခန့်မှန်းမိုးရေချိန် model တစ်ခုကို ဖန်တီးပါသည်-

* :menuselection:`GRASS --> v.surf.rst` (resolution: 500 m)

မြေပြိုမှုဖြစ်နိုင်ချေသည် မိုးရေချိန်နှင့် slope နှစ်ခုစလုံးနှင့် အကြမ်းမျဉ်းအားဖြင့် ဆက်စပ်ပါလိမ့်မည် (တကယ့် model တွင် ပိုများသော layer များနှင့် သင့်လျော်သော parameter များကို အသုံးပြုပါလိမ့်မည်)၊ ``(rainfall * slope )/100`` ဟုဆိုကြပါစို့-

* :menuselection:`SAGA --> Raster calculator` rain ၊ slope: ``(a*b)/100``
  (သို့မဟုတ်- :menuselection:`GRASS --> r.mapcalc`)
* ထို့နောက် ခန့်မှန်းမိုးရေချိန်အများဆုံးဖြစ်သော မြူနီစီပယ်များကို တွက်ချက်ပါမည်- :menuselection:`SAGA --> Raster statistics with polygons` (စိတ်ဝင်စားသော parameter များသည် *Maximum* နှင့် *Mean* တို့ဖြစ်ပါသည်)
