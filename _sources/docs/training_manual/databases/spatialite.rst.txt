သင်ခန်းစာ - QGIS ထဲတွင် SpatiaLite database များဖြင့် အလုပ်လုပ်ခြင်း (Lesson: Working with SpatiaLite databases in QGIS)
=========================================================================================================================

PostGIS ကို ယေဘုယျအားဖြင့် server တစ်ခုပေါ်တွင်အသုံးပြုပြီး spatial database လုပ်ဆောင်နိုင်စွမ်းများကို အသုံးပြုသူအများအပြားမှ တစ်ချိန်တည်းတွင်အသုံးပြုနိုင်ပါသည်၊ QGIS တွင်လည်း *SpatiaLite* ဟုခေါ်သော ဖိုင် format ကိုအသုံးပြုနိုင်ပြီး spatial database တစ်ခုလုံးကို ဖိုင်တစ်ခုတည်းထဲတွင် ပေါ့ပေါ့ပါးပါး သိမ်းဆည်းပေးနိုင်ပါသည်။ အဆိုပါ spatial database အမျိုးအစား ၂ ခုကို မတူညီသောရည်ရွယ်ချက်များအတွက် အသုံးပြုသင့်ပါသည်၊ သို့သော် အခြေခံသဘောတရားများနှင့် နည်းစနစ်များမှာ အတူတူပင်ဖြစ်ပါသည်။ Spatial database အသစ်တစ်ခုကို ဖန်တီးကြည့်မည်ဖြစ်ပြီး QGIS ထဲတွင် ထို database များဖြင့် မည်ကဲ့သို့လုပ်ကိုင်ဆောင်ရွက်နိုင်မည်ကို လေ့လာကြည့်ပါမည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** QGIS Browser interface အသုံးပြုပြီး SpatiaLite database များဖြင့်အပြန်အလှန်လုပ်ဆောင်ပုံကို လေ့လာရန်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Browser အသုံးပြု၍ SpatiaLite database တစ်ခုဖန်တီးခြင်း (Follow Along: Creating a SpatiaLite database with the Browser)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

Browser panel အသုံးပြု၍ SpatiaLite database အသစ်တစ်ခုကို ဖန်တီးပေးနိုင်ပြီး ၎င်းကို QGIS ထဲတွင်အသုံးပြုရန်အတွက် ပြင်ဆင်သတ်မှတ်ပေးနိုင်ပါသည်။

#. Browser ထဲရှိ :guilabel:`SpatiaLite` ပေါ်တွင် right click နှိပ်ပြီး :guilabel:`Create Database` ကိုရွေးချယ်ပါ။
#. ဖိုင်ကို သိမ်းဆည်းလိုသည့် ဖိုင်လမ်းကြောင်းကို သတ်မှတ်ပေးပြီး ဖိုင်ကို ``qgis-sl.db`` ဟုနာမည်ပေးပါ။
#. Browser ထဲရှိ :guilabel:`SpatiaLite` ပေါ်တွင် right click နောက်တစ်ကြိမ်နှိပ်ပြီး :guilabel:`New Connection` ကိုရွေးချယ်ပါ။ ယခင်အဆင့်က ဖန်တီးခဲ့သောဖိုင်ကို ရှာပြီးဖွင့်ပေးပါ။

ယခုအခါ database အသစ်ကို သတ်မှတ်ပြီးဖြစ်ပါသည်၊ Browser ထဲရှိ SpatiaLite တွင် ဖန်တီးထားသော database သာရှိမည်ဖြစ်ပြီး ဤအဆင့်တွင် connection ကိုဖျက်ပစ်ရုံသာ လုပ်နိုင်မည်ဖြစ်ပါသည်။ အဘယ်ကြောင့်ဆိုသော် ဤ database ထဲတွင် မည်သည့် table မျှ မထည့်သွင်းထားရသေးသောကြောင့်ဖြစ်သည်။ Database ထဲတွင် table များထည့်သွင်းကြည့်ပါမည်။

#. Layer အသစ်တစ်ခုဖန်တီးမည့် ခလုတ်ကိုရှာဖွေပြီး dropdown ကိုအသုံးပြုကာ SpatiaLite layer အသစ်တစ်ခုကို ဖန်တီးပါ၊ သို့မဟုတ် :menuselection:`Layer --> New -->` |newSpatiaLiteLayer| :menuselection:`New SpatiaLite Layer` ကိုရွေးချယ်ပါ။
#. ယခင်အဆင့်များတွင် ဖန်တီးခဲ့သော database ကို dropdown ထဲတွင် ရွေးချယ်ပါ။
#. Layer name တွင် ``places`` ဟုနာမည်ပေးပါ။
#. :guilabel:`Create an auto-incrementing primary key` တွင် အမှန်ခြစ်ပေးပါ။
#. အောက်တွင်ပြထားသည့်အတိုင်း attribute နှစ်ခုကို ထည့်သွင်းပါ။
#. Table ကိုဖန်တီးရန် :guilabel:`OK` ကိုနှိပ်ပါ။

   .. figure:: img/new_layer_setup.png
      :align: center

#. Browser ၏ထိပ်တွင်ရှိသော refresh ခလုတ်ကိုနှိပ်ပါက ``places`` table ကိုစာရင်းထဲတွင် တွေ့ရမည်ဖြစ်သည်။

   .. figure:: img/new_layer_added.png
      :align: center

   Table ပေါ်တွင် right click နှိပ်ပြီး ၎င်း၏ property များကို ကြည့်ရှုနိုင်ပါသည်။

ဤအဆင့်မှစ၍ edit ပြုလုပ်ခြင်း စတင်နိုင်ပြီး database အသစ်ထဲသို့ data များတိုက်ရိုက်ထည့်သွင်းနိုင်ပြီဖြစ်ပါသည်။

DB Manager အသုံးပြု၍ database တစ်ခုထဲသို့ data များထည့်သွင်းနည်းကိုလည်း လေ့လာခဲ့ပြီးဖြစ်ပါသည်၊ သင့် SpatiaLite DB အသစ်ထဲသို့ data များထည့်သွင်းရန် ထိုနည်းအတိုင်းလုပ်ဆောင်နိုင်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
----------------------------------------------------------------------

SpatiaLite database များဖန်တီးနည်း၊ database ထဲသို့ table များထည့်သွင်းနည်းနှင့် ထို table များကို QGIS ထဲတွင် layer များအဖြစ်အသုံးပြုနည်းများကို လေ့လာခဲ့ခြင်းဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |newSpatiaLiteLayer| image:: /static/common/mActionNewSpatiaLiteLayer.png
   :width: 1.5em
