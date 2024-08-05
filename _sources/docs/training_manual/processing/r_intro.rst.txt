.. _r-intro:

*************************************************************************
Processing တွင် R script များအသုံးပြုခြင်း (Use R scripts in Processing)
*************************************************************************

မော်ဂျူးကို Matteo Ghetta မှ ပါဝင်ကူညီထားပြီး `Scuola Superiore Sant'Anna <https://www.santannapisa.it/it>`_ မှ ငွေကြေးထောက်ပံ့ထားပါသည်။

Processing (``Processing R Provider`` plugin ဖြင့်) သည် QGIS အတွင်း R script များရေးသားပြီး run နိုင်ရန် လုပ်ဆောင်ပါသည်။

.. warning::
   သင့်ကွန်ပျူတာတွင် R ကို install ပြုလုပ်ထားရမည်ဖြစ်ပြီး PATH ကို မှန်ကန်စွာသတ်မှတ်ပေးထားရပါမည်။ ထို့အပြင် Processing သည် ပြင်ပ R package များသာ ခေါ်ယူသောကြောင့် ၎င်း package များကို install မပြုလုပ်နိုင်ပါ။ ထို့ကြောင့် ပြင်ပ package များကို R ထဲတွင် တိုက်ရိုက် install ပြုလုပ်ထားပေးပါ။ အသုံးပြုသူလမ်းညွှန်ထဲရှိ သက်ဆိုင်ရာ :ref:`အခန်း <creating_r_scripts>` တွင်ကြည့်ရှုပါ။

.. note::
   ``sp`` ၊ ``rgdal`` နှင့် ``raster`` ကဲ့သို့သော Processing မှ *မဖြစ်မနေလိုအပ်သော* package များမရှိပါက *package* ပြဿနာများရှိနိုင်ပါသည်။

Script များထည့်သွင်းခြင်း (Adding scripts)
===========================================

Script တစ်ခုထည့်သွင်းခြင်းသည် ရိုးရှင်းပါသည်။ အလွယ်ကူဆုံးနည်းလမ်းမှာ Processing toolbox ကိုဖွင့်ပြီး toolbox ၏ထိပ်ရှိ R menu (R icon တွင် label တပ်ထားသော) မှ :menuselection:`Create new R script...` ကိုရွေးချယ်ပေးခြင်းဖြစ်သည်။ Text editor တစ်ခုထဲတွင်လည်း script ကိုဖန်တီးနိုင်ပြီး ၎င်းကို R script folder (:file:`processing/rscripts`) ထဲတွင် သိမ်းဆည်းနိုင်ပါသည်။ ထို folder ထဲတွင် သိမ်းဆည်းထားပြီးသောအခါ processing toolbox ထဲရှိ script နာမည်ပေါ်တွင် right click နှိပ်ပြီး :menuselection:`Edit Script...` ကိုရွေးကာ script ကို edit ပြုလုပ်နိုင်ပါသည်။ 

.. figure:: img/r_intro/r_intro_1.png

.. note::
   Processing ထဲတွင် R ကိုမတွေ့ရပါက :menuselection:`Processing --> Options --> Providers` ထဲတွင် R ကို activate လုပ်ပေးရပါမည်။

:menuselection:`Create new R script...` ကိုနှိပ်ပါက *script editor window* တစ်ခုပွင့်လာမည်ဖြစ်ပြီး script စာကိုယ် မထည့်သွင်းမီ parameter အချို့ကို ထိုထဲတွင် သတ်မှတ်ပေးရပါမည်။

.. figure:: img/r_intro/r_intro_2.png
   :scale: 70%
   :align: center

Plot များဖန်တီးခြင်း (Creating plots)
======================================

ဤလေ့ကျင့်ခန်းတွင် vector layer field တစ်ခု၏ **boxplot** တစ်ခုကိုဖန်တီးမည်ဖြစ်သည်။

:file:`exercise_data/processing/r_intro/` folder ထဲရှိ :file:`r_intro.qgs` QGIS project ကိုဖွင့်ပါ။


Script parameters
-----------------

Editor ကိုဖွင့်ပြီး စတင်ရေးသားပါ။

Script စာကိုယ် **မတိုင်မီ** တွင် parameter အချို့ကို သတ်မှတ်ပေးရပါမည်-

#. Script ကိုထားရှိလိုသော အုပ်စု၏နာမည် (ဤဥပမာတွင် `plots` ဖြစ်သည်) (အုပ်စုသည် ရှိနေပြီးသားမဟုတ်ပါက ဖန်တီးပေးမည်ဖြစ်သည်)::

    ##plots=group

   Processing toolbox ထဲရှိ **plots** R အုပ်စုထဲတွင် script ကိုရှာတွေ့နိုင်ပါသည်။

#. Plot တစ်ခုကို ပြသလိုကြောင်း Processing ကိုပြောပေးရပါမည် (ဤဥပမာတွင်)::

    ##showplots

   **Result Viewer** panel ထဲတွင် plot ဖွင့်ရန် link တစ်ခုကို တွေ့ရပါလိမ့်မည် (:menuselection:`View --> Panels` ထဲနှင့် :menuselection:`Processing --> Results Viewer` ဖြင့် Panel ကို အဖွင့်/အပိတ်လုပ်နိုင်ပါသည်)။

#. Input data အကြောင်းကိုလည်း Processing ကိုပြောပြပေးရန် လိုအပ်ပါသည်။ ဤဥပမာတွင် vector layer ၏ field တစ်ခုမှ plot တစ်ခုကိုဖန်တီးလိုပါသည်::

    ##Layer=vector

   ယခုအခါ Input သည် vector တစ်ခုဖြစ်ကြောင်း Processing မှသိရှိပြီဖြစ်ပါသည်။ နာမည် *Layer* သည် အရေးမကြီးပါ၊ အရေးကြီးသည်မှာ **vector** parameter ဖြစ်ပါသည်။

#. နောက်ဆုံးတွင် vector layer ၏ input field ကိုသတ်မှတ်ပေးရပါမည် (အထက်တွင်ပေးထားသော နာမည် *Layer* ကိုအသုံးပြုပြီး)::

    ##X=Field Layer

   *Layer* ၏ field တစ်ခုကိုလိုအပ်ကြောင်းနှင့် ၎င်းကို **X** ဟုခေါ်ဆိုမည်ဖြစ်ကြောင်း Processing မှသိရှိပြီဖြစ်ပါသည်။

#. ``name`` ကိုအသုံးပြုပြီး script ၏နာမည်ကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်::

    ##My box plot script=name
    
   သတ်မှတ်မပေးထားပါက ဖိုင်နာမည်သည် script ၏နာမည်အတိုင်း ဖြစ်ပါလိမ့်မည်။

Script စာကိုယ် (Script body)
-----------------------------

ယခုအခါ script ၏ *heading* ကိုသတ်မှတ်ပြီးဖြစ်သောကြောင့် function ထည့်သွင်းနိုင်ပြီဖြစ်ပါသည်::

    boxplot(Layer[[X]])

**boxplot** သည် R function ၏နာမည်ဖြစ်ပါသည်၊ parameter **Layer** သည် input dataset အတွက် သင်သတ်မှတ်ပေးထားသော နာမည်ဖြစ်ပြီး **X** သည် ထို dataset ၏ field အတွက် သင်သတ်မှတ်ပေးထားသော နာမည်ဖြစ်ပါသည်။

.. warning::
   parameter **X** သည် လေးထောင့်ကွင်းနှစ်ခု (``[[]]``) အတွင်း ရှိရပါမည်။

အပြီးသတ် script သည် အောက်ပါပုံစံအတိုင်းဖြစ်ပါသည်::

    ##Vector processing=group
    ##showplots
    ##Layer=vector
    ##X=Field Layer
    boxplot(Layer[[X]])

.. figure:: img/r_intro/r_intro_3.png

Processing မှအကြံပြုထားသော default ဖိုင်လမ်းကြောင်း (processing/rscripts) ထဲတွင် script ကိုသိမ်းဆည်းပါ။ Script heading ထဲတွင် ``name`` တစ်ခုကို မသတ်မှတ်ထားပါက သင်ရွေးချယ်သော ဖိုင်နာမည်သည် Processing toolbox ထဲရှိ script ၏နာမည် ဖြစ်ပါလိမ့်မည်။

.. note::
   Script ကို သင်ကြိုက်နှစ်သက်ရာနေရာတွင် သိမ်းဆည်းနိုင်ပါသည်၊ သို့သော် Processing toolbox ထဲတွင် script ကိုအလိုအလျောက်ထည့်သွင်းပေးလိမ့်မည်မဟုတ်ပါ၊ ထို့ကြောင့် script ကို manual upload လုပ်ပေးရပါမည်။

Editor window ၏အပေါ်ဘက်ရှိ ခလုတ်ကိုနှိပ်ပြီး script ကို run လိုက်ပါ-

.. figure:: img/r_intro/r_intro_4.png

Editor window ကိုပိတ်လိုက်ပြီး Processing ၏ text box ထဲတွင် သင်၏ script ကိုရှာဖွေပါ-

.. figure:: img/r_intro/r_intro_5.png

ယခုအခါ Processing algorithm window ထဲတွင် လိုအပ်သော parameter များကိုဖြည့်သွင်းနိုင်ပြီဖြစ်ပါသည်-

* **Layer** အတွက် *sample_points* ကိုရွေးပါ
* **X** field အတွက် *value* ကိုရွေးပါ

**Run** ကိုနှိပ်ပါ။

.. figure:: img/r_intro/r_intro_6.png

**Result window** သည် အလိုအလျောက်ပွင့်လာသင့်ပါသည်၊ ထိုသို့မပွင့်လာပါက :menuselection:`Processing --> Result Viewer...` ကိုနှိပ်ပါ။

Viewer ထဲရှိ link ကိုနှိပ်ပါက အောက်ပါအတိုင်း တွေ့ရပါလိမ့်မည်-

.. figure:: img/r_intro/r_intro_7.png

.. note::
   Plot ပေါ်တွင် right click နှိပ်ပြီး ပုံကို ဖွင့်နိုင်၊ ကူးယူနိုင်၊ သိမ်းဆည်းနိုင်ပါသည်။

Vector တစ်ခုဖန်တီးခြင်း (Create a vector)
==========================================

Vector layer တစ်ခုကို ဖန်တီးပြီး ၎င်းကို QGIS ထဲသို့ အလိုအလျောက်ထည့်သွင်းပေးနိုင်ပါသည်။

အောက်ပါဥပမာကို အွန်လိုင်း R script များစုစည်းမှုတွင် တွေ့ရနိုင်သော ``Random sampling grid`` script မှရယူထားပါသည် (အွန်လိုင်းစုစည်းမှုထဲရှိ script များကို https://github.com/qgis/QGIS-Processing/tree/master/rscripts တွင်တွေ့နိုင်ပါသည်)။

ဤလေ့ကျင့်ခန်း၏ရည်ရွယ်ချက်မှာ input vector layer တစ်ခုကိုအသုံးပြုပြီး ကျပန်း point vector layer တစ်ခုကိုဖန်တီးရန်ဖြစ်ပြီး ``sp`` package မှ ``spsample`` function ကိုအသုံးပြုပြီး extent (နယ်ပယ်အကျယ်အဝန်း) ကို ကန့်သတ်ရန်ဖြစ်သည်။


Script parameters
------------------

Script စာကိုယ် မတိုင်မီတွင် parameter အချို့ကို သတ်မှတ်ပေးရပါမည်-

#. Script ကိုထားရှိလိုသော အုပ်စုနာမည်ကို သတ်မှတ်ပါ၊ ဤဥပမာတွင် *Point pattern analysis* ဖြစ်သည်::

    ##Point pattern analysis=group
#. ကျပန်း point များ၏နေရာချထားမှုကို ကန့်သတ်ပေးမည့် input parameter (vector layer တစ်ခု) တစ်ခုကို သတ်မှတ်ပါ::

    ##Layer=vector

#. ဖန်တီးမည့် point အရေအတွက်အတွက် input parameter တစ်ခုကိုသတ်မှတ်ပါ (``Size`` ဖြစ်ပြီး default တန်ဖိုးသည် ``10`` ဖြစ်ပါသည်)::

    ##Size=number 10

   .. note:: Default တန်ဖိုး (``10``) သတ်မှတ်ပေးထားသောကြောင့် အသုံးပြုသူအနေဖြင့် ထိုဂဏန်းကိုပြောင်းလဲပေးနိုင်သလို parameter တွင်ဂဏန်းမထည့်ပဲ ချန်ထားနိုင်ပါသည်။

#. Output vector layer တစ်ခု (``Output`` ဟုခေါ်ဆိုသော) ကိုသတ်မှတ်ပါ::

    ##Output=output vector

Script စာကိုယ် (Script body)
-----------------------------

ယခုအခါ function ကို ထည့်သွင်းနိုင်ပြီဖြစ်ပါသည်-

#. ``spsample`` function ကိုအသုံးပြုပါ::

    pts=spsample(Layer, Size, type="random")

   Point များ၏နေရာချထားမှုကိုကန့်သတ်ရန် function သည် *Layer* ကိုအသုံးပြုပါသည် (၎င်းသည် line layer တစ်ခုဖြစ်ပါက point သည် line တစ်ခုခုပေါ်တွင်ရှိရမည်ဖြစ်သည်၊ ၎င်းသည် polygon layer တစ်ခုဖြစ်ပါက point သည် polygon အတွင်းတွင် ရှိရပါမည်)။ Point အရေအတွက်ကို *Size* parameter မှရယူပါသည်။ Sampling နည်းလမ်းသည် *random* ဖြစ်ပါသည်။

#. Output (`Output`` parameter) ကိုထုတ်ယူပါ::

    Output=SpatialPointsDataFrame(pts, as.data.frame(pts))

အပြီးသတ် script သည် အောက်ပါပုံစံအတိုင်းဖြစ်ပါသည်::

    ##Point pattern analysis=group
    ##Layer=vector
    ##Size=number 10
    ##Output=output vector
    pts=spsample(Layer, Size, type="random")
    Output=SpatialPointsDataFrame(pts, as.data.frame(pts))

.. figure:: img/r_intro/r_intro_8.png

Script ကို သိမ်းဆည်းပြီး run ပါ။

ပေါ်လာသော window အသစ်ထဲတွင် parameter ထည့်သွင်းပြီး run ကိုနှိပ်ပါ- 

.. figure:: img/r_intro/r_intro_9.png


ရလာဒ် layer ကို table of contents ထဲသို့ ထည့်သွင်းပေးမည်ဖြစ်ပြီး point များကို မြေပုံ canvas ပေါ်တွင် ပြသပေးမည်ဖြစ်သည်-

.. figure:: img/r_intro/r_intro_10.png


R - syntax မှ စာသားနှင့်ဂရပ် output (Text and graph output from R - syntax)
============================================================================

Processing (``Processing R Provider plugin`` ဖြင့်) သည် R မှ ရလာဒ်များကိုရရှိရန် အထူး syntax ကိုအသုံးပြုပါသည်-

* Command မတိုင်မီတွင် ``>`` ထည့်သွင်းခြင်း၊ ``>lillie.test(Layer[[Field]])`` သည် ရလာဒ်ကို R output (Result viewer) သို့ပို့ပေးသင့်ကြောင်း ဆိုလိုပါသည်။
* Plot နောက်တွင် ``+`` ထည့်သွင်းခြင်းသည် plot များကို ထပ်ပေးနိုင်ပါသည်။ ဥပမာ ``plot(Layer[[X]],
  Layer[[Y]]) + abline(h=mean(Layer[[X]]))``
