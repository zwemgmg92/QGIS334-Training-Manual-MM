အခြားပရိုဂရမ်များ (Other programs)
===================================

မော်ဂျူးကို Paolo Cavallini - `Faunalia <https://www.faunalia.eu>`_ မှ ပါဝင်ကူညီထားပါသည်။

.. note:: ဤသင်ခန်းစာတွင် အတွင်းပိုင်း Processing မှ အခြားထပ်ဆောင်းပရိုဂရမ်များကို မည်သို့အသုံးပြုရမည်ကို ပြသပေးမည်ဖြစ်ပါသည်။ သင့်တော်သော package များကို install ပြုလုပ်ထားရပါမည်။

GRASS
------

GRASS_ သည် geospatial data စီမံခန့်ခွဲမှုနှင့် analysis ၊ image processing ၊ ဂရပ်ဖစ်များနှင့် မြေပုံထုတ်လုပ်ခြင်း၊ spatial modeling ၊ နှင့် ပုံဖော်ပြသခြင်းတို့အတွက် အခမဲ့အသုံးပြုနိုင်သော GIS software suite တစ်ခုဖြစ်ပါသည်။ 

Windows များတွင် OSGeo4W standalone installer (32 and 64 bit) မှတဆင့် default အနေဖြင့် GRASS ကို install ပြုလုပ်ပေးပါသည်၊ ၎င်းတွင် အဓိက Linux distribution များအားလုံးအတွက် ပါဝင်ပါသည်။

R
--

R_ သည် စာရင်းအင်းအချက်အလက်ဆိုင်ရာတွက်ချက်ခြင်းနှင့် ဂရပ်ဖစ်များအတွက် အခမဲ့အသုံးပြုနိုင်သော software environment တစ်ခုဖြစ်ပါသည်။

လိုအပ်သော library (**LIST**) အနည်းငယ်နှင့်အတူ R ကို သီးခြား install ပြုလုပ်ပေးရပါမည်။ QGIS ထဲတွင် R ကိုအသုံးပြုနိုင်စေရန် *Processing R Provider* plugin ကိုလည်း install ပြုလုပ်ပေးရပါမည်။

Processing implementation ၏ အဓိကအချက်သည် ရိုးရှင်းသော သို့မဟုတ် ရှုပ်ထွေးသော သင့်ကိုယ်ပိုင် script များကိုထည့်သွင်းပေးနိုင်ပြီး ၎င်းတို့ကို အခြားသောမော်ဂျူးတစ်ခုခုအဖြစ် အသုံးပြုနိုင်ခြင်းဖြစ်ပါသည်။

R_ ကို install ပြုလုပ်ထားပြီးသားဖြစ်ပါက (Processing ၏ General configuration မှ R မော်ဂျူးကို activate လုပ်ရန် မမေ့ပါနှင့်) ကြိုပေးထားသော ဥပမာအချို့ကို စမ်းသပ်ကြည့်ပါ။

အခြားသောအရာများ (Others)
-------------------------

LASTools_  သည် LiDAR data များကို process လုပ်ရန်နှင့် ဆန်းစစ်လေ့လာရန် အခမဲ့ နှင့် စီးပွားဖြစ် command များကို ရောထားသောအစုတစ်ခုဖြစ်ပါသည်။ Operating system အမျိုးမျိုးပေါ်မူတည်ပြီး ရရှိနိုင်မှု ကွဲပြားပါသည်။

ထပ်ဆောင်း plugin များမှတဆင့် နောက်ထပ် tool များအသုံးပြုနိုင်ပါသည်၊ ဥပမာ-

* LecoS_:  မြေယာဖုံးလွှမ်းမှု စာရင်းအင်းအချက်အလက်များနှင့် တောတောင်ရေမြေ ဂေဟဗေဒ အတွက် suite တစ်ခုဖြစ်ပါသည်။
* lwgeom_: PostGIS ၏အစိတ်အပိုင်းဟောင်းဖြစ်ပြီး၊ ဤ library တွင် ဂျီဩမေတြီ သန့်စင်ခြင်းအတွက် အသုံးဝင်သော tool အချို့ပါဝင်ပါသည်။
* Animove_: တိရစ္ဆာန်များ၏ နေထိုင်ရာ အကွာအဝေးအပိုင်းအခြားကို ဆန်းစစ်လေ့လာရန် tool များဖြစ်ပါသည်။

နောက်ထပ် tool များလာပါဦးမည်။

Backends များအကြား နှိုင်းယှဉ်ချက် (Comparison among backends)
---------------------------------------------------------------

ကြားခံဇုန်များနှင့် အကွာအဝေးများ (Buffers and distances)
.........................................................

``points.shp`` ကိုထည့်သွင်းပြီး Toolbox ၏ filter ထဲတွင် ``buf`` ဟုရိုက်ပြီး ၎င်းပေါ်တွင် click နှစ်ချက်နှိပ်ပါ-

- :menuselection:`Fixed distance buffer`: Distance 10000
- :menuselection:`Variable distance buffer`: Distance field SIZE
- :menuselection:`v.buffer.distance`: distance 10000
- :menuselection:`v.buffer.column`: bufcolumn SIZE
- :menuselection:`Shapes Buffer`: ပုံသေတန်ဖိုး 10000 (dissolve လုပ်ခြင်းနှင့် dissolve မလုပ်ခြင်း)၊ attribute field (scaling ဖြင့်)

လုပ်ဆောင်မှုမြန်နှုန်း မည်မျှကွာခြားသည်ကို ကြည့်ပါ၊ မတူညီသော option များလည်းရရှိနိုင်ပါသည်။

**ဖတ်ရှုသူများအတွက် လေ့ကျင့်ခန်း** - မတူညီသော နည်းလမ်းများအကြား ဂျီဩမေတြီ output များထဲရှိ ကွာခြားချက်ကိုရှာပါ။

ယခုအခါ raster buffer များနှင့် အကွာအဝေးများဖြစ်ပါသည်-

- ဦးစွာ ``rivers.shp`` vector ကို ထည့်သွင်းပြီး :menuselection:`GRASS --> v.to.rast.value` ဖြင့် vector ကို raster အဖြစ်သို့ပြောင်းလဲပါ၊ **သတိထားရန်**- cell size ကို 100 မီတာ သတ်မှတ်ထားရပါမည်၊ ထိုသို့မဟုတ်ပါက တွက်ချက်ချိန်များစွာ ကြာမြင့်ပါလိမ့်မည်၊ ရလာဒ်မြေပုံတွင် 1 နှင့် NULLs တန်ဖိုးများရှိပါလိမ့်မည်။
- :menuselection:`SAGA --> Shapes to Grid --> COUNT` အသုံးပြုပြီး ထိုအတိုင်း လုပ်ဆောင်ပါ (ရလာဒ်မြေပုံ- 6 မှ 60 အထိ)
- ထို့နောက် :menuselection:`proximity` (GRASS အတွက် value=1 ၊ SAGA အတွက် rivers ID list) ကိုလုပ်ဆောင်ပါ၊ :menuselection:`r.buffer` ကို 1000 ၊ 2000 ၊ 3000 parameter များဖြင့်လုပ်ဆောင်ပါ၊ :menuselection:`r.grow.distance` (မြေပုံနှစ်ခုမှ ပထမမြေပုံ၊ SAGA raster တွင်လုပ်ဆောင်ပါက ဒုတိယမြေပုံသည် river တစ်ခုချင်းစီနှင့်သက်ဆိုင်သော ဧရီယာများကိုပြသပါလိမ့်မည်) ကိုလုပ်ဆောင်ပါ။

Dissolve
..........

ဘုံဖြစ်သော Attribute တစ်ခုပေါ်အခြေခံ၍ feature များကို ပေါင်းစပ်ပေးပါသည်- 

- :menuselection:`GRASS --> v.dissolve` ``municipalities.shp`` on PROVINCIA
- :menuselection:`QGIS --> Dissolve` ``municipalities.shp`` on PROVINCIA
- :menuselection:`OGR --> Dissolve` ``municipalities.shp`` on PROVINCIA
- :menuselection:`SAGA --> Polygon Dissolve` ``municipalities.shp`` on PROVINCIA (**NB:** `Keep inner boundaries` ကို select မလုပ်ထားရပါ)

.. note:: နောက်ဆုံးတစ်ခုသည် SAGA <=2.10 နှင့်အောက် ဗားရှင်းများတွင် ပျက်နေပါသည်။

**ဖတ်ရှုသူများအတွက် လေ့ကျင့်ခန်း** - မတူညီသောနည်းလမ်းများအကြား ကွာခြားချက် (ဂျီဩမေတြီနှင့် attribute များ) ကိုရှာပါ။

.. _GRASS: https://grass.osgeo.org/
.. _R: https://www.r-project.org/
.. _LASTools: https://rapidlasso.com/lastools/
.. _LecoS: https://conservationecology.wordpress.com/qgis-plugins-and-scripts/lecos-land-cover-statistics/
.. _lwgeom: https://plugins.qgis.org/plugins/processinglwgeomprovider/
.. _Animove: https://www.faunalia.eu/en/dev/animove
