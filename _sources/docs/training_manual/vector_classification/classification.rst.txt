သင်ခန်းစာ- အတန်းအစားခွဲခြားခြင်း (Lesson: Classification)
======================================================================

Label များသည် သီးခြားနေရာများ၏အမည်များကဲ့သို့ အချက်အလက်များအတွက် ကောင်းမွန်ပါသော်လည်း အရာရာတိုင်းအတွက် အသုံးမပြုနိုင်ပါ။ ဥပမာ၊ ``landuse`` ဧရိယာတစ်ခုချင်းစီသည် ဘာအတွက်အသုံးပြုသလဲဆိုသည်ကို သိချင်လျှင် Label များအသုံးပြုပြီး သိနိုင်ပါသည်-

.. figure:: img/bad_landuse_labels.png
   :align: center

မြေပုံပေါ်ရှိ label များသည် ဖတ်ရှုရန် ခက်ခဲနေပြီး မြေပုံပေါ်တွင် များစွာသော landuse ဧရိယာအမျိုးမျိုးရှိနေလျှင် label များထပ်နေစေပါသည်။


**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Vector data များကို ထိရောက်မှုရှိရှိ အတန်းအစားခွဲခြားတတ်စေရန်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- Nominal Data များကို အတန်းအစားခွဲခြားခြင်း (Follow Along: Classifying Nominal Data)
--------------------------------------------------------------------------------------------------------------------------------

#. ``landuse`` layer အတွက် :guilabel:`Layer Properties` dialog ကိုဖွင့်ပါ
#. :guilabel:`Symbology` tab သို့သွားပါ
#. :guilabel:`Single Symbol` ဟုပေါ်နေသော dropdown ကိုနှိပ်ပြီး :guilabel:`Categorized` သို့ပြောင်းပါ-

   .. figure:: img/categorised_styles.png
      :align: center

#. Panel အသစ်ထဲတွင် :guilabel:`Value` ကို ``landuse`` ဟုပြောင်းပြီး :guilabel:`Color ramp` ကို :guilabel:`Random colors` ပြောင်းပါ
#. :guilabel:`Classify` ခလုတ်ကိုနှိပ်ပါ

   .. figure:: img/categorised_style_settings.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ

   အောက်ပါပုံစံအတိုင်း တွေ့ရပါလိမ့်မည်-

   .. figure:: img/categorisation_result.png
      :align: center

#. :guilabel:`Layers` panel ထဲရှိ ``landuse`` ၏ဘေးတွင်ရှိသော မြား (သို့မဟုတ် အပေါင်းလက္ခဏာ) ကိုနှိပ်ပါ၊ အောက်ပါအတိုင်း category (အမျိုးအစား) များကို တွေ့ရပါလိမ့်မည်-

   .. figure:: img/categories_explained.png
      :align: center

   Landuse polygon များကို အရောင်ဖြည့်ထားပြီး အတန်းအစားခွဲခြားထားပါသည်၊ ထို့ကြောင့် landuse တူညီသော ဧရိယာများသည် အရောင်အတူတူဖြစ်နေပါသည်။

#. :guilabel:`Layers` panel သို့မဟုတ် :guilabel:`Layer Properties` dialog ထဲတွင် အရောင်အကွက်ကို click နှစ်ချက်နှိပ်ပြီး landuse ဧရိယာတစ်ခုချင်းစီ၏ သင်္ကေတကို ပြောင်းလဲနိုင်ပါသည်-

   .. figure:: img/change_layer_color.png
      :align: center

ဗလာ (empty) ဖြစ်နေသော category (အမျိုးအစား) တစ်ခုရှိနေပါသည်-

.. figure:: img/empty_category.png
   :align: center

ဗလာဖြစ်နေသော category သည် landuse တန်ဖိုးမသတ်မှတ်ထားသော သို့မဟုတ် *NULL* တန်ဖိုးရှိသော မည်သည့်အရာကိုမဆို အရောင်ခြယ်ရန် အသုံးပြုပါသည်။ ဗလာဖြစ်နေသော category ကိုဆက်လက်ထားရှိခြင်းသည် *NULL* တန်ဖိုးရှိသော ဧရိယာများကို မြေပုံပေါ်တွင်ဖော်ပြရာတွင် အသုံးဝင်ပါသည်။ ဗလာ သို့မဟုတ် *NULL* တန်ဖိုးကို သိသာစွာ ပြသလိုလျှင် အရောင်ပြောင်းလဲနိုင်ပါသည်။

လုပ်ဆောင်ထားသည့် ပြောင်းလဲမှုများမပျက်သွားစေရန် မြေပုံကို သိမ်းဆည်းရန် မမေ့ပါနှင့်၊

:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- နောက်ထပ် အတန်းအစားခွဲခြားခြင်း (Try Yourself: More Classification)
----------------------------------------------------------------------------------------------------------------------------

အထက်တွင် လေ့လာခဲ့သည့်အတိုင်း ``buildings`` layer ကို အတန်းအစားခွဲခြားပါ။ ``building`` field ပေါ်မူတည်ပြီး category ခွဲကာ :guilabel:`Spectral` အရောင်စဉ်တန်း ကိုအသုံးပြုပါ။

.. note:: ရလာဒ်ကို မြင်နိုင်ရန် Urban ဧရိယာကို zoom ချဲ့ကြည့်ပါ

:abbr:`★★☆ (Moderate level)` လုပ်လိုက်ကြည့်ပါ- Ratio Classification (Follow Along: Ratio Classification)
---------------------------------------------------------------------------------------------------------

Classification (အတန်းအစားခွဲခြားခြင်း) အမျိုးအစား ၄ မျိုးရှိပါသည်- *nominal* ၊ *ordinal* ၊
*interval* နှင့် *ratio* တို့ဖြစ်ပါသည်။

**nominal** classification တွင် object များကို အတန်းအစားခွဲသည့် category များသည် (name-based) အမည်ကိုအခြေခံပြီး order (အစဉ်) မရှိပါ။ ဥပမာ- မြို့အမည်များ၊ ခရိုင် code များ၊ အစရှိသည်တို့ဖြစ်သည်။ Nominal data များအတွက် အသုံးပြုသော သင်္ကေတများသည် order သို့မဟုတ် magnitude များကို ရည်ညွှန်းခြင်းမရှိသင့်ပါ။

* Point များအတွက် သင်္ကေတပုံသဏ္ဍာန်အမျိုးမျိုးကို အသုံးပြုနိုင်ပါသည်။
* Polygon များအတွက် အကွက်ပုံစံအမျိုးမျိုး သို့မဟုတ် အရောင်အမျိုးမျိုးကို အသုံးပြုနိင်ပါသည် (အရောင်ဖျော့နှင့် အရောင်ရင့် ရောမသုံးပါနှင့်)။
* Line များအတွက် dash (-) ပုံသဏ္ဍာန်အမျိုးမျိုး၊ အရောင်အမျိုးမျိုး (အရောင်ဖျော့နှင့် အရောင်ရင့် ရောမသုံးပါနှင့်) နှင့် line တစ်လျှောက် သင်္ကေတအမျိုးမျိုးကို အသုံးပြုနိုင်ပါသည်။


**ordinal** classification တွင် category များကို order တစ်ခုဖြင့် စီစဉ်ထားပါသည်။ ဥပမာ- ကမ္ဘာ့မြို့များ၏ ကုန်သွယ်ရေး၊ ခရီးသွားလာရေး၊ ယဉ်ကျေးမှု၊ စသည်တို့အတွက် အရေးကြီးမှုပေါ်မူတည်၍ ၎င်းမြို့များကို အဆင့်သတ်မှတ်ချက်တစ်ခုပေးထားပါသည်။ Ordinal data များအတွက် အသုံးပြုသော သင်္ကေတများသည် order ကိုရည်ညွှန်းပြီး magnitude ကိုရည်ညွှန်းခြင်းမရှိပါ။

* Point များအတွက် ဖျော့ရာမှ ရင့်သွားသော အရောင်များပါဝင်သော သင်္ကေတများကို အသုံးပြုနိုင်ပါသည်။
* Polygon များအတွက် အဆင့်အလိုက် ဖြစ်သော (graduated) အရောင်များ (အဖျော့ မှ အရင့်သို့) ကိုအသုံးပြုနိုင်ပါသည်။
* Line များအတွက် အဆင့်အလိုက် ဖြစ်သော (graduated) အရောင်များ (အဖျော့ မှ အရင့်သို့) ကိုအသုံးပြုနိုင်ပါသည်။

**interval** classification တွင် ဂဏန်းများသည် အပေါင်း၊ အနှုတ် နှင့် သုည တန်ဖိုးများရှိသော စကေးတစ်ခုအတွင်းရှိသည်။ ဥပမာ- ပင်လယ်ရေမျက်နှာပြင် အထက်ရှိ အမြင့်/ အောက်ရှိ အမြင့်၊ ဒီဂရီ ဆဲလ်စီးယပ် ဖြင့်အပူချိန်။ Interval data များအတွက် အသုံးပြုသော သင်္ကေတများသည် order နှင့် magnitude ကိုရည်ညွှန်းပါသည်။

* Point များအတွက် အရွယ်အစားကွဲပြားသော သင်္ကေတများ (အသေး မှ အကြီး သို့) ကို အသုံးပြုနိုင်ပါသည်။ 
* Polygon များအတွက် အဆင့်အလိုက် ဖြစ်သော အရောင်များ (အဖျော့ မှ အရင့် သို့) ကိုအသုံးပြုနိုင်ပါသည်။
* Line များအတွက် အထူ (thickness) ကို အသုံးပြုနိုင်ပါသည် (အပါး မှ အထူ သို့)

**ratio** classification တွင် ဂဏန်းများသည် အပေါင်းနှင့် သုည တန်ဖိုးသာရှိသော စကေးတစ်ခုအတွင်းရှိသည်။ ဥပမာ- ပကတိသုည (0 ဒီဂရီ ကယ်ဗင်) အထက်ရှိ အပူချိန်၊ point တစ်ခုမှ အကွာအဝေး၊ လအလိုက် လမ်းတစ်ခုပေါ်ရှိ ပျမ်းမျှ ယာဉ်အသွားအလာ ပမာဏ၊ အစရှိသည်တို့ဖြစ်သည်။ Interval data များအတွက် အသုံးပြုသော သင်္ကေတများသည် order နှင့် magnitude ကိုရည်ညွှန်းပါသည်။

* Point များအတွက် အရွယ်အစားကွဲပြားသော သင်္ကေတများ (အသေး မှ အကြီး သို့) ကို အသုံးပြုနိုင်ပါသည်။ 
* Polygon များအတွက် အဆင့်အလိုက် ဖြစ်သော အရောင်များ (အဖျော့ မှ အရင့် သို့) သို့မဟုတ် အရွယ်အစားအမျိုးမျိုးဖြင့် ရုပ်ပုံများ ကို အသုံးပြုနိုင်ပါသည်။
* Line များအတွက် အထူ (thickness) ကို အသုံးပြုနိုင်ပါသည် (အပါး မှ အထူ သို့)။

အထက်ပါဥပမာထဲတွင် ``landuse`` layer ထဲရှိ record တစ်ခုချင်းစီကို ၎င်း၏ ``landuse`` attribute ပေါ်အခြေခံပြီး အရောင်ခြယ်သရန် nominal classification ကိုအသုံးပြုခဲ့ပါသည်။ ယခုအခါ record များကို ဧရိယာအလိုက် အတန်းအစားခွဲခြားရန် ratio classification ကို အသုံးပြုပါမည်။

Layer ကို အတန်အစားပြန်ခွဲခြားမည်ဖြစ်သောကြောင့် မသိမ်းဆည်းရသေးလျှင် ရှိနေပြီးသား အတန်းအစားများပျက်ကုန်မည်ဖြစ်သည်။ လက်ရှိ classification ကို သိမ်းဆည်းရန်-

#. Layer ၏ properties dialog ကိုဖွင့်ပါ
#. :guilabel:`Style` drop-down menu ထဲမှ :guilabel:`Save Style ...` ခလုတ်ကိုနှိပ်ပါ။
#. :guilabel:`Rename Current...` ကိုရွေးချယ်ပြီး ``land usage`` ဟုရိုက်ထည့်ပြီး :guilabel:`OK` ကိုနှိပ်ပါ။

   အမျိုးအစားများနှင့် ၎င်းတို့၏သင်္ကေတများကို layer ၏ property များထဲတွင် သိမ်းဆည်းထားပြီဖြစ်သည်။
#. :guilabel:`Style` drop-down menu ၏ :guilabel:`Add...` ပေါ်တွင် နှိပ်ပြီး ``ratio`` အမည်ဖြင့် style အသစ်တစ်ခုဖန်တီးပါ။ ၎င်းသည် classification အသစ်ကို သိမ်းဆည်းလိမ့်မည်ဖြစ်သည်။
#. :guilabel:`Layer Properties` dialog ကိုပိတ်ပါ။

Landuse ဧရိယာများကို အရွယ်အစားဖြင့် အတန်းအစားခွဲခြားလိုပါသည်၊ သို့သော် ပြဿနာတစ်ခုမှာ အရွယ်အစား field တစ်ခုမပါရှိပါ၊ ထို့ကြောင့် အရွယ်အစား field အသစ်ကိုဖန်တီးပါမည်။

#. ``landuse`` layer အတွက် Attribute ဇယားကို ဖွင့်ပါ။
#. |toggleEditing|  :sup:`Toggle editing` ခလုတ်ကို နှိပ်ပြီး edit mode ကိုဝင်ပါ။
#. |newAttribute| :sup:`New field` ခလုတ်ကိုအသုံးပြု၍ ဒဿမအမျိုးအစားဖြင့် column အသစ်တစ်ခုကို ထည့်သွင်းပြီး ``AREA`` ဟုအမည်ပေးပါ။

   .. figure:: img/add_area_column.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ။

   Field အသစ်ကို ထည့်သွင်းပေးမည်ဖြစ်သည် (ဇယား၏ ညာဘက်အစွန်ဆုံးတွင်ရှိသည်၊ မမြင်ရလျှင် ရေပြင်ညီ scroll လုပ်ပြီးကြည့်နိုင်ပါသည်)။ သို့သော် အခုအချိန်တွင် *NULL* တန်ဖိုးများအများအပြားပါရှိနေပါသည်။

   ထိုပြဿနာကိုဖြေရှင်းရန် ဧရိယာများကို တွက်ချက်ရန်လိုအပ်ပါသည်။

   #. |calculateField| ခလုတ်ကိုနှိပ်ပြီး field calculator ကိုဖွင့်ပါ။

      အောက်ပါ dialog ပွင့်လာပါမည်-

      .. figure:: img/calculate_field_dialog.png
         :align: center

   #. |checkbox| :guilabel:`Update existing fields` ကိုအမှန်ခြစ်ပါ
   #. Field များ drop-down menu ထဲတွင် :guilabel:`AREA` ကိုရွေးချယ်ပါ

      .. figure:: img/field_calculator_top.png
         :align: center

   #. :guilabel:`Expression` tab အောက်တွင် စာရင်းထဲရှိ :guilabel:`Geometry` function များအုပ်စုကို ဖြန့်ကြည့်ပြီး :menuselection:`$area` ကို ရှာပါ။

   #. ၎င်းကို click နှစ်ချက်နှိပ်လိုက်ပါက :guilabel:`Expression` field ထဲတွင် ပေါ်လာမည်ဖြစ်သည်

      .. figure:: img/geometry_area_select.png
         :align: center

   #. :guilabel:`OK` ကိုနှိပ်ပါ
   #. Attribute ဇယားထဲရှိ ``AREA`` field ကိုကြည့်လိုက်ပါက တန်ဖိုးများထည့်သွင်းပြီးသားဖြစ်နေမည်ကို တွေ့ရပါလိမ့်မည် (Data များပေါ်လာစေရန် column ၏ ခေါင်းစီးကို click လုပ်ပေးရန် လိုအပ်ကောင်းလိုအပ်နိုင်ပါသည်)

   .. note:: အဆိုပါ ဧရိယာများသည် project ၏ ဧရိယာယူနစ် setting များအတိုင်းဖြစ်သည်၊ ထို့ကြောင့် စတုရန်းမီတာ သို့မဟုတ် စတုရန်းဒီဂရီ ယူနစ်များဖြင့် ဖြစ်နိုင်ပါသည်။

#. တည်းဖြတ်မှုများကိုသိမ်းဆည်းရန် |saveEdits| ကိုနှိပ်ပါ၊ ထို့နောက် |toggleEditing| :sup:`Toggle editing` ကိုနှိပ်ပြီး edit mode မှ ထွက်ပါ။
#. Attribute ဇယားကို ပိတ်လိုက်ပါ။

ရရှိပြီးသော data ကို ``landuse`` layer အားပုံဖော်ပြသရာတွင် အသုံးပြုကြည့်ပါမည်။ 

#. ``landuse`` layer အတွက် :guilabel:`Layer properties` dialog မှ :guilabel:`Symbology` tab ကိုဖွင့်ပါ
#. Classification style ကို :guilabel:`Categorized` မှ :guilabel:`Graduated` သို့ပြောင်းပါ

#. :guilabel:`Value` တွင် ``AREA`` ဟုပြောင်းပါ

#. :guilabel:`Color ramp` အောက်တွင် :guilabel:`Create New Color Ramp...` ဆိုသည့် option ကိုရွေးချယ်ပါ-

   .. figure:: img/area_gradient_select.png
      :align: center

#. :guilabel:`Gradient` ကိုရွေးချယ် (ရွေးချယ်ထားပြီးသားမရှိလျှင်) ပြီး :guilabel:`OK` ကိုနှိပ်ပါ။ အောက်ပါပုံအတိုင်း မြင်တွေ့ရပါလိမ့်မည်-

   .. figure:: img/gradient_color_select.png
      :align: center

   ၎င်းကို ဧရိယာများကို ညွှန်းဆိုပြသရာတွင် အသုံးပြုမည်ဖြစ်ပြီး ဧရိယာငယ်များကို :guilabel:`Color 1` အနေဖြင့်ပြသပြီး ဧရိယာအကြီးများကို :guilabel:`Color 2` အနေဖြင့်ပြသမည်ဖြစ်သည်။


#. သင့်တော်သော အရောင်များကို ရွေးချယ်ပါ

   ဥပမာထဲတွင် ရလာဒ်သည် အောက်ပါပုံစံအတိုင်း ဖြစ်ပါလိမ့်မည်-

   .. figure:: img/gradient_color_example.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ
#. :guilabel:`Color ramp` tab အောက်ရှိ :guilabel:`Save Color Ramp...` ကိုရွေးချယ်ခြင်းဖြင့် color ramp (အရောင်စဉ်တန်း) ကို သိမ်းဆည်းနိုင်ပါသည်။ Color ramp အတွက် သင့်တော်သော အမည်တစ်ခုပေးပြီး :guilabel:`Save` ကိုနှိပ်ပါ။ :guilabel:`All Color Ramps` အောက်တွင် တူညီသော color ramp ကို အလွယ်တကူရွေးချယ်နိုင်ပါလိမ့်မည်။
#. :guilabel:`Mode` အောက်တွင် |equalCount| :sup:`Equal Count (Quantile)` ကိုရွေးချယ်ပါ။
#. :guilabel:`Classify` ကိုနှိပ်ပါ။

   အောက်ပါပုံစံအတိုင်း တွေ့ရပါလိမ့်မည်-

   .. figure:: img/landuse_gradient_selected.png
      :align: center

   ကျန်သောအရာများကို ဒီအတိုင်း ထားခဲ့ပါ။

#. :guilabel:`OK` ကိုနှိပ်ပါ-

.. figure:: img/gradient_result_map.png
   :align: center


:abbr:`★★☆ (Moderate level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- Classification ကို ပိုမိုကောင်းမွန်အောင်လုပ်ဆောင်ခြင်း (Try Yourself: Refine the Classification)
-------------------------------------------------------------------------------------------------------------------------------------------------------------

* အဓိပ္ပါယ်ရှိသော classification တစ်ခုမရမချင်း :guilabel:`Mode` နှင့် :guilabel:`Classes` တန်ဖိုးများကို ပြောင်းလဲကြည့်ပါ။ 

.. admonition:: အဖြေ
   :class: dropdown

   အသုံးပြုသော setting များသည် မတူညီနိုင်ပါ၊ :guilabel:`Classes` = ``6`` နှင့် :guilabel:`Mode` = :guilabel:`Natural Breaks (Jenks)` (အရောင်အတူတူအသုံးပြုထားပြီး) တန်ဖိုးများဖြင့်ဆိုလျှင် မြေပုံသည် အောက်ပါပုံစံအတိုင်း ဖြစ်ပါလိမ့်မည်-

   .. figure:: img/gradient_map_new_mode.png
      :align: center


:abbr:`★★★ (Advanced level)` လိုက်လုပ်ကြည့်ပါ- စည်းမျဉ်းအခြေခံသော Classification (Follow Along: Rule-based Classification)
---------------------------------------------------------------------------------------------------------------------------

Classification တစ်ခုအတွက် criteria (သတ်မှတ်ချက်) အများအပြားကို ပေါင်းစပ်ခြင်းသည် အသုံးဝင်စေပါသည်၊ သို့သော် သာမန် classification ပြုလုပ်ခြင်းသည် attribute တစ်ခုကိုသာ ထည့်သုံးပါသည်။ ထိုနေရာတွင် စည်းမျဉ်းအခြေခံသော (rule-based) classification သည် အသုံးဝင်လာပါသည်။

ဤသင်ခန်းစာတွင် အခြားလူနေအိမ်ဧရိယာများနှင့် အခြား landuse အမျိုးအစား (ဧရိယာပေါ်မူတည်ပြီး) များမှ |majorUrbanName| မြို့ကို အလွယ်တကူ သတ်မှတ်ဖော်ထုတ်မည့် နည်းလမ်းဖြင့် ``landuse`` layer ကိုဖော်ပြသွားမည်ဖြစ်သည်။

#. ``landuse`` layer အတွက် :guilabel:`Layer Properties` dialog ကိုဖွင့်ပါ
#. :guilabel:`Symbology` tab သို့ပြောင်းပါ
#. Classification style ကို :guilabel:`Rule-based` သို့ပြောင်းပါ

   QGIS သည် layer အတွက် လုပ်ဆောင်မည့် လက်ရှိ classification ကိုကိုယ်စားပြုမည့် rule (စည်းမျဉ်း) များကို အလိုအလျောက်ပြသပေးပါလိမ့်မည်။ ဥပမာ- အထက်ပါ လေ့ကျင့်ခန်းကို ပြီးစီးပါက အောက်ပါပုံစံအတိုင်း မြင်တွေ့ရပါလိမ့်မည်-

   .. figure:: img/rule_based_classification.png
      :align: center

#. Rule များအားလုံးကို ရွေးချယ်ရန် click နှိပ်ပြီး ဖိဆွဲပါ။
#. ရှိနေပြီးသား rule များအားလုံးကို ဖယ်ရှားရန် |symbologyRemove| :sup:`Remove selected rules` ခလုတ်ကိုအသုံးပြုပါ။

စိတ်ကြိုက် rule များကိုထည့်သွင်းကြည့်ကြပါမည်။

#. |symbologyAdd| :sup:`Add rule` ခလုတ်ကို နှိပ်ပါ
#. :guilabel:`Edit rule` dialog ပေါ်လာပါမည်
#. :guilabel:`Label` အနေဖြင့် ``Swellendam city`` ကိုထည့်ပါ
#. :guilabel:`Filter` စာသားဘေးရှိ |expression| ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Expression String Builder` ကိုဖွင့်ပါ
#. ``"name" = 'Swellendam'`` ရိုက်ထည့်ပြီး validate လုပ်ပါ

   .. figure:: img/query_builder_example.png
      :align: center

#. :guilabel:`Edit rule` dialog သို့ ပြန်သွားပြီး ၎င်းကို မီးခိုးပြာရောင် (grey-blue) အရင့် တစ်ခုထားပြီး border (ဘောင်) ကိုဖယ်ရှားလိုက်ပါ

   .. figure:: img/rule_style_result.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ
#. အောက်ပါ rule များကို ထည့်သွင်းရန် အထက်ဖော်ပြပါအဆင့်များအတိုင်း ထပ်မံလုပ်ဆောင်ပါ-

   #. ``"landuse" = 'residential' AND "name" <> 'Swellendam'`` ဟူသော သတ်မှတ်ချက်ဖြင့် **Other residential** အညွှန်း။ :guilabel:`Fill color` ကို မီးခိုးပြာ (blue-grey) အဖျော့ ရွေးချယ်ပါ။
   #. ``"landuse" <> 'residential' AND "AREA" >= 605000`` ဟူသော သတ်မှတ်ချက်ဖြင့် **Big non residential areas** အညွှန်း။ အလယ်စိမ်း (mid-green) အရောင်တစ်ခု ရွေးချယ်ပါ။

      .. figure:: img/criterion_refined_midway.png
         :align: center

      အဆိုပါ filter များသည် rule နှင့်ကိုက်ညီသော ဧရိယာများကို မြေပုံပေါ်တွင် ဖော်ပြပေးမည်ဖြစ်သည် (605000 စတုရန်းမီတာထက်ငယ်သော non-residential ဧရိယာများသည် rule များထဲတွင် ပါဝင်မည်မဟုတ်ပါ)

   #. **Small non residential areas** ဟူသော rule အသစ်တစ်ခုကိုအသုံးပြုပြီး ကျန်ရှိနေသော feature များကို ရယူပါမည်။ Filter expression တစ်ခုအစား |radioButtonOn| :guilabel:`Else` ကိုအမှန်ခြစ်ပါ။ အဆိုပါ category ကို သင့်တော်သော အစိမ်းဖျော့ရောင် တစ်ခုပေးထားပါ။

      .. figure:: img/criterion_else.png
         :align: center

   Rule များသည် အောက်ပါပုံစံအတိုင်း ဖြစ်နေသင့်ပါသည်-

   .. figure:: img/criterion_refined_list.png
      :align: center

#. Apply ကိုနှိပ်ပါ။

မြေပုံသည် အောက်ပါပုံစံအတိုင်းဖြစ်နေပါလိမ့်မည်-

.. figure:: img/rule_based_map_result.png
   :align: center

ယခုဆိုလျှင် အထင်ကရအဖြစ်ဆုံး လူနေ (residential) ဧရိယာနှင့် အခြား လူမနေသော (non-residential) ဧရိယာများကို ၎င်းတို့၏ အရွယ်အစားအရ အရောင်ခြယ်သထားသော |majorUrbanName| ပါဝင်သည့် မြေပုံတစ်ခုကို ရရှိပြီဖြစ်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
----------------------------------------------------------------------

Symbology (သင်္ကေတဆိုင်ရာများ) သည် layer တစ်ခု၏ attribute များကို အလွယ်တကူ ဖော်ပြပေးစေနိုင်ပါသည်။ ရွေးချယ်လိုက်သော attribute တစ်ခုခုကိုအသုံးပြုပြီး feature များ၏ သိသာထင်ရှားမှုကို မြေပုံဖတ်ရှုသူများအား နားလည်စေနိုင်ပါသည်။ ကြုံတွေ့နေရသည့် ပြဿနာပေါ်မူတည်ပြီး အမျိုးမျိုးသော classification နည်းလမ်းများကို အသုံးချနိုင်ပါသည်။

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
----------------------------------------------------------------------

ယခုဆိုလျှင် ကြည့်ကောင်းသော မြေပုံတစ်ခုကို ရရှိပြီဖြစ်ပါသည်၊ သို့သော် ထိုမြေပုံကို QGIS အပြင်ဘက်သို့ print ထုတ်နိုင်သော format တစ်ခုဖြင့်မည်သို့ ထုတ်ယူမည်ကို နောက်လာမည့် သင်ခန်းစာတွင် တွေ့ရမည်ဖြစ်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |equalCount| image:: /static/common/mClassificationEqualCount.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |majorUrbanName| replace:: Swellendam
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |saveEdits| image:: /static/common/mActionSaveEdits.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
