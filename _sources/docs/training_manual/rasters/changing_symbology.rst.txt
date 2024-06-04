သင်ခန်းစာ - Raster သင်္ကေတ ပြောင်းလဲခြင်း (Lesson: Changing Raster Symbology)
==============================================================================

Raster data များအားလုံးသည် ကောင်းကင်ဓာတ်ပုံများမဟုတ်ကြပါ။ အခြား raster data ပုံစံအမျိုးမျိုးရှိပြီး၊ ထို raster တော်တော်များများကို ကောင်းမွန်စွာ မြင်ရနိုင်ပြီးအသုံးဝင်နိုင်စေရန် သင်္ကေတများပြောင်းလဲပေးရန် လိုအပ်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Raster layer တစ်ခုအတွက် သင်္ကေတပြောင်းလဲရန်။

:abbr:`★☆☆ (Basic level)` မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ- (Try Yourself:)
-------------------------------------------------------------------------

#. :guilabel:`Browser` Panel ကိုအသုံးပြုပြီး :file:`exercise_data/raster/SRTM/` အောက်တွင်ရှိသော :file:`srtm_41_19.tif` ကိုထည့်သွင်းပါ။
#. :guilabel:`Layers panel` ထဲရှိ အဆိုပါ layer ကို right-click နှိပ်ပြီး :guilabel:`Zoom to Layer` ကိုရွေးကာ layer ၏ extent ကို zoom ချဲ့ကြည့်ပါ။

ဤ dataset သည် *Digital Elevation Model (DEM)* တစ်ခုဖြစ်ပါသည်။ မြေမျက်နှာပြင် အနိမ့်အမြင့်ကို ဖော်ပြသော မြေပုံတစ်ခုဖြစ်ပြီး၊ ဥပမာအားဖြင့် တောင်တန်းများနှင့် ချိုင့်ဝှမ်းများ မည်သည့်နေရာတွင် ရှိသည်ကို မြင်ရနိုင်ပါသည်။

ယခင်သင်ခန်းစာတွင်သုံးခဲ့သော dataset ၏ pixel တစ်ခုချင်းစီတွင် အရောင်အချက်အလက်များပါဝင်ပြီး ယခု *DEM* တွင် pixel တစ်ခုချင်းစီသည် အမြင့် တန်ဖိုးများပါဝင်ပါသည်။

DEM ကိုထည့်သွင်းလိုက်သည်နှင့် grayscale (မီးခိုးရောင်စကေး) ပုံစံဖြင့် ပြသနေသည်ကို တွေ့ရပါလိမ့်မည်-

.. figure:: img/greyscale_dem.png
   :align: center

QGIS သည် image ၏ pixel တန်ဖိုးများကို အမြင်ပိုင်းဆိုင်ရာအတွက် အလိုအလျှောက် stretch (အရောင်တစ်ဆက်တည်း) ပြုလုပ်ပေးပါသည်။ ၎င်း၏ အလုပ်လုပ်ပုံကို နောက်ပိုင်းတွင် ပိုမိုလေ့လာသွားမည်ဖြစ်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Raster Layer သင်္ကေတ ပြောင်းလဲခြင်း (Follow Along: Changing Raster Layer Symbology)
---------------------------------------------------------------------------------------------------------------------------------

Raster သင်္ကေတကို ပြောင်းလဲရန် မတူညီသောရွေးချယ်စရာ ၂ ခုရှိပါသည်-

#. :guilabel:`Layer Properties` dialog အတွင်းတွင် ရှိပါသည်။ Layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Properties` option ကိုရွေးချယ်ခြင်းအားဖြင့် dialog ကိုဖွင့်ပါ၊ ထို့နောက် :guilabel:`Symbology` tab သို့ပြောင်းပါ။
#. :guilabel:`Layers` panel ၏ ညာဘက်အပေါ်ရှိ |symbology| :sup:`Open the Layer Styling panel` ခလုတ်ကိုနှိပ်ခြင်းဖြင့် (ကီးဘုတ် shortcut :kbd:`F7`) :guilabel:`Layer Styling` panel ကိုပွင့်စေပြီး |symbology| :sup:`Symbology` tab သို့ပြောင်းနိုင်ပါသည်။

သင်နှစ်သက်ရာနည်းလမ်းကို ရွေးချယ်ပါ။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Singleband gray (Follow Along: Singleband gray)
---------------------------------------------------------------------------------------------

Raster ဖိုင်တစ်ခုသည် ယခင်သင်ခန်းစာမှာကဲ့သို့ ဓာတ်ပုံတစ်ခုမဟုတ်လျှင် ၎င်းကို ထည့်သွင်းသောအခါ default style ကို grayscale gradient အဖြစ် ပြသပါလိမ့်မည်။  

ထို renderer (ပုံဖော်ပြသပေးသည့်အရာ) တွင်ပါဝင်သည့် feature အချို့ကို လေ့လာကြည့်ရအောင်။

.. figure:: img/dem_layer_properties.png
   :align: center

Default :guilabel:`Color gradient` ကို ``Black to white`` အဖြစ်သတ်မှတ်ပါသည်၊ ဆိုလိုသည်မှာ pixel တန်ဖိုးအနိမ့်များသည် အနက်ရောင် ဖြစ်ပြီး pixel တန်ဖိုးအမြင့်များသည် အဖြူရောင်ဖြစ်သည်။ အဆိုပါ setting ကို ``White to black`` သို့ပြောင်းလဲကြည့်ပြီး ရလာဒ်ကို ကြည့်ပါ။

အလွန်အရေးကြီးသည့်အရာမှာ :guilabel:`Contrast enhancement` parameter ဖြစ်သည်၊ default အနေဖြင့် ``Stretch to MinMax`` အဖြစ်သတ်မှတ်ပါသည်၊ ဆိုလိုသည်မှာ pixel တန်ဖိုးများကို အနိမ့်ဆုံးတန်ဖိုးနှင့် အမြင့်ဆုံးတန်ဖိုးများသို့ stretch လုပ်ပေးခြင်းဖြစ်သည်။

Enhancement ပြုလုပ်ထားသည့်ပုံ (ဘယ်ဘက်) နှင့် မပြုလုပ်ထားသည့်ပုံ (ညာဘက်) ၏ကွာခြားချက်ကို ကြည့်ပါ-

.. figure:: img/enhancement.png
   :align: center

Stretch အတွက် အသုံးပြုသင့်သော အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများမှာ :guilabel:`Min / Max Value Settings` အောက်တွင် လက်ရှိရှိနေသော တန်ဖိုးများဖြစ်သည်။ အနိမ့်ဆုံးနှင့်အမြင့်ဆုံးတန်ဖိုးများကို တွက်ချက်ပြီး stretch အတွက်အသုံးပြုရန် နည်းလမ်းများစွာရှိပါသည်-

#. **User Defined** - :guilabel:`Min` နှင့် :guilabel:`Max` တန်ဖိုးများကို ကိုယ်တိုင် ရိုက်ထည့်ပေးခြင်းဖြစ်သည်။
#. **Cumulative count cut** - အလွန် နိမ့်သော သို့မဟုတ် အလွန် မြင့်သောတန်ဖိုးများ ရှိသောအခါ အသုံးဝင်ပါသည်။ ၎င်းသည် အဆိုပါ တန်ဖိုးများ၏ ``2%`` (သို့မဟုတ် သင်ရွေးချယ်သောတန်ဖိုး) ကို *ဖြတ်* ပေးပါသည်။
#. **Min / max** - Raster ၏ *အစစ်အမှန်* သို့မဟုတ် *ခန့်မှန်းထားသော* အနိမ့်ဆုံးနှင့်အမြင့်ဆုံးတန်ဖိုးများ
#. **Mean +/- standard deviation** - Mean တန်ဖိုးနှင့် Standard deviation (စံတိမ်းချက်) တန်ဖိုးအရ တွက်ချက်ပေးပါလိမ့်မည်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Singleband pseudocolor (Follow Along: Singleband pseudocolor)
-----------------------------------------------------------------------------------------------------------

Grayscale များသည် raster layer များအတွက် အမြဲတမ်းသင့်တော်သည့် style များမဟုတ်ပါ။ DEM အား ပိုမိုအရောင်စုံလင်အောင် စမ်းကြည့်ကြပါမည်။

* :guilabel:`Render type` တွင် :guilabel:`Singleband pseudocolor` သို့ပြောင်းပါ။ Default ထည့်သွင်းပေးသော အရောင်ကို မကြိုက်လျှင် အခြား :guilabel:`Color ramp` ကိုရွေးချယ်ပါ။
* အရောင် အတန်းအစားခွဲခြားမှုအသစ်တစ်ခု ထုတ်ပေးရန် :guilabel:`Classify` ခလုတ်ကိုနှိပ်ပါ
* ထိုအရောင်ကို DEM တွင် အသုံးပြုရန် :guilabel:`OK` ကိုနှိပ်ပါ

.. figure:: img/dem_pseudocolor_properties.png
   :align: center

Raster ကို အောက်ပါပုံစံအတိုင်း မြင်တွေ့ရပါလိမ့်မည်-

.. figure:: img/pseudocolor_raster.png
   :align: center


Raster တန်ဖိုးနိမ့်သော ဧရိယာများကို အပြာရောင်ဖြင့်ပြသပြီး တန်ဖိုးမြင့်သောနေရာများကို အနီရောင်ဖြင့် ပြသနေသည်ကို မြင်တွေ့ရပါမည်။


လိုက်လုပ်ကြည့်ပါ - အလင်းဖောက်နှုန်း ပြောင်းလဲခြင်း (Follow Along: Changing the transparency)
---------------------------------------------------------------------------------------------

တစ်ခါတရံတွင် raster layer တစ်ခုလုံး၏ အလင်းဖောက်နှုန်း (transparency) ကို ပြောင်းလဲခြင်းအားဖြင့် အဆိုပါ raster မှ ဖုံးအုပ်နေသော အခြား layer များကို မြင်တွေ့နိုင်ပြီး study area ကို ကောင်းစွာ နားလည်သဘောပေါက်စေနိုင်ပါသည်။

Raster layer ၏ အလင်းဖောက်နှုန်း ကို ပြောင်းလဲရန် :guilabel:`Transparency` tab သို့သွားပြီး :guilabel:`Global Opacity` slider ကိုလျော့ချပါ-

.. figure:: img/global_transparency.png
   :align: center


ပိုမိုစိတ်ဝင်စားစရာကောင်းသည်မှာ အချို့ pixel တန်ဖိုးများအတွက် အလင်းဖောက်နှုန်း ကိုပြောင်းလဲခြင်းဖြစ်သည်။ ဥပမာ- ယခုအသုံးပြုခဲ့သော raster ထဲတွင် ထောင့်များ၌ အရောင်တစ်မျိုးတည်းဖြစ်နေသည်ကို မြင်တွေ့နိုင်ပါသည်။ အဆိုပါ pixel များကို transparent အနေဖြင့် သတ်မှတ်ရန် :guilabel:`Transparency` tab ထဲရှိ :guilabel:`Custom Transparency Options` သို့သွားပါ။

* |symbologyAdd| :sup:`Add values manually` ခလုတ်ကို နှိပ်ခြင်းဖြင့် တန်ဖိုးအပိုင်းအခြားတစ်ခုကို ထည့်သွင်းနိုင်ပြီး ၎င်းတို့၏ အလင်းဖောက်မှု ရာခိုင်နှုန်းကို သတ်မှတ်ပေးနိုင်ပါသည်။
* တစ်ခုထဲသော တန်ဖိုးများအတွက် |contextHelp| :sup:`Add values from display` ခလုတ်သည် ပိုမိုအသုံးဝင်ပါသည်
* |contextHelp| :sup:`Add values from display` ခလုတ်ကိုနှိပ်ပါ။ Dialog ပျောက်သွားမည်ဖြစ်ပြီး မြေပုံနှင့် အပြန်အလှန်လုပ်ဆောင်နိုင်မည်ဖြစ်သည်။
* DEM ၏ ထောင့်၌ရှိသော အရောင်ပေါ်တွင် click နှိပ်ပါ
* Transparency ဇယားတွင် click လုပ်ထားသော တန်ဖိုးများဖြင့် ဖြည့်သွားမည်ကို တွေ့ရပါလိမ့်မည်-

  .. figure:: img/click_transparency.png
     :align: center

* Dialog ကိုပိတ်ရန် :guilabel:`OK` ကိုနှိပ်ပြီး ပြောင်းလဲမှုများကို ကြည့်ပါ။

  .. figure:: img/good_raster.png
     :align: center

  ယခုဆိုလျှင် ထောင့်များတွင် 100% အလင်းဖောက်သွားမည်ဖြစ်ပါသည်။


နိဂုံးချုပ် (In Conclusion)
----------------------------------------------------------------------

အထက်ဖော်ပြပါများသည် Raster သင်္ကေတများဆိုင်ရာ အခြေခံ function အချို့ဖြစ်ကြပါသည်။ QGIS တွင် အခြား option များစွာရှိပါသည်၊ ၎င်းတို့မှာ paletted/unique တန်ဖိုးများအသုံးပြု၍ layer တစ်ခုအား သင်္ကေတထည့်ခြင်း၊ multispectral (ရောင်စဉ်တန်းများစွာပါသော) image တစ်ခုထဲရှိ band အမျိုးမျိုးကို အရောင်အမျိုးမျိုးဖြင့် ဖော်ပြခြင်း၊ သို့မဟုတ် အလိုအလျှောက် hillshade effect တစ်ခုပြုလုပ်ခြင်း (DEM raster ဖိုင်များဖြင့်သာ အသုံးဝင်ပါသည်) တို့ဖြစ်ကြပါသည်။

အကိုးအကား (Reference)
----------------------------------------------------------------------

SRTM dataset ကို `http://srtm.csi.cgiar.org/ <http://srtm.csi.cgiar.org/>`_ မှရယူထားပါသည်။

နောက်ထပ် ဘာအကြောင်းအရာလဲ? (What's Next?)
----------------------------------------------------------------------

ယခုဆိုလျှင် data ကို သင့်လျော်စွာ ပြသပေးနေသည်ကို မြင်တွေ့နိုင်ပြီဖြစ်ပါသည်၊ ၎င်းကို နောက်ထပ် မည်သို့ဆန်းစစ်လေ့လာမှုများ ပြုလုပ်နိုင်သည်ကို ဆက်လက်လေ့လာကြပါမည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |contextHelp| image:: /static/common/mActionContextHelp.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
