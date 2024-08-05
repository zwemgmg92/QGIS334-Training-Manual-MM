********************************************************************************************************
မော်ဂျူး - PostGIS ဖြင့် Spatial Database သဘောတရားများ (Module: Spatial Database Concepts with PostGIS)
********************************************************************************************************

Spatial Database များသည် database တစ်ခုအတွင်း record များ၏ဂျီဩမေတြီများကို သိမ်းဆည်းစေနိုင်ပြီး အဆိုပါ ဂျီဩမေတြီများအသုံးပြု၍ record များကို query လုပ်ခြင်းနှင့် ရယူခြင်းများကို ဆောင်ရွက်နိုင်ပါသည်။ ဤမော်ဂျူးတွင် PostgreSQL ၏တိုးချဲ့မှုတစ်ခုဖြစ်သော PostGIS ကိုအသုံးပြုမည်ဖြစ်ပြီး spatial database တစ်ခု setup လုပ်ခြင်း၊ database ထဲသို့ data များ ထည့်သွင်းခြင်းနှင့် PostGIS တွင်လုပ်ဆောင်နိုင်သော geographic function များကိုအသုံးပြုခြင်းများကို လေ့လာမည်ဖြစ်ပါသည်။

ဤအပိုင်းတွင် အလုပ်လုပ်ဆောင်နေစဉ်အတွင်း `Boston GIS အသုံးပြုသူအုပ်စု <https://www.bostongis.com/postgis_quickguide.bqg>`_ တွင်ရှိသော **PostGIS
cheat sheet** ကော်ပီတစ်ခုကို သိမ်းထားနိုင်ပါသည်။ အခြား အသုံးဝင်သော အရင်းအမြစ်သည် `online <https://postgis.net/documentation/>`_  PostGIS documentation ဖြစ်ပါသည်။

Boundless မှ ဖန်တီးထားသော PostGIS နှင့် Spatial Databases နှင့်ပတ်သက်သည့် ပိုမိုကျယ်ပြန့်သော tutorial များကိုလည်း PostGIS ဝက်ဘ်ဆိုဒ်ပေါ်တွင် တွေ့ရနိုင်ပါသည်-

* `Introduction to PostGIS <https://postgis.net/workshops/postgis-intro/>`_
* `PostGIS Database Tips and Tricks
  <https://postgis.net/documentation/tips/>`_

`PostGIS In Action <https://www.postgis.us>`_ တွင်လည်း ကြည့်ရှုပါ။

.. toctree::
   :maxdepth: 2

   spatial_functions
   simple_feature_model
   import_export
   spatial_queries
   geometry
