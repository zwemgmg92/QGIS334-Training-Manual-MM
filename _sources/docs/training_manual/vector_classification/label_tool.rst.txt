သင်ခန်းစာ - အညွှန်းများ (Lesson: Labels)
===============================================================================

Object တစ်ခုအကြောင်း သတင်းအချက်အလက်တစ်ခုခုကို ပြသရန် မြေပုံပေါ်တွင် label (အညွှန်း) များထည့်သွင်းနိုင်ပါသည်။ Vector layer မှန်သမျှ ၎င်းနှင့်သက်ဆိုင်ရာ label များရှိနိုင်ပါသည်။ ထို label များသည် layer တစ်ခု၏ attribute data များပေါ်တွင် မူတည်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Layer တစ်ခုတွင် အသုံးဝင်ပြီး ကြည့်ကောင်းသော label များအသုံးပြုရန်

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- Label များအသုံးပြုခြင်း (Follow Along: Using Labels)
-------------------------------------------------------------------------------------------------

ဦးစွာ GUI ထဲတွင် |labelingSingle| ခလုတ် မြင်ရအောင်လုပ်ပါ-

#. Menu item :menuselection:`View --> Toolbars` သို့သွားပါ။
#. :guilabel:`Label Toolbar` item ၏ဘေးတွင် အမှန်ခြစ်ဖြစ်နေအောင် လုပ်ထားပါ။ ဖြစ်မနေလျှင် :guilabel:`Label Toolbar` ပေါ်တွင် click နှိပ်ပါ။
#. :guilabel:`Layers` panel ထဲရှိ ``places`` layer ကို click နှိပ်ပါ။
#. :guilabel:`Layer Styling` panel ၏ :guilabel:`Labels` tab ကိုဖွင့်ရန် |labelingSingle| toolbar ခလုတ်ကို နှိပ်ပါ။

#. :guilabel:`No Labels` မှ |labelingSingle| :guilabel:`Single Labels` သို့ပြောင်းပါ။

   Label များအတွက် attribute များမှ မည်သည့် field ကို အသုံးပြုမည်ဆိုသည်ကို ရွေးချယ်ပေးရန် လိုပါသည်။ ယခင်သင်ခန်းစာထဲတွင် ``name`` field သည် ယခုလုပ်ဆောင်မည့်ကိစ္စအတွက် အသင့်တော်ဆုံး field အဖြစ် ဆုံးဖြတ်ခဲ့ပြီးဖြစ်ပါသည်။

#. Value list မှ ``name`` ကိုရွေးချယ်ပါ-

   .. figure:: img/select_label_with.png
      :align: center

#. :guilabel:`Apply` ကိုနှိပ်ပါ။

မြေပုံသည် အောက်ပါပုံစံအတိုင်း label များရှိနေသင့်ပါသည်-

.. figure:: img/first_place_names.png
   :align: center


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ- Label option များကို ပြောင်းလဲခြင်း (Follow Along: Changing Label Options)
-----------------------------------------------------------------------------------------------------------------------

အစောပိုင်းက သင်ခန်းစာများတွင် မြေပုံအတွက်ရွေးခဲ့သော style များပေါ်မူတည်၍ label များသည် ကောင်းမွန်စွာ format မဖြစ်ခြင်း၊ point marker များမှ ဝေးလွန်းခြင်း သို့မဟုတ် ထပ်နေခြင်းများ ဖြစ်နေသည်ကိုတွေ့ရနိုင်ပါသည်။

.. note:: အပေါ်တွင် :guilabel:`Layer Styling` panel ကိုဖွင့်ရန် :guilabel:`Label Toolbar` ထဲရှိ |labelingSingle| ခလုတ်ကို အသုံးပြုခဲ့ပါသည်။ ထိုကဲ့သို့သော label option များကို :guilabel:`Layer Styling` panel နှင့် :guilabel:`Layer Properties` dialog မှတဆင့်လည်း ဖွင့်နိုင်ပါသည်။ ဤတွင် :guilabel:`Layer Properties` dialog ကိုအသုံးပြုပါမည်။

#. ``places`` layer ပေါ်တွင် click နှစ်ချက်နှိပ်ပြီး :guilabel:`Layer Properties` dialog ကိုဖွင့်ပါ။
#. |labelingSingle| :guilabel:`Labels` tab ကို select လုပ်ပါ။
#. ဘယ်ဘက် option list ထဲတွင် :guilabel:`Text` ကို select လုပ်ထားပြီး အောက်တွင်ပြထားသည့်အတိုင်း စာသား format ပြင်ဆင်ခြင်း option များကို ပြင်ဆင်ပါ-

   .. figure:: img/label_formatting_options.png
      :align: center

#. :guilabel:`Apply` ကိုနှိပ်ပါ။

   ထို စာလုံးဖောင့် သည် ကြီးနေပြီး အသုံးပြုသူများနှင့်ပိုရင်းနှီးနေနိုင်သော်လည်း ၎င်းကို ဖတ်ရှုရာတွင် ၎င်းစာသား၏အောက်၌ မည်သည့် layer များ ပုံဖော်ပြသထားသည့်အပေါ်မူတည်နေပါသေးသည်။ ထိုအရာကို ဖြေရှင်းရန် :guilabel:`Buffer` option ကို ကြည့်ကြည့်ပါ။

#. ဘယ်ဘက် option list မှ :guilabel:`Buffer` ကို select လုပ်ပါ။
#. :guilabel:`Draw text buffer` ၏ဘေးရှိ checkbox ကိုအမှန်ခြစ်ပါ၊ ထို့နောက် အောက်တွင်ပြထားသည့်အတိုင်း option များကိုရွေးချယ်ပါ-

   .. figure:: img/buffer_options.png
      :align: center

#. :guilabel:`Apply` ကိုနှိပ်ပါ။

   နေရာကိုပြသသော label များတွင် အရောင် buffer တစ်ခု သို့မဟုတ် border တစ်ခု ထည့်သွင်းပေးမည်ဖြစ်ပြီး ၎င်းတို့ကို မြေပုံပေါ်တွင် အလွယ်တကူ ရှာတွေ့နိုင်ပါသည်-

   .. figure:: img/buffer_results.png
      :align: center

   ယခုဆိုလျှင် label များကို ၎င်းတို့၏ point marker များနှင့်ဆက်စပ်ပြီး နေရာချထားနိုင်ပြီဖြစ်ပါသည်။

#. ဘယ်ဘက် option list ထဲမှ :guilabel:`Placement` ကို select လုပ်ပါ။
#. :guilabel:`Around point` ကိုရွေးချယ်ပြီး :guilabel:`Distance` တန်ဖိုးကို ``2.0`` မီလီမီတာသို့ ပြောင်းပါ-

   .. figure:: img/offset_placement_settings.png
      :align: center

#. :guilabel:`Apply` ကိုနှိပ်ပါ။

   Label များသည် ၎င်းတို့၏ point marker များနှင့် ထပ်နေခြင်းမရှိတော့သည်ကို မြင်တွေ့ရပါလိမ့်မည်။


:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- Layer သင်္ကေတ အစား Label များကို အသုံးပြုခြင်း (Follow Along: Using Labels Instead of Layer Symbology)
------------------------------------------------------------------------------------------------------------------------------------------------------

အများစုတွင် point တစ်ခု၏ တည်နေရာသည် အလွန်တိတိကျကျဖြစ်ရန် မလိုအပ်ပါ။ ဥပမာ- ``places`` layer ထဲရှိ point အများစုသည် မြို့တစ်ခုလုံး သို့မဟုတ် ဆင်ခြေဖုံးများကို ရည်ညွှန်းထားပြီး၊ ထိုကဲ့သို့သော feature များနှင့်သက်ဆိုင်သော point များသည် စကေးအကြီးပေါ်တွင် အတိအကျဖြစ်မည်မဟုတ်ပါ။ အမှန်တကယ်တော့ အတိအကျဖြစ်လွန်းသော point တစ်ခုထားခြင်းသည် မြေပုံဖတ်ရာတွင် မကြာခဏ ရှုပ်ထွေးစေနိုင်ပါသည်။

ဥပမာတစ်ခုပေးရလျှင် ကမ္ဘာ့မြေပုံတစ်ခုပေါ်တွင် European Union (ဥရောပသမဂ္ဂ) အတွက် point တစ်ခုကို Poland နိုင်ငံထဲရှိနေရာတစ်ခုတွင် ချထားသည်ဆိုပါစို့။ မြေပုံဖတ်သည့်သူတစ်ယောက်သည် Poland နိုင်ငံထဲတွင် *European Union* ဟု label တပ်ထားသော point တစ်ခုကို မြင်ပြီး European Union ၏ မြို့တော်သည် Poland နိုင်ငံထဲတွင်ရှိသည်ဟု ထင်ကောင်းထင်နိုင်ပါသည်။

ထိုကဲ့သို့သော နားလည်မှုလွဲခြင်းများမဖြစ်စေရန် point သင်္ကေတများကို ပိတ်ထားပြီး ၎င်းတို့ကို label များဖြင့် အစားထိုးလျှင် အသုံးဝင်ပါသည်။

QGIS တွင် label များကို ၎င်းတို့ရည်ညွှန်းသော point များပေါ်တွင် တိုက်ရိုက်ပုံဖော်ပြသစေရန် နေရာပြောင်းလဲပေးခြင်းဖြင့် လုပ်ဆောင်နိုင်ပါသည်။

#. ``places`` layer အတွက် :guilabel:`Layer Properties` dialog မှ |labelingSingle| :guilabel:`Labels` tab ကိုဖွင့်ပါ။
#. Option list မှ :guilabel:`Placement` option ကို ရွေးပါ။
#. :guilabel:`Offset from point` ခလုတ်ကိုနှိပ်ပါ

   Point maker နှင့်ဆက်စပ်သော label ၏နေရာကို သတ်မှတ်နိုင်သော :guilabel:`Quadrant` option ပေါ်လာပါလိမ့်မည်။ Point ၏ အလယ်တွင် label ကို နေရာထားချင်သောကြောင့် center quadrant ကိုရွေးချယ်ပါ-

   .. figure:: img/quadrant_offset_options.png
      :align: center

#. အရင်ကလုပ်နေကြအတိုင်း layer :guilabel:`Symbology` ကို ပြင်ဆင်ပြီး point သင်္ကေတများကို ဖျောက်ထားပြီး :guilabel:`Marker` ၏ အရွယ်အစားကို ``0.0`` ထားရှိပါ-

   .. figure:: img/hide_point_marker.png
      :align: center

#. :guilabel:`Apply` ကိုနှိပ်လိုက်ပါက အောက်ပါရလာဒ်ကို မြင်တွေ့ရပါလိမ့်မည်-

   .. figure:: img/hide_point_marker_results.png
      :align: center


မြေပုံကို zoom ချုံ့ကြည့်လိုက်လျှင် label အချို့သည် ထပ်နေခြင်းများမဖြစ်စေရန်အတွက် စကေးအကြီးများတွင် ပျောက်သွားသည်ကို တွေ့ရနိုင်ပါသည်။ ထိုသို့ပျောက်သွားခြင်းသည် တစ်ခါတရံတွင် point များစွာရှိသော dataset များဖြင့်လုပ်ကိုင်သောအခါ သင်လိုချင်သည့်ပုံစံဖြစ်နေသော်လည်း အခြားအချိန်များတွင် အသုံးဝင်သော သတင်းအချက်အလက်များ လွတ်သွားပါလိမ့်မည်။ ထိုသို့ဖြစ်ခြင်းကို ကိုင်တွယ်ရန် အခြားဖြစ်နိုင်ခြေတစ်ခုရှိပါသည်၊ ၎င်းကို ဤသင်ခန်းစာ၏ နောက်ထပ်လေ့ကျင့်ခန်းတစ်ခုထဲတွင် သင်ကြားပေးမည်ဖြစ်ပါသည်။ ယခုအတွက်ကတော့ zoom ချုံ့ကြည့်ပြီး toolbar ထဲရှိ |showUnplacedLabel| ခလုတ်ကိုနှိပ်ပြီး ဘာဖြစ်သွားသလဲ ကြည့်ကြည့်ပါ။

:abbr:`★★☆ (Moderate level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- Label များကို စိတ်ကြိုက်ပြင်ဆင်ခြင်း (Try Yourself: Customize the Labels)
--------------------------------------------------------------------------------------------------------------------------------------

* Point marker တစ်ခုနှင့် ``2.0`` မီလီမီတာ label offset (အရွေ့) တစ်ခုရရှိရန် label နှင့် သင်္ကေတ setting များကို reset (မူလအတိုင်းပြန်ထား) လုပ်ပါ။

.. admonition:: အဖြေ
   :class: dropdown

   မြေပုံတွင် marker point များကို ပြသနေသင့်ပြီး label များသည် 2 မီလီမီတာ အရွေ့တွင် ရှိနေသင့်ပါသည်။ Marker များနှင့် label များ၏ style များသည် မြေပုံတွင် ရှင်းလင်းစွာ မြင်ရနေသင့်ပါသည်-

   .. figure:: img/customised_labels_one.png
      :align: center

* မြေပုံကို ``1:100000`` စကေးထားရှိပါ။ :guilabel:`Status Bar` ထဲရှိ :guilabel:`Scale` box ထဲတွင် ရိုက်ထည့်ခြင်းဖြင့် လုပ်ဆောင်နိုင်ပါသည်။ Label များကို ထိုစကေး၌ ကြည့်ရှုရာတွင် သင့်လျော်စေရန် label များကို မွမ်းမံပြင်ဆင်ပါ။

.. admonition:: အဖြေ
   :class: dropdown

   ဤနောက်ဆုံးရလာဒ်ကို ရရှိရန် ဖြစ်နိုင်ချေတစ်ခုရှိပါသည်-

   .. figure:: img/possible_outcome_map.png
      :align: center

   ဤရလာဒ်ကို ရရှိရန်-

   * ဖောင့်အရွယ်အစား ``10`` ကိုအသုံးပြုပါ
   * ပတ်လည် point နေရာချထားမှုအကွာအဝေးကို ``1.5 mm`` အသုံးပြုပါ
   * Marker အရွယ်အစားကို ``3.0 mm`` အသုံးပြုပါ
   * ထို့အပြင် ဤဥပမာသည် :guilabel:`Wrap on character` option ကိုအသုံးပြုထားပါသည်-

     .. figure:: img/wrap_character_settings.png
        :align: center

   * :guilabel:`Wrap on character` တွင် ``space`` တစ်ခုရိုက်ထည့်ပြီး :guilabel:`Apply` နှိပ်ပါ။ ဤဥပမာတွင် အချို့သော နေရာအမည်များသည် အလွန်ရှည်နေပြီး စာကြောင်းများစွာဖြင့် ပေါ်နေပါသည်။ ထိုအတွက် မြေပုံပေါ်တွင် ပိုမိုသင့်လျော်စွာဖြစ်စေရန် setting ကို ရှာတွေ့ကောင်းရှာတွေ့နိုင်ပါသည်။


:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- Line များကို အညွှန်းတပ်ခြင်း (Follow Along: Labeling Lines)
-----------------------------------------------------------------------------------------------------------

ယခုဆိုလျှင် သင့်အနေဖြင့် label တပ်ခြင်းသည် မည်သို့အလုပ်လုပ်သည်ကို သိရှိပြီးဖြစ်ပါသည်။ သို့သော် ပြဿနာတစ်ခုတော့ရှိနေပါသေးသည်။ Point များနှင့် polygon များကို label တပ်ရသည်မှာ လွယ်ကူသော်လည်း line များအတွက်ဆိုလျှင် ဘယ်လိုဖြစ်မလဲ။ Line များကို point များနည်းတူ label တပ်မည်ဆိုလျှင် ရလာဒ်သည် အောက်ပါပုံစံအတိုင်း ဖြစ်နေပါလိမ့်မည်- 

.. figure:: img/bad_street_labels.png
   :align: center

လွယ်လွယ်ကူကူနားလည်စေရန်အတွက် ``roads`` layer label များကို format ပြန်ပြင်ပါမည်။

#. ``places`` layer ကိုဖျောက်ထားပါ
#. အထက်တွင် ``places`` အတွက် လုပ်ဆောင်ခဲ့သည့်အတိုင်း ``roads`` layer အတွက် |labelingSingle| :guilabel:`Single Labels` ကိုထားပေးပါ။
#. Label များများကိုမြင်နိုင်စေရန် စာလုံးဖောင့် :guilabel:`Size` ကို ``10`` ထားပါ
#. |majorUrbanName| မြို့ဧရိယာကို zoom ချဲ့ကြည့်ပါ
#. :guilabel:`Labels` tab ၏ :guilabel:`Placement` tab ထဲတွင် အောက်ပါ setting များကို ရွေးချယ်ပါ-

   .. figure:: img/street_label_settings.png
      :align: center

   စာသား style များသည် default တန်ဖိုးများကိုအသုံးပြုထားပြီး label များသည် ဖတ်ရခက်ခဲနေသည်ကို တွေ့ရပါလိမ့်မည်။ :guilabel:`Text` ကို မီးခိုးရောင်အရင့် သို့မဟုတ် အနက်ရောင် :guilabel:`Color` သုံးပြီး :guilabel:`Buffer` တွင် အဝါဖျော့ :guilabel:`Color` ကိုသုံးကြည့်ပါ။

   မြေပုံသည် စကေးပေါ်မူတည်၍ အောက်ပါပုံစံနှင့်ဆင်တူ ဖြစ်နေပါလိမ့်မည်-

   .. figure:: img/street_label_formatted.png
      :align: center

   အချို့သော လမ်းအမည်များသည် တစ်ကြိမ်ထက်ပိုပြီး ပေါ်နေသည်ကို တွေ့ရလိမ့်မည်ဖြစ်သည်။ ထိုကဲ့သို့ မဖြစ်စေရန်-

#. :guilabel:`Layer Properties` dialog ၏ :guilabel:`Labels` tab ထဲတွင် :guilabel:`Rendering` option ကိုရွေးချယ်ပြီး အောက်တွင်ပြထားသည့်အတိုင်း :guilabel:`Merge connected lines to avoid duplicate labels` ကို select လုပ်ပါ-

   .. figure:: img/merge_lines_option.png
      :align: center

#. :guilabel:`OK` ကိုနှိပ်ပါ။

   အခြားအသုံးဝင်သော function မှာ သတိမထားမိနိုင်လောက်အောင် တိုနေသော feature များအတွက် label များတပ်ခြင်းကို ရှောင်ရှားခြင်းဖြစ်သည်။

#. ထို :guilabel:`Rendering` panel ထဲမှာပင် :guilabel:`Suppress labeling of features smaller than ...` ၏ တန်ဖိုးကို ``5.00 mm`` ဟုသတ်မှတ်ပြီး :guilabel:`Apply` နှိပ်လိုက်သောအခါ ထွက်လာသောရလာဒ်ကို သတိထားကြည့်ပါ။

   အမျိုးမျိုးသော :guilabel:`Placement` setting များကိုလည်း စမ်းကြည့်ပါ။ ယခင်တုန်းက မြင်တွေ့ခဲ့ပြီးသည့်အတိုင်း :guilabel:`Horizontal` option သည် ဤဥပမာအတွက် သိပ်မကောင်းမွန်သောကြောင့် ၎င်းအစား :guilabel:`Curved` option ကိုစမ်းကြည့်ကြပါမည်။

#. :guilabel:`Labels` tab ၏ :guilabel:`Placement` panel ထဲတွင် :guilabel:`Curved` option ကို select လုပ်ပါ။

ရလာဒ်သည် အောက်ပါအတိုင်းဖြစ်သည်-

.. figure:: img/final_street_labels.png
   :align: center

ယခင်ကမြင်တွေ့ခဲ့ရသော label အချို့ ပျောက်သွားသည်ကို တွေ့ရပါမည်။ အဘယ်ကြောင့်ဆိုသော ကွေ့ကောက်နေသောလမ်းများအတိုင်း ချောမွေ့ပြီးဖတ်ရလွယ်အောင် label တပ်ရာတွင်ခက်ခဲသောကြောင့် ဖြစ်သည်။ Label တပ်ရာတွင် လမ်းများအကြားနေရာလွတ်များတွင် ရှိမနေပဲ လမ်းများအတိုင်းခြေရာခံလိုက်သောကြောင့် အခြား label များကို ပိုမိုအသုံးဝင်စေနိုင်ပါသည်။ ပိုအသုံးဝင်မည်ထင်သည့် သို့မဟုတ် ပိုမိုကြည့်ကောင်းမည်ထင်သည့် option များကို အသုံးပြုရန် ဆုံးဖြတ်နိုင်ပါသည်။


:abbr:`★★★ (Advanced level)` လိုက်လုပ်ကြည့်ပါ- Data ဖြင့်သတ်မှတ်နိုင်သော setting များ (Follow Along: Data Defined Settings)
----------------------------------------------------------------------------------------------------------------------------

#. ``roads`` layer အတွက် label တပ်ခြင်းကို ပိတ်လိုက်ပါ
#. ``places`` layer အတွက် label တပ်ခြင်းကို ပြန်ဖွင့်ပါ
#. |openTable| ခလုတ်ကိုနှိပ်ပြီး ``places`` အတွက် attribute ဇယားကိုဖွင့်ပါ

   ယခုအနေဖြင့် စိတ်ဝင်စားသော ``place`` *field* တစ်ခုရှိပြီး ထို field သည် *record* တစ်ခုချင်းစီအတွက် မြို့ပြဧရိယာအမျိုးအစားကို သတ်မှတ်ပေးထားပါသည်။ Label style များအတွက် ထို data ကို အသုံးပြုနိုင်ပါသည်။

#. ``places`` ၏ :guilabel:`Labels` panel ထဲရှိ :guilabel:`Text` panel သို့သွားပါ
#. :guilabel:`Style` ၏အောက်ရှိ Italic text ခလုတ်၏ ဘေးရှိ |dataDefine| ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Expression String Builder` ကိုဖွင့်ရန် :menuselection:`Edit...` ကိုရွေးပါ-

   .. figure:: img/expression_string_builder.png
      :align: center

#. :menuselection:`Fields and Values` အောက်ထဲတွင် ``place`` ကို click နှစ်ချက်နှိပ်ပြီးနောက် :guilabel:`All Unique` ကိုနှိပ်ပါ။ ထိုသို့လုပ်ခြင်းသည် ဤ layer ၏ ``place`` field ထဲရှိ unique (တစ်မျိုးတည်းဖြစ်သော) ဖြစ်သောတန်ဖိုးများအားလုံးကို စာရင်းလုပ်ပေးပါလိမ့်မည်။ Text editor ထဲတွင် ``=`` တစ်ခုထည့်ပြီး ``town`` ပေါ်တွင် click နှစ်ချက်နှိပ်ပါ။

   နောက်တစ်နည်းအားဖြင့် text editor ထဲတွင် ``"place" = 'town'`` ဟု တိုက်ရိုက် စာရိုက်ထည့်နိုင်ပါသည်။

#. :guilabel:`OK` ကို နှစ်ကြိမ်နှိပ်ပါ-

   .. figure:: img/expression_builder_settings.png
      :align: center

``place`` field နှင့် ``town`` ကိုက်ညီသော နေရာများအားလုံးအတွက် label များကို italic (စာလုံးအစောင်း) ဖြင့်ပြသနေသည်ကို သတိပြုကြည့်ပါ။

.. figure:: img/italic_label_result.png
   :align: center


:abbr:`★★★ (Advanced level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- Data ဖြင့်သတ်မှတ်သော setting များကို အသုံးပြုခြင်း (Try Yourself: Using Data Defined Settings)
-----------------------------------------------------------------------------------------------------------------------------------------------------------

.. note:: ဤနေရာတွင် အဆင့်မြင့် label တပ်ခြင်း setting များအချို့ကို သရုပ်ပြရန်အတွက် အနည်းငယ် ရှေ့သို့ကျော်လိုက်ပါမည်။ အဆင့်မြင့် level တွင် သင့်အနေဖြင့် အောက်ပါတို့ကို နားလည်သည်ဟု ယူဆထားပါသည်။ အကယ်၍ နားမလည်လျှင် ဤအပိုင်းကို ချန်ထားခဲ့နိုင်ပြီး နောက်ပိုင်းနားလည်သွားသောအခါမှ ပြန်လာပြီးလုပ်ဆောင်နိုင်ပါသည်။

#. ``places`` အတွက် Attribute ဇယားကို ဖွင့်ပါ
#. |toggleEditing| ခလုတ်ကို နှိပ်ပြီး edit mode ထဲသို့သွားပါ
#. |newAttribute| ခလုတ်နှိပ်ပြီး column အသစ်တစ်ခု ထပ်ထည့်ပါ
#. အောက်ပါအတိုင်း ပြင်ဆင်သတ်မှတ်ပါ-

   .. figure:: img/font_size_column.png
      :align: center

#. မတူညီသော နေရာအမျိုးအစားတစ်ခုချင်းစီအတွက် စိတ်ကြိုက် စာလုံးဖောင့် အရွယ်အစားများကို သတ်မှတ်ရန် ထို column ကိုအသုံးပြုပါ (``place`` field ထဲရှိ key တစ်ခုစီ)

.. admonition:: အဖြေ
   :class: dropdown

   #. Edit mode ထဲတွင်ပဲ ဆက်ရှိနေပြီး ``FONT_SIZE`` တန်ဖိုးများကို သင်နှစ်သက်သလို သတ်မှတ်ပါ။ ဤဥပမာတွင် မြို့ များအတွက် ``16`` ၊ ဆင်ခြေဖုံး များအတွက် ``14`` ၊ နယ်မြေ များအတွက် ``12`` နှင့် ရွာများ အတွက် ``10`` ကိုအသုံးပြုပါသည်။
   #. ပြောင်းလဲမှုများကို သိမ်းဆည်းပြီး edit mode ကိုပိတ်လိုက်ပါ
   #. ``places`` layer အတွက် :guilabel:`Text` formatting option သို့ပြန်သွားပြီး စာလုံးဖောင့် အရွယ်အစား |dataDefine| data defined override dropdown ထဲရှိ :guilabel:`Attribute field` ထဲမှ ``FONT_SIZE`` ကိုရွေးချယ်ပါ-

      .. figure:: img/font_size_override.png
         :align: center

   အထက်ဖော်ပြပါ တန်ဖိုးများကိုအသုံးပြုလျှင် ရလာဒ်သည် အောက်ပါအတိုင်းဖြစ်သင့်ပါသည်-

     .. figure:: img/font_override_results.png
        :align: center


:abbr:`★★★ (Advanced level)` Labeling နှင့်ပတ်သက်သော နောက်ထပ်လုပ်ဆောင်နိုင်ခြေများ (Further Possibilities With Labeling)
-------------------------------------------------------------------------------------------------------------------------

ဤသင်တန်းတွင် option အားလုံးကို ထည့်သွင်းမဖော်ပြနိုင်ပါ၊ သို့သော် :guilabel:`Label` tab တွင် အခြားများစွာသော အသုံးဝင်သည့် function များရှိသည်ကို သိထားပါ။ စကေးအခြေခံသော ပုံဖော်ပြသခြင်းကို သတ်မှတ်ပေးနိုင်ခြင်း၊ layer တစ်ခုထဲရှိ label များအတွက် ပုံဖော်ပြသမှုဦးစားပေးအဆင့်ကို ပြောင်းလဲနိုင်ခြင်းနှင့် layer attribute များကိုအသုံးပြု၍ label option တိုင်းကို သတ်မှတ်ပေးနိုင်ခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။ Label တစ်ခု၏ အလှည့် ၊ XY တည်နေရာနှင့် အခြားဂုဏ်သတ္တိများကိုပင် သတ်မှတ်ပေးနိုင်ပါသည် (attribute field များရှိလျှင်)၊ ထို့နောက် ထိုဂုဏ်သတ္တိများကို :guilabel:`Layer Labeling Options` ခလုတ်နှင့်ကပ်လျက်တွင်ရှိသော tool များကို အသုံးပြု၍ တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်-

|labelingSingle| |showPinnedLabels| |pinLabels|
|showHideLabels| |moveLabel| |rotateLabel|
|changeLabelProperties|

(လိုအပ်သော attribute field များပါရှိပြီး edit mode တွင်ရှိနေလျှင် အဆိုပါ tool များသည် active ဖြစ်လာပါလိမ့်မည်)

Lable တပ်ခြင်းစနစ်၏ ပိုများသောဖြစ်နိုင်ခြေများကို လေ့လာစူးစမ်းကြည့်ပါ။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

တသမတ်တည်းမဟုတ်ပဲ ပြောင်းလဲနိုင်စွမ်းရှိသော (dynamic) label များကို ဖန်တီးရာတွင် layer attribute များကို မည်သို့အသုံးပြုသည်ကို သင်ယူပြီးဖြစ်ပါသည်။ ဤနည်းအားဖြင့် မြေပုံသည် ပိုမို၍ အချက်အလက်များပေးစွမ်းနိုင်လာပြီး ကြည့်ရှုရပိုမိုကောင်းမွန်စေပါသည်။

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
-------------------------------------------------------------------------------

ယခုဆိုလျှင် သင့်အနေဖြင့် attribute များသည် မြေပုံအတွက် အမြင်ဆိုင်ရာကွဲပြားမှုများကို မည်ကဲ့သို့ လုပ်ဆောင်သည်ကို သိရှိပြီးဖြစ်သည်။ Object များ၏သင်္ကေတများ သူ့အလိုလိုပြောင်းလဲရန် attribute များကို မည်သို့အသုံးပြုရမည်ဆိုသည်ကို နောက်လာမည့် သင်ခန်းစာတွင် တွေ့ရမည်ဖြစ်ပါသည်။ 


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |changeLabelProperties| image:: /static/common/mActionChangeLabelProperties.png
   :width: 1.5em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |labelingSingle| image:: /static/common/labelingSingle.png
   :width: 1.5em
.. |majorUrbanName| replace:: Swellendam
.. |moveLabel| image:: /static/common/mActionMoveLabel.png
   :width: 1.5em
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |pinLabels| image:: /static/common/mActionPinLabels.png
   :width: 1.5em
.. |rotateLabel| image:: /static/common/mActionRotateLabel.png
   :width: 1.5em
.. |showHideLabels| image:: /static/common/mActionShowHideLabels.png
   :width: 1.5em
.. |showPinnedLabels| image:: /static/common/mActionShowPinnedLabels.png
   :width: 1.5em
.. |showUnplacedLabel| image:: /static/common/mActionShowUnplacedLabel.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
