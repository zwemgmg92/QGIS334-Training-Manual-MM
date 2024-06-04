သင်ခန်းစာ- တသမတ်တည်းမဟုတ်ပဲပြောင်းလဲနိုင်သော ပုံထုတ်အပြင်အဆင်တစ်ခုဖန်တီးခြင်း (Lesson: Creating a Dynamic Print Layout)
========================================================================================================================

ယခုဆိုလျှင် အခြေခံမြေပုံတစ်ခု ဖန်တီးသည့်နည်းလမ်းကိုသင်ကြားပြီးဖြစ်ပါသည်၊ နောက်တစ်ဆင့်အနေဖြင့် မြေပုံ နယ်ပယ်အကျယ်အဝန်း (extent) နှင့် စာမျက်နှာ property များပေါ်မူတည်ပြီး ပြောင်းလဲနိုင်သော မြေပုံ layout တစ်ခုကို ဖန်တီးမည်ဖြစ်သည်၊ ဥပမာ-  စာမျက်နှာ၏အရွယ်အစားကို ပြောင်းလဲလိုက်သောအခါ။ ထို့အပြင် ဖန်တီးသည့်ရက်စွဲသည်လည်း အလိုအလျှောက် ပြောင်းလဲသွားမည်ဖြစ်သည်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- တသမတ်တည်းမဟုတ်ပဲပြောင်းလဲနိုင်သော မြေပုံမြင်ကွင်းများ ဖန်တီးခြင်း (Follow Along: Creating the dynamic map canvas)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------

#. ESRI Shapefile format ဖြင့် dataset များဖြစ်သော :file:`protected_areas.shp` ၊ :file:`places.shp` ၊ :file:`rivers.shp`
   နှင့် :file:`water.shp` တို့ကို မြေပုံမြင်ကွင်း ထဲသို့ထည့်သွင်းပြီး ၎င်းတို့၏ဂုဏ်သတ္တိများကို ကြိုက်နှစ်သက်သလိုပြင်ဆင်ပါ။
#. After everything is rendered and symbolized to your liking,
   click the |newLayout| :sup:`New Print Layout` icon in the :guilabel:`Project` toolbar
   or choose :menuselection:`Project -->` |newLayout| :menuselection:`New Print Layout`.
   You will be prompted to choose a title for the new print layout.
#. အားလုံးကို စိတ်ကြိုက် သင်္ကေတဆိုင်ရာများထည့်သွင်းကာ ပုံဖော်ပြသပြီးပါက :guilabel:`Project` toolbar ထဲရှိ |newLayout| :sup:`New Print Layout` icon ကိုနှိပ်ပါ၊ သို့မဟုတ် :menuselection:`Project -->` |newLayout| :menuselection:`New Print Layout` ကိုရွေးချယ်ပါ။ Print layout အသစ်တစ်ခု ခေါင်းစဉ်တစ်ခု ရွေးချယ်ခိုင်းပါလိမ့်မည်။
#. Swellendam ၊ South Africa အနီးနားရှိ ဒေသ၏ မြေပုံတစ်ခုနှင့် ခေါင်းစဉ်တစ်ခုပါဝင်သော မြေပုံ layout တစ်ခုကိုဖန်တီးလိုခြင်းဖြစ်ပါသည်။ Layout သည် ဘေးအနားသပ် (margin) 7.5 မီလီမီတာရှိပြီး ခေါင်းစဉ်သည် 36 မီလီမီတာ အမြင့် ရှိသင့်ပါသည်။
#. Canvas ပေါ်တွင် ``main map`` ဟုခေါ်သော မြေပုံ item တစ်ခုကို ဖန်တီးပြီး :guilabel:`Layout` panel သို့သွားပါ။ :guilabel:`Variables` section သို့ရောက်အောင်သွားပြီး :guilabel:`Layout` အပိုင်းကို ရှာပါ။ တသမတ်တည်းမဟုတ်ပဲပြောင်းလဲနိုင်သော (dynamic) print layout တွင် အသုံးပြုနိုင်သော variable များအချို့ကို တွေ့ရပါမည်။ :guilabel:`Layout` panel သို့သွားပြီး :guilabel:`Variables` section သို့ သွားပါ။ ပထမဆုံး variable သည် margin ကိုသတ်မှတ်ပါလိမ့်မည်။ |symbologyAdd| ခလုတ်ကိုနှိပ်ပြီး name တွင် ``sw_layout_margin`` ဟုရိုက်ထည့်ပါ။ Value တွင် ``7.5`` ဟုသတ်မှတ်ပါ။ |symbologyAdd| ခလုတ်ကို ထပ်နှိပ်ပြီး name တွင် ``sw_layout_height_header`` ဟုရိုက်ထည့်ပါ။ Value တွင် ``36`` ဟုသတ်မှတ်ပါ။
#. ယခုဆိုလျှင် Variable များကိုအသုံးပြုပြီး မြေပုံ canvas ၏ တည်နေရာနှင့်အရွယ်အစားကို အလိုအလျှောက်ဖန်တီးရန်အသင့်ဖြစ်နေပါသည်။ မြေပုံ item ကို select လုပ်ထားပြီး :guilabel:`Item Properties` panel သို့သွားပြီး :guilabel:`Position and Size` section ကိုဖွင့်ပါ။ :guilabel:`X` အတွက် |dataDefineExpressionOn| :sup:`Data defined override` ကိုနှိပ်ပြီး :guilabel:`Variables` entry မှ ``@sw_layout_margin`` ကိုရွေးချယ်ပါ။
#. :guilabel:`Y` အတွက် |dataDefineExpressionOn| :sup:`Data defined override` ကိုနှိပ်ပြီး :guilabel:`Edit...` ကိုရွေးချယ်ပြီး formula ထဲတွင် အောက်ပါကို ရိုက်ထည့်ပါ-::

     to_real(@sw_layout_margin) + to_real(@sw_layout_height_header)

#. :guilabel:`Width` နှင့် :guilabel:`Height` အတွက် variable များကိုအသုံးပြုပြီး မြေပုံ item ၏အရွယ်အစားကို ဖန်တီးနိုင်ပါသည်။ :guilabel:`Width` အတွက် |dataDefineExpressionOn| :sup:`Data defined override` ကိုနှိပ်ပြီး :guilabel:`Edit ...` ကိုထပ်မံရွေးချယ်ပါ။ Formula ထဲတွင် အောက်ပါကို ဖြည့်ပါ-::

     @layout_pagewidth - @sw_layout_margin * 2

   :guilabel:`Height` အတွက် |dataDefineExpressionOn| :sup:`Data defined override` ကိုနှိပ်ပြီး :guilabel:`Edit ...` ကိုရွေးချယ်ပါ။ Formulat ထဲတွင် အောက်ပါကို ဖြည့်ပါ-::

     @layout_pageheight -  @sw_layout_height_header -  @sw_layout_margin * 2

#. အဓိက မြေပုံ canvas extent ၏ ကိုဩဒိနိတ်များပါဝင်သော grid (မြေပုံတွင်အကွက်ချထားသော လေးထောင့်ကွက်) တစ်ခုကိုလည်း ဖန်တီးပါမည်။ :guilabel:`Item Properties` သို့ထပ်မံသွားပြီး :guilabel:`Grids` section ကိုရွေးချယ်ပါ။ |symbologyAdd| ခလုတ်ကို နှိပ်ပြီး grid တစ်ခုကို ထည့်သွင်းပါ။ :guilabel:`Modify grid ...` ပေါ်တွင် နှိပ်ပြီး :guilabel:`X` ၊ :guilabel:`Y` နှင့် :guilabel:`Offset` အတွက် :guilabel:`Interval` ကို QGIS အဓိက canvas ထဲတွင် ရွေးထားသော မြေပုံစကေးအရ သတ်မှတ်ပါ။ :guilabel:`Grid type` ဖြစ်သော :guilabel:`Cross` သည် ယခုလုပ်မည့် သင်ခန်းစာအတွက် အလွန်သင့်တော်ပါသည်။

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- တသမတ်တည်းမဟုတ်ပဲပြောင်းလဲနိုင်သော ခေါင်းစီး ကိုဖန်တီးခြင်း (Follow Along: Creating the dynamic header)
------------------------------------------------------------------------------------------------------------------------------------------------------

#. |addBasicShape| :sup:`Add Shape` ခလုတ်ကိုအသုံးပြုပြီး ခေါင်းစီး ပါဝင်မည့် ထောင့်မှန်စတုဂံတစ်ခုကို ထည့်သွင်းပါ။ :guilabel:`Items` panel ထဲတွင် ``header`` အမည်ကိုရိုက်ထည့်ပါ။
#. :guilabel:`Item Properties` သို့သွားပြီး :guilabel:`Position and Size` section ကိုဖွင့်ပါ။ |dataDefineExpressionOn| :sup:`Data defined override` ကိုအသုံးပြုပြီး :guilabel:`X` အတွက်သာမက :guilabel:`Y` အတွက်ပါ ``sw_layout_margin`` variable ကိုရွေးချယ်ပါ။ :guilabel:`Width` ကို အောက်ပါ expression ဖြင့် သတ်မှတ်ပါလိမ့်မည်-::

     @layout_pagewidth - @sw_layout_margin * 2

   :guilabel:`Height` ကို ``sw_layout_height_header`` variable ဖြင့်သတ်မှတ်ပါလိမ့်မည်။
#. ခေါင်းစီးကို မတူညီသော အပိုင်းများအဖြစ်သို့ ခွဲခြားရန် ရေပြင်ညီ မျဉ်းတစ်ခုနှင့် ဒေါင်လိုက်မျဉ်း နှစ်ခုကို |addNodesShape| :sup:`Add Node Item` ကိုအသုံးပြု၍ ထည့်သွင်းပါမည်။ ရေပြင်ညီမျဉ်းတစ်ခုနှင့် ဒေါင်လိုက်မျဉ်းနှစ်ခုကို ဖန်တီးပြီး ၎င်းတို့ကို ``Horizontal line`` ၊ ``Vertical line 1`` ``Vertical line 2`` ဟုအမည်ပေးပါ။

   #. ရေပြင်ညီမျဉ်းအတွက်-

      #. :guilabel:`X` ကို ``sw_layout_margin`` variable သတ်မှတ်ပါ
      #. :guilabel:`Y` အတွက် expression ကို အောက်ပါအတိုင်းသတ်မှတ်ပါ-::

           @sw_layout_margin + 8

      #. :guilabel:`Width` အတွက် expression ကို အောက်ပါအတိုင်းသတ်မှတ်ပါ-::

           @layout_pagewidth -  @sw_layout_margin * 3 - 53.5

   #. ပထမဒေါင်လိုက်မျဉ်းအတွက်-

      #. :guilabel:`X` အတွက် expression ကို အောက်ပါအတိုင်းသတ်မှတ်ပါ-::

           @layout_pagewidth - @sw_layout_margin * 2 - 53.5

      #. :guilabel:`Y` ကို ``sw_layout_margin`` variable သတ်မှတ်ပါ
      #. အမြင့် (Height) သည် ဖန်တီးထားသော ခေါင်းစီးနှင့်အတူတူဖြစ်ရပါမည်၊ ထို့ကြောင့် :guilabel:`Height` ကို ``sw_layout_height_header`` variable သတ်မှတ်ပါ။

   #. ဒုတိယ ဒေါင်လိုက်မျဉ်းကို ပထမဒေါင်လိုက်မျဉ်း၏ ဘယ်ဘက်တွင် နေရာချထားပါသည်။

      #. :guilabel:`X` အတွက် expression ကို အောက်ပါအတိုင်းသတ်မှတ်ပါ-::

           @layout_pagewidth - @sw_layout_margin * 2 - 83.5

      #. :guilabel:`Y` ကို ``sw_layout_margin`` variable သတ်မှတ်ပါ
      #. အမြင့် သည် အခြား ဒေါင်လိုက်မျဉ်း၏အမြင့်နှင့်အတူတူဖြစ်ရပါမည်၊ ထို့ကြောင့် :guilabel:`Height` ကို ``sw_layout_height_header`` variable သတ်မှတ်ပါ။

   အောက်ပါပုံသည် ကျွန်ုပ်တို့ဖန်တီးထားသော dynamic layout ၏ ဖွဲ့စည်းပုံကို ပြသပါသည်။ မျဉ်းများဖြင့် ဖန်တီးထားသော ဧရိယာထဲတွင် element အချို့ ဖြည့်သွင်းပါမည်။

.. figure:: img/dynamic_layout_structure.png
   :align: center

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- Dynamic header အတွက် label များဖန်တီးခြင်း (Follow Along: Creating labels for the dynamic header)
-------------------------------------------------------------------------------------------------------------------------------------------------

#. QGIS project ၏ ခေါင်းစဉ်ကို အလိုအလျှောက်ထည့်သွင်းနိုင်ပါသည်။ ခေါင်းစဉ်ကို :guilabel:`Project Properties` ထဲတွင် သတ်မှတ်ထားပါသည်။ |label| :sup:`Add Label` ခလုတ်ဖြင့် label တစ်ခုထည့်သွင်းပြီး ``project title (variable)`` အမည်ကို ထည့်ပါ။ :guilabel:`Items Properties` Panel ၏ :guilabel:`Main Properties` ထဲတွင် အောက်ပါ expression ကို ရိုက်ထည့်ပါ-::

     [%@project_title%]

   Label ၏တည်နေရာကို သတ်မှတ်ပါ။

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 3

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 0.25

   #. :guilabel:`Width` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @layout_pagewidth - @sw_layout_margin *2 - 90

   #. :guilabel:`Height` အတွက် ``11.25`` ကိုရိုက်ထည့်ပါ။

   :guilabel:`Appearance` အောက်တွင် စာလုံးဖောင့် အရွယ်အစား (Font size) ကို 16 pt သတ်မှတ်ပါ။

#. ဒုတိယ label တွင် မြေပုံအတွက် ဖော်ပြချက် (description) တစ်ခုပါဝင်ပါလိမ့်မည်။ Label တစ်ခုထပ်မံထည့်သွင်းပြီး ``map description`` ဟုအမည်ပေးပါ။ :guilabel:`Main Properties` ထဲတွင် ``map description`` ဟူသော စာလုံးကို ရိုက်ထည့်ပါ။ :guilabel:`Main Properties` ထဲတွင် အောက်ပါကိုလည်း ထည့်သွင်းပါမည်-::

     printed on: [%format_date(now(),'dd.MM.yyyy')%]

   ဤတွင် ``Date and Time`` function နှစ်ခုကို အသုံးပြုထားပါသည် (``now`` နှင့် ``format_date``)

   Label ၏တည်နေရာကို သတ်မှတ်ပါ။

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 3

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 11.5

#. တတိယ label တွင် သင့်အဖွဲ့အစည်းအကြောင်း အချက်အလက်များ ပါဝင်ပါလိမ့်မည်။ ဦးစွာ  :guilabel:`Item Properties` ၏ :guilabel:`Variables` menu ထဲတွင် variable အချို့ကို ဖန်တီးပါမည်။ :guilabel:`Layout` menu သို့သွားပြီး |symbologyAdd| ခလုတ်ကို တစ်ကြိမ်စီနှိပ်ပြီး ``o_department`` ၊ ``o_name`` ၊ ``o_adress`` နှင့် ``o_postcode`` ဟူသော အမည်များကို ရိုက်ထည့်ပါ။ ဒုတိယ row ထဲတွင် သင့်အဖွဲ့အစည်းအကြောင်း အချက်အလက်ကို ထည့်သွင်းပါ။ ထို variable များကို :guilabel:`Main Properties` section ထဲတွင် အသုံးပြုပါမည်။

   :guilabel:`Main Properties` ထဲတွင် အောက်ပါတို့ကို ရိုက်ထည့်ပါ-::

     [% @o_name %]
     [% @o_department %]
     [% @o_adress %]
     [% @o_postcode %]

   Label ၏ တည်နေရာကို သတ်မှတ်ပါ။

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @layout_pagewidth - @sw_layout_margin - 49.5

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 15.5

   #. :guilabel:`Width` အတွက် ``49.00`` ကိုအသုံးပြုပါ
   #. :guilabel:`Height` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_height_header - 15.5

.. figure:: img/dynamic_layout_organisation.png

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- Dynamic header ထဲသို့ ဓာတ်ပုံများ ထည့်သွင်းခြင်း (Follow Along: Adding pictures to the dynamic header)
------------------------------------------------------------------------------------------------------------------------------------------------------

#. |addImage| :sup:`Add Picture` ခလုတ်ကိုအသုံးပြုပြီး ``organisation information`` ဆိုသည့် label ၏အပေါ်တွင် ဓာတ်ပုံတစ်ခု ထည့်သွင်းပါ။  ``organisation logo`` ဆိုသည့်အမည်ပေးပြီး logo ၏ တည်နေရာနှင့်အရွယ်အစားကို သတ်မှတ်ပါ-

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @layout_pagewidth - @sw_layout_margin - 49.5

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 3.5

   #. :guilabel:`Width` အတွက် ``39.292`` ကိုအသုံးပြုပါ
   #. :guilabel:`Height` အတွက် ``9.583`` ကိုအသုံးပြုပါ

   သင့်အဖွဲ့အစည်း၏ logo ကိုထည့်သွင်းရန် အဆိုပါ logo ကို home directory အောက်တွင် သိမ်းဆည်းထားရမည်ဖြစ်ပြီး ထိုဖိုင်လမ်းကြောင်းကို :menuselection:`Main Properties --> Image Source` အောက်တွင် ထည့်သွင်းရမည်ဖြစ်သည်။
#. Layout တွင် မြောက်အရပ်ပြမြား (north arrow) လိုအပ်နေပါသေးသည်။ |northArrow| :sup:`Add North Arrow` ကိုအသုံးပြုပြီး ထည့်သွင်းပါမည်။ Default north arrow ကို အသုံးပြုပါမည်။ တည်နေရာသတ်မှတ်ပေးပါမည်-

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @layout_pagewidth - @sw_layout_margin * 2 - 78

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 9

   #. :guilabel:`Width` အတွက် ``21.027`` ကိုအသုံးပြုပါ
   #. :guilabel:`Height` အတွက် ``21.157`` ကိုအသုံးပြုပါ

:abbr:`★★☆ (Moderate level)` လိုက်လုပ်ကြည့်ပါ- Dynamic header ၏ စကေးဘား ဖန်တီးခြင်း (Follow Along: Creating the scalebar of the dynamic header)
------------------------------------------------------------------------------------------------------------------------------------------------

#. |scaleBar| :sup:`Add Scale Bar` ကိုနှိပ်ပြီး Header ထဲတွင် စကေးဘား တစ်ခုထည့်သွင်းကာ ၎င်းကို north arrow ၏အထက် ထောင့်မှန်စတုဂံထဲတွင် နေရာချထားပါ။ :guilabel:`Main Properties` အောက်ရှိ :guilabel:`Map` ထဲတွင် ``main map(Map 1)`` ကိုရွေးချယ်ပါ။ ဆိုလိုသည်မှာ QGIS main canvas ထဲတွင် သင်ရွေးချယ်လိုက်သော extent အတိုင်း စကေးသည် အလိုအလျှောက် ပြောင်းလဲသွားမည်ဖြစ်သည်။  :guilabel:`Style` ကို :guilabel:`Numeric` ရွေးပါ။ ဆိုလိုသည်မှာ စကေးဘားတစ်ခု မပါပဲ ရိုးရိုးစကေး တစ်ခုကို ထည့်သွင်းမည်ဖြစ်သည်။ စကေး၏ တည်နေရာနှင့် အရွယ်အစားကို သတ်မှတ်ရန် လိုအပ်ပါသေးသည်။

   #. :guilabel:`X` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @layout_pagewidth - @sw_layout_margin * 2 - 78

   #. :guilabel:`Y` အတွက် အောက်ပါ expression ကိုအသုံးပြုပါ-::

        @sw_layout_margin + 1

   #. :guilabel:`Width` အတွက် ``25`` ကိုအသုံးပြုပါ
   #. :guilabel:`Height` အတွက် ``8`` ကိုအသုံးပြုပါ
   #. ``Reference point`` ကို အလယ်ဗဟို (center) တွင် နေရာချထားပါ။

သင့်အနေဖြင့် ပထမဆုံး dynamic မြေပုံ layout ကို ဖန်တီးပြီးဖြစ်ပါသည်။ Layout ကို ကြည့်ကြည့်ပြီး လိုချင်သည့်ပုံစံအတိုင်း ဖြစ်/မဖြစ် စစ်ဆေးကြည့်ပါ။ :guilabel:`page properties` ကို ပြောင်းလဲလိုက်တိုင်း dynamic မြေပုံ layout သည် အလိုအလျှောက် လိုက်လံပြောင်းလဲမည်ဖြစ်သည်။ ဥပမာ- စာမျက်နှာအရွယ်အစားကို DIN A4 မှ DIN A3 သို့ပြောင်းလဲလျှင် |refresh| :sup:`Refresh view` ခလုတ်ကို နှိပ်လိုက်ပါက စာမျက်နှာဒီဇိုင်း ပြောင်းလဲသွားပါမည်ဖြစ်သည်။

.. figure:: img/dynamic_layout.png
   :align: center

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့် စာမျက်နှာတွင် သင့်အနေဖြင့် assignment (အိမ်စာ) တစ်ခုပြီးအောင် လုပ်ရပါမည်။ ထိုသို့လုပ်ခြင်းဖြင့် သင့်လေ့လာခဲ့ပြီးသမျှ နည်းလမ်းများကို လေ့ကျင့်နိုင်မည်ဖြစ်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addBasicShape| image:: /static/common/mActionAddBasicShape.png
   :width: 1.5em
.. |addImage| image:: /static/common/mActionAddImage.png
   :width: 1.5em
.. |addNodesShape| image:: /static/common/mActionAddNodesShape.png
   :width: 1.5em
.. |dataDefineExpressionOn| image:: /static/common/mIconDataDefineExpressionOn.png
   :width: 1.5em
.. |label| image:: /static/common/mActionLabel.png
   :width: 1.5em
.. |newLayout| image:: /static/common/mActionNewLayout.png
   :width: 1.5em
.. |northArrow| image:: /static/common/north_arrow.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |scaleBar| image:: /static/common/mActionScaleBar.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
