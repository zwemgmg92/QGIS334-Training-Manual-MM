Interpolation နှင့် ကွန်တိုရေးဆွဲခြင်း (Interpolation and contouring)
======================================================================

မော်ဂျူးကို Paolo Cavallini - `Faunalia <https://www.faunalia.eu>`_ မှ ပါဝင်ကူညီထားပါသည်။

.. note:: ဤသင်ခန်းစာတွင် အမျိုးမျိုးသော interpolation များကိုတွက်ချက်ရန် အမျိုးမျိုးသော backend များအသုံးပြုနည်းကို လေ့လာရပါမည်။

Interpolation
---------------

Project သည် တောင်ဘက်မှ မြောက်ဘက်သို့ မိုးရေချိန်ပြောင်းလဲမှုတစ်ခုကို ပြသပါသည်။ ``points.shp`` vector ပေါ်တွင်အခြေခံပြီး ``RAIN`` parameter ဖြင့် interpolation အတွက် နည်းလမ်းအမျိုးမျိုးကိုအသုံးပြုပါမည်-

.. warning:: Analysis အားလုံးအတွက် cell size ကို :kbd:`500` ဟုသတ်မှတ်ပါ။

- :menuselection:`GRASS --> v.surf.rst`
- :menuselection:`SAGA --> Multilevel B-Spline Interpolation`
- :menuselection:`SAGA --> Inverse Distance Weighted` [Inverse distance to a power; Power: 4; Search radius: Global; Search range: all points]
- :menuselection:`GDAL --> Grid (Inverse Distance to a power)` [Power:4]
- :menuselection:`GDAL --> Grid (Moving average)` [Radius1&2: 50000]

နည်းလမ်းများအကြား ပြောင်းလဲမှုကို တိုင်းတာပြီး ၎င်းကို point များသို့အကွာအဝေးဖြင့် အပြန်အလှန်ဆက်စပ်ကြည့်ပါ-

- :menuselection:`GRASS --> r.series` [Unselect Propagate NULLs, Aggregate operation: stddev]
- :menuselection:`GRASS --> v.to.rast.value` on ``points.shp``
- :menuselection:`GDAL --> Proximity`
- :menuselection:`GRASS --> r.covar` Correlation matrix (အပြန်အလှန်ဆက်နွယ်မှုပြ မက်ထရစ်) ကိုပြသရန်၊ correlation ၏သိသာထင်ရှားမှုကိုစစ်ဆေးရန် ဥပမာ- http://vassarstats.net/rsig.html ဖြင့်။
 
ထို့ကြောင့် point များမှဝေးကွာသောဧရိယာများတွင် interpolation တိကျမှု နည်းပါလိမ့်မည်။

Contour
---------

*stddev* raster ပေါ်တွင် ကွန်တိုမျဉ်းများ [အမြဲတမ်း step=10] ကိုရေးဆွဲရန် အမျိုးမျိုးသောနည်းလမ်းများမှာ-

- :menuselection:`GRASS --> r.contour.step`
- :menuselection:`GDAL --> Contour`
- :menuselection:`SAGA --> Contour lines from grid` [**NB:** အချို့ SAGA ဗားရှင်းအဟောင်းများတွင် output shp ဖိုင်သည် ဆီလျော်မှုမရှိပါ]
