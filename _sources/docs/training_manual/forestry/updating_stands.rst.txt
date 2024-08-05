သင်ခန်းစာ - Forest Stand များကို Update ပြုလုပ်ခြင်း (Lesson: Updating Forest Stands)
======================================================================================

Inventory မြေပုံအဟောင်းများမှ အချက်အလက်များကို digitize ပြုလုပ်ပြီးဖြစ်ကာ forest stand များတွင် သက်ဆိုင်ရာ အချက်အလက်များ ထည့်သွင်းပြီးဖြစ်ပါသည်။ နောက်တစ်ဆင့်အနေဖြင့် လက်ရှိသစ်တောအခြေအနေ inventory ကိုဖန်တီးရန်ဖြစ်ပါသည်။

Forest stand အသစ်များကို ကောင်းကင်ဓာတ်ပုံတစ်ခုကိုအသုံးပြုပြီး digitize ပြုလုပ်ပါမည်။ ယခင်သင်ခန်းစာအတိုင်းပင် Color Infrared (CIR) ကောင်းကင်ဓာတ်ပုံတစ်ခုကို အသုံးပြုပါမည်။ ဤဓာတ်ပုံအမျိုးအစားသည် အပြာရောင် (blue) light အစား အနီအောက် (infrared) light ကိုဖမ်းယူခြင်းဖြစ်ပြီး အပင်ဧရိယာများကို လေ့လာရာတွင် ကျယ်ပြန့်စွာအသုံးပြုပါသည်။

Forest stand များကို digitize ပြုလုပ်ပြီးသောအခါ ထိန်းသိမ်းရေးစည်းမျဉ်းများအရ ကန့်သတ်ချက်အသစ်များကဲ့သို့သော အချက်အလက်များကို ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** CIR ကောင်းကင်ဓာတ်ပုံမှ forest stand အသစ်များကို digitize ပြုလုပ်ရန်နှင့် အခြား dataset များမှ အချက်အလက်များထည့်သွင်းရန်။


:abbr:`★☆☆ (Basic level)` Forest Stand အဟောင်းများနှင့် လက်ရှိ ကောင်းကင်ဓာတ်ပုံကို နှိုင်းယှဉ်ခြင်း (Comparing the Old Forest Stands to Current Aerial Photographs)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

National Land Survey of Finland တွင် ကောင်းကင်ဓာတ်ပုံများ၊ သမားရိုးကျမြေမျက်နှာသွင်ပြင်မြေပုံများ၊ DEM ၊ LiDAR data အစရှိသည့် ပထဝီဝင်ဆိုင်ရာ data များကို ဒေါင်းလုဒ်ပြုလုပ်ခွင့်ပေးထားပါသည်။ ဝန်ဆောင်မှုကို `ဤတွင် <https://tiedostopalvelu.maanmittauslaitos.fi/tp/kartta?lang=en>`_ အင်္ဂလိပ်ဘာသာဖြင့် ရရှိနိုင်ပါသည်။ ဤလေ့ကျင့်ခန်းတွင် အသုံးပြုသော ကောင်းကင်ဓာတ်ပုံကို ထိုဝန်ဆောင်မှုမှ ဒေါင်းလုဒ်ရယူထားသော orthorectified CIR ဓာတ်ပုံနှစ်ချပ် (M4134F_21062012 နှင့် M4143E_21062012) မှ ဖန်တီးထားပါသည်။

#. QGIS ကိုဖွင့်ပြီး :menuselection:`Project --> Properties... --> CRS` ထဲတွင် project ၏ CRS ကို :guilabel:`ETRS89 / ETRS-TM35FIN` ဟုသတ်မှတ်ပါ
#. :file:`rautjarvi_aerial.tif` ဟူသည့် CIR ဓာတ်ပုံကို project ထဲသို့ ထည့်သွင်းပါ-

   #. File manager browser မှတဆင့် :file:`exercise_data\\forestry\\` folder သို့သွားပါ
   #. :file:`rautjarvi_aerial.tif` ဖိုင်ကို project ထဲသို့ click နှိပ်ဖိဆွဲကာ ထည့်သွင်းပါ
#. QGIS project ကို :file:`digitizing_2012.qgs` အနေဖြင့် သိမ်းဆည်းပါ 

CIR ဓာတ်ပုံများသည် 2012 မှဓာတ်ပုံများဖြစ်ပါသည်။ 1994 ခုနှစ်တွင် ဖန်တီးခဲ့သော stand များနှင့် နှစ် ၂၀ နီးပါးကြာပြီးနောက် stand အခြေအနေများကို နှိုင်းယှဉ်ကြည့်နိုင်ပါသည်။

#. ယခင်သင်ခန်းစာတွင် ဖန်တီးခဲ့သော :file:`forest_stands_1994.shp` layer ကိုထည့်သွင်းပါ-

   #. File manager browser မှတဆင့် :file:`exercise_data\\forestry\\` folder သို့သွားပါ
   #. :file:`forest_stands_1994.shp` ဖိုင်ကို project ထဲသို့ click နှိပ်ဖိဆွဲကာ ထည့်သွင်းပါ
#. Polygon များကို ဖြတ်ပြီး မြင်နိုင်စေရန်အတွက် Layer အတွက် သင်္ကေတကိုသတ်မှတ်ပါ-

   #. :guilabel:`forest_stands_1994` တွင် right-click နှိပ်ပါ
   #. :guilabel:`Properties` ကိုရွေးချယ်ပါ
   #. |symbology| :guilabel:`Symbology` tab သို့သွားပါ
   #. :guilabel:`Fill color` တွင် transparent fill ဟုသတ်မှတ်ပါ
   #. :guilabel:`Stroke color` တွင် purple (ခရမ်းရောင်) သတ်မှတ်ပါ
   #. :guilabel:`Stroke width` တွင် ``0.50 mm`` ဟုသတ်မှတ်ပါ
#. Forest stand အဟောင်းများသည် သင်အမြင်အရ အဓိပ္ပါယ်ကောက်ယူထားသော တစ်မျိုးတည်းဖြစ်သည့် (homogeneous) forest အတိုင်း ဟုတ်မဟုတ်ကို စစ်ဆေးသုံးသပ်ပါ။
#. ဧရိယာပတ်လည်ကို zoom အချုံ့/အချဲ့နှင့် မြင်ကွင်းရွှေ့ခြင်းများ လုပ်ဆောင်ပါ။ အချို့ forest stand အဟောင်းများသည် ဓာတ်ပုံနှင့် ကိုက်ညီနေသေးပြီး အခြားအရာများသည် မကိုက်ညီတော့သည်ကို သတိပြုမိပါလိမ့်မည်။

   ၎င်းသည် သာမန်အခြေအနေတစ်ခုဖြစ်ပါသည်၊ အကြောင်းမှာ နှစ်ပေါင်း ၂၀ ခန့်ကြာမြင့်သွားပြီဖြစ်ပြီး အမျိုးမျိုးသော သစ်တောလုပ်ငန်းများ (သစ်ထုတ်ခြင်း၊ ပင်ကျပ်နှုတ်ခြင်း၊...) ကို လုပ်ဆောင်ထားသောကြောင့်ဖြစ်သည်။ 1992 ခုနှစ်တွင် digitize ပြုလုပ်ခဲ့သူသည် Forest stand များကို homogeneous အဖြစ်မြင်တွေ့ခဲ့ရပြီး အချိန်ကြာလာသည်နှင့် အချို့သစ်တောများသည် နည်းလမ်းအမျိုးမျိုးဖြင့် တိုးတက်လာသည်လည်း ဖြစ်နိုင်ပါသည်။ ထိုအချိန်က forest inventory ဦးစားပေးမှုများသည် ယနေ့ခေတ်နှင့် ကွဲပြားခဲ့သောကြောင့်လည်း ဖြစ်နိုင်ပါသည်။

နောက်တစ်ဆင့်အနေဖြင့် forest stand အဟောင်းများကိုအသုံးမပြုပဲ ဤဓာတ်ပုံအတွက် forest stand အသစ်များကိုဖန်တီးပါမည်။ နောက်ပိုင်းတွင် ၎င်းတို့အကြား ကွာခြားမှုကို နှိုင်းယှဉ်နိုင်ပါသည်။


:abbr:`★☆☆ (Basic level)` CIR ဓာတ်ပုံကို အဓိပ္ပါယ်ကောက်ယူခြင်း (Interpreting the CIR Image)
--------------------------------------------------------------------------------------------

Inventory အဟောင်းလုပ်ခဲ့သော ဧရိယာကိုပင် digitize ပြုလုပ်ပါမည်၊ road များနှင့် lake ကြားထဲရှိ ဧရိယာဖြစ်ပါသည်။ ဧရိယာတစ်ခုလုံးကို digitize ပြုလုပ်ရန်မလိုပါ၊ ယခင်လေ့ကျင့်ခန်းရှိ forest stand အများစု ပါရှိပြီးသားဖြစ်သော vector ဖိုင်ဖြင့် စတင်လုပ်ဆောင်နိုင်ပါသည်။

#. |polygonLayer| :guilabel:`forest_stands_1994` layer ကိုဖယ်ရှားပါ
#. :file:`exercise_data\\forestry\\forest_stands_2012.shp` ဖိုင်အား project ထဲသို့ထည့်သွင်းပါ
#. Polygon များတွင် အဖြည့်အရောင်များမရှိစေပဲ border မျဉ်းများကို မြင်ရနိုင်စေရန်အတွက် layer ၏ style ကိုသတ်မှတ်ပါ

   #. ``forest_stands_2012`` layer ၏ :guilabel:`Properties` dialog ကိုဖွင့်ပါ
   #. |symbology| :guilabel:`Symbology` tab သို့သွားပါ
   #. :guilabel:`Fill color` တွင် transparent fill သတ်မှတ်ပါ
   #. :guilabel:`Stroke color` တွင် green သတ်မှတ်ပါ
   #. :guilabel:`Stroke width` တွင် ``0.50 mm`` ဟုသတ်မှတ်ပါ

   .. figure:: img/stands_2012_1.png
      :align: center

   |

Inventory ဧရိယာ၏ မြောက်ဘက်အပိုင်းတွင် forest stand များမရှိသေးသည်ကို မြင်ရနိုင်ပါသည်။ လုပ်ဆောင်ရမည်မှာ ထို မရှိသေးသော forest stand များကို digitize ပြုလုပ်ရန်ဖြစ်သည်။

မစတင်မီတွင် digitize ပြုလုပ်ထားပြီးသော forest stand များနှင့် ဓာတ်ပုံထဲရှိ သက်ဆိုင်ရာ forest များကို အချိန်ပေးပြီး ကြည့်ရှုစစ်ဆေးပါ။ Forest stand border များကို မည်သို့ဆုံးဖြတ်သည်နှင့်ပတ်သက်ပြီး မြင်အောင် ကြိုးစားကြည့်ပါ၊ သင့်တွင် သစ်တောနှင့်ဆိုင်သောဗဟုသုတအချို့ရှိလျှင် အထောက်အကူဖြစ်ပါသည်။

ထည့်သွင်းစဉ်းစားရမည့်အချို့အချက်များ-

* မည်သည့်သစ်တောများတွင် ရွက်ကြွေ (deciduous) မျိုးစိတ်များ (Finland တွင် အများစုသည် birch forest များဖြစ်ကြသည်) ရှိသလဲနှင့် မည်သည့်သစ်တောများတွင် ထင်းရှူး (conifer) မျိုးစိတ်များရှိသလဲ (ဤဧရိယာတွင် pine သို့မဟုတ် spruce များရှိကြသည်)။ CIR ဓာတ်ပုံများထဲတွင် deciduous မျိုးစိတ်များကို အနီရောင်တောက်တောက် အနေဖြင့် ပြသလေ့ရှိပြီး conifer များကို အစိမ်းရင့်ရောင် အနေဖြင့် ပြသလေ့ရှိပါသည်။
* သစ်တောသည် မည်မျှသက်တမ်းရှိပြီလဲ။ ဓာတ်ပုံထဲတွင် အပင်ရွက်အုပ်များ၏ အရွယ်အစားကို ဖော်ထုတ်နိုင်ပါသည်။
* အမျိုးမျိုးသော forest stand များသည် မည်မျှ သိပ်သည်းနေပါသလဲ။ မကြာသေးမီက thinning (ပင်ကျပ်နှုတ်ခြင်း) လုပ်ထားသော forest stand တစ်ခုတွင် အပင်ရွက်အုပ်များအကြား နေရာလွတ်များကို မြင်ရမည်ဖြစ်ပြီး ၎င်း၏ပတ်လည်ရှိ အခြား forest stand များမှ အလွယ်တကူ ခွဲခြားနိုင်ပါသည်။
* အပြာရောင် ဧရိယာများသည် ကျတ်တီးမြေများ၊ လမ်းများနှင့် မြို့ပြဧရိယာများ၊ ကြီးထွားမှုမရှိသေးသော စိုက်ပျိုးသီးနှံပင်များ အစရှိသည်တို့ကို ဖော်ပြပါသည်။
* Forest stand များကို ဖော်ထုတ်ရာတွင် ဓာတ်ပုံကို အလွန်နီးကပ်စွာ zoom ချဲ့မကြည့်ပါနှင့်။ ဤဓာတ်ပုံအတွက် 1:3000 နှင့် 1:5000 စကေးသည် လုံလောက်ပါသည်။ အောက်ပါပုံကိုကြည့်ပါ (1:4000 စကေး)-

.. figure:: img/zoom_to_CIR_1-4000.png
   :align: center


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - CIR ဓာတ်ပုံမှ Forest Stand များကို Digitize ပြုလုပ်ခြင်း (Try Yourself: Digitizing Forest Stands from CIR Imagery)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Forest stand များကို digitize ပြုလုပ်သောအခါ အပင်မျိုးစိတ်အရ၊ သစ်တောသက်တမ်းအရ၊ အပင်သိပ်သည်းမှုအရ homogeneous (တစ်မျိုးတည်းဖြစ်သည့်) ဖြစ်နိုင်သမျှဖြစ်သော သစ်တောဧရိယာများကို ရရှိရန်လုပ်ဆောင်သင့်ပါသည်။ အလွန်အသေးစိတ်လုပ်ဆောင်ပါက သေးငယ်သော forest stand များ ရာဂဏန်းနှင့်ချီပြီး ရရှိမည်ဖြစ်ပြီး အသုံးဝင်မှုရှိလိမ့်မည်မဟုတ်ပါ။ မသေးလွန်း (အနည်းဆုံး 0.5 ဟက်တာ) ပြီး မကြီးလွန်းသော (3 ဟက်တာထက်မပိုသော) forest stand များကို ရရှိရန် လုပ်ဆောင်သင့်ပါသည်။

ထိုအချက်များကို မှတ်ထားပြီး မရှိသေးသော forest stand များကို digitize စတင်လုပ်ဆောင်နိုင်ပြီဖြစ်ပါသည်။

#. Snapping နှင့် topology ရွေးချယ်စရာများကို သတ်မှတ်ပါ-

   #. :menuselection:`Project --> Snapping options...` သို့သွားပါ
   #. |snapping| :sup:`Enable Snapping` ကိုနှိပ်ပြီး :guilabel:`Advanced Configuration` ကို select လုပ်ပါ
   #. |checkbox| :guilabel:`forest_stands_2012` layer ကို အမှန်ခြစ်ပါ

      #. :guilabel:`Type` တွင် :guilabel:`Vertex` ဟုသတ်မှတ်ပါ
      #. :guilabel:`Tolerance` တွင် ``10`` ဟုသတ်မှတ်ပါ
      #. :guilabel:`Units` တွင် :guilabel:`pixels` ဟုသတ်မှတ်ပါ
      #. :guilabel:`Avoid Overlap` အောက်ရှိ box တွင် အမှန်ခြစ်ပါ
      #. |topologicalEditing| :guilabel:`Topological editing` ကိုနှိပ်ပါ
      #. |avoidIntersectionsLayers| :guilabel:`Follow Advanced Configuration` ကိုရွေးချယ်ပါ
      #. Dialog ကိုပိတ်လိုက်ပါ

      .. figure:: img/snapping_2012.png
         :align: center

#. Layer list ထဲရှိ :guilabel:`forest_stands_2012` layer ကို select လုပ်ပါ
#. Editing စတင်ရန် |toggleEditing| :sup:`Toggle Editing` ကိုနှိပ်ပါ
#. ယခင်သင်ခန်းစာထဲရှိ နည်းလမ်းများအတိုင်း digitizing ကိုစတင်ပါ။ တစ်ခုတည်းသော ကွာခြားချက်မှာ ယခုအခါတွင် snapping ပြုလုပ်ရန် မည်သည့် point layer မှမရှိတော့ပါ။ ဤဧရိယာအတွက် forest stand အသစ် 14 ခုခန့် ရရှိသင့်ပါသည်။ Digitize ပြုလုပ်နေစဉ်  ``StandID`` field ထဲတွင် ``901`` မှစတင်ပြီး ဂဏန်းများကို ဖြည့်သွင်းပါ။
#. လုပ်ဆောင်မှုပြီးဆုံးသွားသောအခါ layer သည် အောက်ပါပုံစံအတိုင်းဖြစ်သင့်ပါသည်-

   .. figure:: img/new_stands_ready.png
      :align: center

CIR ဓာတ်ပုံများမှ အဓိပ္ပါယ်ကောက်ယူထားသည့်အတိုင်း 2012 ခုနှစ်တွင်ရှိသော အမျိုးမျိုးသော forest stand များကိုပြသနေသည့် polygon များကို ရရှိပြီဖြစ်ပါသည်။ သို့သော် forest inventory data များမပါရှိသေးပါ။ ထိုအတွက် တောထဲသို့သွားရောက်ပြီး forest stand တစ်ခုချင်းစီအတွက် forest attribute များကိုခန့်မှန်းရာတွင်အသုံးပြုရမည့် sample data အချို့ကို ကောက်ယူရပါလိမ့်မည်။ နောက်လာမည့်သင်ခန်းစာတွင် ထိုအကြောင်းကို လေ့လာရပါမည်။ 

ဤဧရိယာအတွက် ထည့်သွင်းစဉ်းစားရန်လိုအပ်သည့် conservation regulation များအကြောင်း ထပ်ဆောင်းအချက်အလက်များအချို့ကို ထည့်သွင်းပေးနိုင်ပါသည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Forest Stand များကို Conservation အချက်အလက်များဖြင့် Update ပြုလုပ်ခြင်း (Follow Along: Updating Forest Stands with Conservation Information)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

ယခုလုပ်ဆောင်နေသည့်ဧရိယာအတွက် သစ်တောစီမံကိန်းများရေးဆွဲသောအခါ ထည့်သွင်းစဉ်းစားရမည့် conservation regulation အချို့ရှိပါသည်- 

* ထိန်းသိမ်းကာကွယ်ထားသော Siberian flying squirrel (Pteromys volans) မျိုးစိတ်၏ တည်နေရာ နှစ်ခုကို ဖော်ထုတ်ပြီးဖြစ်ပါသည်။ Regulation အရ တည်နေရာများပတ်လည် 15 မီတာဧရိယာကို ဘာမှမလုပ်ပဲ ထားခဲ့ရပါမည်။
* ဧရိယာထဲရှိ ချောင်းတစ်လျှောက်တွင် ပေါက်ရောက်နေသော Riparian (ကမ်းနားပေါက်ရောက်သော) forest ကို ထိန်းသိမ်းကာကွယ်ထားရပါမည်။ ကွင်းဆင်းလေ့လာသောအခါ ချောင်း၏တစ်ဖက်တစ်ချက် 20 မီတာကို ထိန်းသိမ်းကာကွယ်ထားရမည်ကို တွေ့ရှိခဲ့ရပါသည်။

Squirrel ၏တည်နေရာများပါဝင်သော vector ဖိုင်တစ်ခုရှိပါသည်၊ မြောက်ဘက်ဧရိယာမှ lake ဘက်သို့ စီးဆင်းနေသော digitize ပြုလုပ်ထားသည့် ချောင်းပါဝင်သော vector ဖိုင်တစ်ခုရှိပါသည်။

#. :file:`exercise_data\\forestry\\` folder မှ :file:`squirrel.shp` နှင့် :file:`stream.shp` ဖိုင်များကို project ထဲသို့ ထည့်သွင်းပါ။
#. ``squirrel`` layer ကိုကြည့်ရှုရန် |openTable| :sup:`Open Attribute Table` tool ကိုအသုံးပြုပါ

   Siberian flying squirrel အနေဖြင့် သတ်မှတ်ထားသော တည်နေရာ နှစ်ခု ရှိသည်ကို တွေ့မြင်နိုင်မည်ဖြစ်ပြီး ထိန်းသိမ်းကာကွယ်ရမည့်ဧရိယာကို တည်နေရာများမှ 15 မီတာအကွာအဝေးဖြင့် ညွှန်ပြထားသည်ကို တွေ့မြင်နိုင်ပါသည်။

ထိန်းသိမ်းကာကွယ်ရမည့်ဧရိယာကို ပိုမိုတိကျစွာ သတ်မှတ်ကြည့်ပါမည်။ Point တည်နေရာများပတ်လည်တွင် ထိန်းသိမ်းကာကွယ်ရမည့်အကွာအဝေးကို အသုံးပြုပြီး buffer တစ်ခုကို ဖန်တီးမည်ဖြစ်ပါသည်။

#. :menuselection:`Vector --> Geoprocessing Tools --> Buffer` ကိုဖွင့်ပါ
#. :guilabel:`Input layer` တွင် |pointLayer| :guilabel:`squirrel` ဟုသတ်မှတ်ပါ
#. :guilabel:`Distance` တွင် ``15 meters`` ဟုသတ်မှတ်ပါ
#. :guilabel:`Buffered` တွင် :file:`exercise_data\\forestry\\squirrel_15m.shp` ဟုသတ်မှတ်ပါ
#. |checkbox| :guilabel:`Open output file afer running algorithm` ကိုအမှန်ခြစ်ပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ
#. လုပ်ငန်းစဉ်ပြီးဆုံးပါက :guilabel:`Close` ကိုနှိပ်ပါ။

     .. figure:: img/squirrel_15m.png
      :align: center

ဧရိယာ၏ မြောက်ဘက်အပိုင်းရှိ တည်နေရာကို zoom ချဲ့ကြည့်ပါက buffer ဧရိယာသည် ကပ်လျက် stand နှစ်ခုပေါ်တွင် ကျရောက်နေသည်ကို တွေ့ရပါလိမ့်မည်။ ဆိုလိုသည်မှာ အဆိုပါ stand ထဲတွင် သစ်တောလုပ်ငန်းတစ်ခုလုပ်ဆောင်သည့်အချိန်တိုင်း ထိန်းသိမ်းကာကွယ်ထားသော တည်နေရာကိုလည်း ထည့်သွင်းစဉ်းစားသင့်သည်ဟု ဆိုလိုခြင်းဖြစ်ပါသည်။

.. figure:: img/north_squirrel_buffer.png
   :align: center

|

Squirrel များ၏ တည်နေရာများကို ထိန်းသိမ်းကာကွယ်ရန်အတွက် forest stand အသစ်များထဲတွင် attribute (column) အသစ်တစ်ခုထည့်သွင်းရပါမည်၊ ထို attribute ထဲတွင် ထိန်းသိမ်းကာကွယ်ရမည့် တည်နေရာများအကြောင်း အချက်အလက်များပါဝင်ပါလိမ့်မည်။ သစ်တောလုပ်ငန်းတစ်ခုကို အစီအစဉ်ချသည့်အချိန်တိုင်း ထိုအချက်အလက်များကို ရရှိလိမ့်မည်ဖြစ်ပြီး ကွင်းလုပ်ငန်းအဖွဲ့သည် လုပ်ငန်းမစတင်မီတွင် ဘာမှမလုပ်ပဲထားခဲ့ရမည့် ဧရိယာကို အမှတ်အသားပြုနိုင်မည်ဖြစ်သည်။

Squirrel များနှင့်ပတ်သက်သော အချက်အလက်များကို forest stand များနှင့် ချိတ်ဆက်ရန် :guilabel:`Join attributes by location` algorithm ကိုအသုံးပြုနိုင်ပါသည်-

#. :menuselection:`Vector --> Data Management Tools --> Join attributes by location` ကိုဖွင့်ပါ။
#. :guilabel:`Join to features in` တွင် |polygonLayer| :guilabel:`forest_stands_2012` ဟုသတ်မှတ်ပါ
#. :guilabel:`Geometric predicate` ထဲတွင် |checkbox| :guilabel:`intersect` ကိုအမှန်ခြစ်ပါ
#. :guilabel:`By comparing to` တွင် |polygonLayer| :guilabel:`squirrel_15m` ကိုသတ်မှတ်ပါ
#. :guilabel:`Join type` တွင် :guilabel:`Take attributes of the first matching feature only (one-to-one)` ဟုသတ်မှတ်ပါ
#. :guilabel:`Discard records which could not be joined` ကိုအမှန်ခြစ်ဖြုတ်ထားပါ
#. :guilabel:`Joined layer` တွင် :file:`exercise_data\\forestry\\stands_squirrel.shp` ဟုသတ်မှတ်ပါ
#. |checkbox| :guilabel:`Open output file afer running algorithm` ကိုအမှန်ခြစ်ပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ
#. လုပ်ငန်းစဉ်ပြီးဆုံးပါက dialog ကိုပိတ်နိုင်ပါသည်။

   .. figure:: img/joined_squirrel_buffer.png
      :align: center

:file:`stands_squirrel.shp` ဟုခေါ်သော forest stand layer အသစ်တစ်ခုရရှိပြီဖြစ်ပြီး  Siberian flying squirrel အတွက် ထိန်းသိမ်းကာကွယ်ရေးအချက်အလက်များပါဝင်နေမည်ဖြစ်သည်။

#. ``stands_squirrel`` layer ၏ attribute ဇယားကို ဖွင့်ပါ
#. ဇယားခေါင်းစီးတွင် :guilabel:`point_pr` field ကို click နှိပ်ပြီး ဇယားကို sort လုပ်ပါ။

   .. figure:: img/stands_squirrel_table.png
      :align: center

   ထိန်းသိမ်းကာကွယ်ရေး တည်နေရာများအကြောင်း အချက်အလက်များပါရှိသော forest stand အချို့ကို မြင်တွေ့ရနိုင်ပါသည်။ သစ်တောမန်နေဂျာအနေဖြင့် Forest stand data ထဲရှိ အချက်အလက်များကို ကြည့်ရှုပြီး ထိန်းသိမ်းကာကွယ်ရေးထည့်သွင်းစဉ်းစားစရာများကို သိနိုင်မည်ဖြစ်သည်။ :guilabel:`squirrel` dataset မှ တည်နေရာများကိုရရှိနိုင်မည်ဖြစ်ပြီး ကွင်းထဲသို့သွားကာ တည်နေရာပတ်လည် သက်ဆိုင်ရာ buffer ကို အမှတ်အသားလုပ်ပေးခြင်းဖြင့် squirrels များကို အနှောင့်အယှက်ပေးခြင်းမှ ရှောင်ရှားနိုင်မည်ဖြစ်သည်။

.. Todo? Consider doing an intersection between the buffer and stands layers
 to actually delimitate area people should not go to?


:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - ချောင်းသို့အကွာအဝေးဖြင့် Forest Stand များကို Update ပြုလုပ်ခြင်း (Try Yourself: Updating Forest Stands with Distance to the Stream)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

ထိန်းသိမ်းကာကွယ်ထားသော squirrel တည်နေရာများအတွက် လုပ်ဆောင်ခဲ့သည့်နည်းအတိုင်း Forest stand များကို ချောင်းနှင့်ဆက်စပ်သော ထိန်းသိမ်းကာကွယ်ရေးအချက်အလက်များဖြင့် update ပြုလုပ်နိုင်ပါသည်။ အချက်တစ်ချို့မှာ-

* ချောင်းပတ်လည် buffer သည် ``20`` မီတာဖြစ်ပါသည်
* Vector ဖိုင်တစ်ခုထဲမှာပင် ထိန်းသိမ်းကာကွယ်ရေးအချက်အလက်များအားလုံးကို ရှိစေချင်သည့်အတွက် :file:`stands_squirrel.shp` ကို base layer အဖြစ်အသုံးပြုပါ
* Output ဖိုင်ကို :file:`forest_stands_2012_protect.shp` ဟု အမည်ပေးပါ 


လုပ်ငန်းစဉ်ပြီးဆုံးပါက output layer ၏ attribute ဇယားကို ဖွင့်ကြည့်ပြီး ချောင်းနှင့်ဆက်စပ်သော riparian forest stand များအတွက် ထိန်းသိမ်းကာကွယ်ရေးအချက်အလက်များအားလုံး ပါဝင်ခြင်းရှိ/မရှိကို အတည်ပြုစစ်ဆေးပါ။

ရလာဒ်ကို ကျေနပ်မှုရှိပါက QGIS project ကိုသိမ်းဆည်းပါ။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Forest stand များကို digitize ပြုလုပ်ရန် CIR ဓာတ်ပုံများကို မည်သို့အဓိပ္ပါယ်ကောက်ယူရမည်ကို မြင်တွေ့ခဲ့ပြီးဖြစ်ပါသည်။ ပိုမိုတိကျသော stand များကိုဖန်တီးရန် အလေ့အကျင့်အချို့ရှိရမည်ဖြစ်ပြီး မြေအမျိုးအစားမြေပုံကဲ့သို့သော အခြား အချက်အလက်များကို အသုံးပြုခြင်းဖြင့် ပိုမိုကောင်းမွန်သော ရလာဒ်များကို ရရှိနိုင်ပါသည်၊ သို့သော် ယခုလေ့ကျင့်ခန်းသည် ထိုအတွက် အခြေခံအဆင့် ဖြစ်ပါသည်။ အခြား dataset များမှ အချက်အလက်များထည့်သွင်းခြင်းသည် အသေးအဖွဲအလုပ်တစ်ခုသာဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

သင် digitize ပြုလုပ်ထားခဲ့သော forest stand များကို အနာဂတ် သစ်တောလုပ်ငန်းများအစီအစဉ်ချမှတ်ရာတွင် အသုံးပြုနိုင်မည်ဖြစ်ပါသည်၊ သို့သော် သစ်တောနှင့်ပတ်သက်သော အချက်အလက်များကို ပိုမိုရရှိရန် လိုအပ်နေပါသေးသည်။ သင် digitize ပြုလုပ်ထားခဲ့သော သစ်တောဧရိယာတွင် inventory ပြုလုပ်ရန်နှင့် သစ်တော parameter များ၏ ယေဘုယျခန့်မှန်းချက်ကို ရရှိရန်  sampling plot (နမူနာကွက်) များ မည်သို့ချမှတ်ရမည်ကို နောက်လာမည့် သင်ခန်းစာတွင် လေ့လာရမည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |avoidIntersectionsLayers| image:: /static/common/mActionAvoidIntersectionsLayers.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |pointLayer| image:: /static/common/mIconPointLayer.png
   :width: 1.5em
.. |polygonLayer| image:: /static/common/mIconPolygonLayer.png
   :width: 1.5em
.. |snapping| image:: /static/common/mIconSnapping.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |topologicalEditing| image:: /static/common/mIconTopologicalEditing.png
   :width: 1.5em
