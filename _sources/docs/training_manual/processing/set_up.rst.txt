Processing framework ပြင်ဆင်သတ်မှတ်ခြင်း (Setting-up the processing framework)
===============================================================================

Processing framework အသုံးမပြုမီ ပထမဦးဆုံး ၎င်းကို configure ပြုလုပ်ရမည်ဖြစ်သည်။ Set-up ပြုလုပ်ရန် များစွာမရှိသောကြောင့် လွယ်ကူပါသည်။ 

ရရှိနိုင်သော algorithm များကိုတိုးချဲ့အသုံးပြုနိုင်ရန် ပြင်ပ application များကို configure ပြုလုပ်နည်းကို နောက်ပိုင်းတွင်ပြသသွားမည်ဖြစ်ပါသည်၊ သို့သော် ယခုအတွက်တော့ framework အသုံးပြုခြင်းကိုသာ လေ့လာသွားမည်ဖြစ်ပါသည်။

Processing framework သည် ပင်မ QGIS plugin တစ်ခုဖြစ်ပါသည်၊ ဆိုလိုသည်မှာ QGIS တွင်အတူ ပါရှိသောကြောင့် ကွန်ပျူတာစနစ်တွင် install ပြုလုပ်ပြီးသားဖြစ်နေသင့်ပါသည်။ Processing framework သည် active ဖြစ်နေလျှင် Menu ဘားတွင် :guilabel:`Processing` ဟုခေါ်သော menu တစ်ခုတွေ့ရပါလိ့မ်မည်။ ထို menu ထဲတွင် framework အစိတ်အပိုင်းများအားလုံးကို ရရှိနိုင်ပါသည်။

.. figure:: img/set_up/menu.png

အဆိုပါ menu ကို ရှာမတွေ့လျှင် plugin manager ထဲတွင် plugin ကို ဖွင့်ပေးရမည်ဖြစ်ပြီး activate လုပ်ပေးရပါမည်။

.. figure:: img/set_up/installer.png

လုပ်ဆောင်ရမည့် အဓိကအစိတ်အပိုင်းသည် toolbox ဖြစ်ပါသည်။ သက်ဆိုင်ရာ menu entry ပေါ်တွင် click နှိပ်ပါက toolbox သည် QGIS window ၏ညာဘက်အခြမ်းတွင် ပေါ်နေသည်ကို တွေ့ရပါလိမ့်မည်။

.. figure:: img/set_up/toolbox.png


အသုံးပြုနိုင်သော algorithm များအားလုံးကို Toolbox တွင် စာရင်းပြုစုထားပြီး *Providers* ဟုခေါ်သော အုပ်စုများ ခွဲထားပါသည်။ Providers များကို :menuselection:`Settings --> Options --> Processing` ထဲတွင် activate သို့မဟုတ် deactivate ပြုလုပ်နိုင်ပါသည်။ ထို dialog အကြောင်းကို နောက်ပိုင်းတွင် ဆွေးနွေးသွားမည်ဖြစ်ပါသည်။

Default အားဖြင့် third-party application များအပေါ်မမှီခိုသော provider များ (လုပ်ဆောင်ရန် QGIS element များသာလိုအပ်သော) သာ active ဖြစ်နေပါသည်။ ပြင်ပ application များကို လိုအပ်သော algorithm များကို ထပ်ဆောင်း configuration ပြုလုပ်ပေးရန် လိုအပ်ပါသည်။ Provider များ configure ပြုလုပ်ခြင်းကို နောက်ပိုင်းရှိသင်ခန်းစာတစ်ခုထဲတွင် ရှင်းပြထားပါသည်။

ယခုအခါ geoalgorithm များကို အသုံးပြုရန် အသင့်ဖြစ်နေပြီ ဖြစ်ပါသည်။ ယခုအချိန်ထိတော့ တစ်ခုခု configure ပြုလုပ်ရန် မလိုအပ်သေးပါ။ ပထမဦးဆုံး algorithm ကို run နိုင်ပြီဖြစ်ကာ နောက်လာမည့် သင်ခန်းစာတွင် လုပ်ဆောင်သွားမည်ဖြစ်ပါသည်။

