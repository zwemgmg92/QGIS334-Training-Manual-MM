သင်ခန်းစာ - LiDAR Data မှ DEM ထုတ်ယူခြင်း (Lesson: DEM from LiDAR Data)
===============================================================================

အမျိုးမျိုးသော နောက်ခံဓာတ်ပုံများကို အသုံးပြု၍ မြေပုံကို ပိုမိုကြည့်ကောင်းအောင် လုပ်ဆောင်နိုင်ပါသည်။ ယခင်ကအသုံးပြုခဲ့သော အခြေခံမြေပုံ သို့မဟုတ် ကောင်းကင်ဓာတ်ပုံ ကိုအသုံးပြုနိုင်ပါသည်၊ သို့သော် အချို့သောနေရာများတွင် မြေမျက်နှာသွင်ပြင် hillshade raster တစ်ခုကို အသုံးပြုခြင်းက ပိုမိုကြည့်ကောင်းစေပါသည်။

LAStools ကိုအသုံးပြုပြီး LiDAR dataset တစ်ခုမှ DEM တစ်ခုကို ထုတ်ယူကာ hillshade raster တစ်ခုကိုဖန်တီးမည်ဖြစ်သည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** LAStools ကို install ပြုလုပ်ရန်နှင့် LiDAR data မှ DEM တစ်ခုတွက်ချက်ရန်နှင့် hillshade raster တစ်ခုတွက်ချက်ရန်။


:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - LAStools ကို Install ပြုလုပ်ခြင်း (Follow Along: Installing Lastools)
-------------------------------------------------------------------------------------------------------------------

Processing framework နှင့် `LAStools <https://rapidlasso.com/2013/09/29/how-to-install-lastools-toolbox-in-qgis>`_ မှပံ့ပိုးပေးထားသော algorithm များကိုအသုံးပြုပြီး QGIS အတွင်း LiDAR data ကို ကိုင်တွယ်လုပ်ဆောင်နိုင်ပါသည်။

LiDAR point cloud တစ်ခုမှ digital elevation model (DEM) တစ်ခုကို ရရှိနိုင်ပြီး၊ ထို့နောက်တွင် ပုံဖော်ပြသရာ၌ အမြင်ပိုင်းအရပိုမိုကောင်းမွန်သော hillshade raster တစ်ခုကိုဖန်တီးပေးနိုင်ပါသည်။ LAStools များဖြင့် ကောင်းမွန်စွာ အလုပ်လုပ်ကိုင်နိုင်စေရန် :guilabel:`Processing` framework setting များကို ဦးစွာ set up ပြုလုပ်ထားရပါမည်-

* QGIS ကို ဖွင့်ထားပါက ပိတ်လိုက်ပါ။
* Lidar plugin အဟောင်းကို :file:`C:/Program Files/QGIS Valmiera/apps/qgis/python/plugins/processing/` folder ထဲတွင် default အနေဖြင့် install လုပ်ထားပြီးသား ဖြစ်နေနိုင်ပါသည်။
* :kbd:`lidar` အမည်ဖြင့် folder တစ်ခုရှိပါက ၎င်းကို ဖျက်ပစ်လိုက်ပါ။ ၎င်းသည် QGIS 2.2 နှင့် 2.4 ၏ installation အချို့အတွက် ကိုက်ညီပါသည်။

.. figure:: img/remove_lidar_folder.png
   :align: center

* :file:`exercise_data\\forestry\\lidar\\` folder ထဲတွင် :file:`QGIS_2_2_toolbox.zip` ဖိုင်ကို တွေ့ရနိုင်ပါသည်။ ၎င်းကို ဖွင့်ပြီး :kbd:`lidar` folder ကို extract လုပ်ပါ။
* အခြား QGIS version ကိုအသုံးပြုနေပါက `ဤ tutorial <https://rapidlasso.com/2013/09/29/how-to-install-lastools-toolbox-in-qgis/>`_ တွင် installation ညွှန်ကြားချက်များကို ကြည့်ရှုနိုင်ပါသည်။

LAStools ကို ကွန်ပျူတာတွင် install လုပ်ရန်လိုအပ်ပါသည်။ နောက်ဆုံးထွက် *lastools* version ကို `ဤနေရာ <https://lastools.github.io/download/LAStools.zip>`_ မှရယူပြီး :file:`lastools.zip` ဖိုင်ကို system ထဲရှိ folder တစ်ခုထဲတွင် extract လုပ်ပါ၊ ဥပမာ- :file:`C:\\lastools\\` ။ :file:`lastools` folder သို့ဖိုင်လမ်းကြောင်း တွင် space သို့မဟုတ် ထူးခြားသည့် အက္ခရာများ မပါရှိရပါ။

.. note:: :kbd:`lastools` folder ထဲရှိ :kbd:`LICENSE.txt` ဖိုင်ကို ဖတ်ကြည့်ပါ။ အချို့သော Lastools များသည် open source ဖြစ်ပြီး အချို့အရာများသည် စီးပွားဖြစ်နှင့် အစိုးရဆိုင်ရာအသုံးပြုမှုများအတွက် လိုင်စင် လိုအပ်ပါသည်။ ပညာရေးနှင့် အကဲဖြတ်ခြင်းဆိုင်ရာ ကိစ္စရပ်များအတွက် Lastools များကို လိုအပ်သလောက် စမ်းသပ်အသုံးပြုနိုင်ပါသည်။

Plugin နှင့် algorithm များကို သင့်ကွန်ပျူတာတွင် install ပြုလုပ်ပြီးဖြစ်ကာ စတင်အသုံးပြုရန်အသင့်ဖြစ်နေပါပြီ၊ စတင်အသုံးပြုရန် Processing framework ကို set up ပြုလုပ်ပေးရန်သာ လိုပါတော့သည်-

* QGIS ထဲတွင် project အသစ်တစ်ခုကို ဖွင့်ပါ။
* Project ၏ CRS ကို :kbd:`ETRS89 / ETRS-TM35FIN` ဟုသတ်မှတ်ပါ။
* Project ကို :kbd:`forest_lidar.qgs` အဖြစ်သိမ်းဆည်းပါ။

QGIS ထဲတွင် LAStools ကို set up ပြုလုပ်ရန်-

* :menuselection:`Processing --> Options and configuration` သို့သွားပါ။
* :guilabel:`Processing options` dialog ထဲတွင် :guilabel:`Providers` သို့သွားပါ၊ ထို့နောက် :guilabel:`Tools for LiDAR data` သို့သွားပါ။
* :guilabel:`Activate` ကိုအမှန်ခြစ်ပါ။
* :guilabel:`LAStools folder` အတွက် :kbd:`c:\\lastools\\` ဟုသတ်မှတ်ပါ (သို့မဟုတ် LAStools ကို extract လုပ်ထားသော folder)။

.. figure:: img/processing_options.png
   :align: center

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - LAStools ဖြင့် DEM တစ်ခုတွက်ချက်ခြင်း (Follow Along: Calculating a DEM with LAStools)
-----------------------------------------------------------------------------------------------------------------------------------

:doc:`../vector_analysis/spatial_statistics` တွင် SAGA algorithm အချို့ကို run ရန် :menuselection:`Processing` toolbox ကိုအသုံးပြုခဲ့ပြီးဖြစ်ပါသည်။ ယခုအခါ LAStools program များကို run ရန် :menuselection:`Processing` toolbox  ကိုအသုံးပြုပါမည်-

* :menuselection:`Processing --> Toolbox` ကိုဖွင့်ပါ။
* အောက်ခြေရှိ dropdown menu ထဲတွင် :guilabel:`Advanced interface` ကိုရွေးချယ်ပါ။
* :guilabel:`Tools for LiDAR data` category ကိုမြင်တွေ့ရပါမည်။

.. figure:: img/processing_toolbox.png
   :align: center

* အသုံးပြုနိုင်သော tool များကို မြင်ရနိုင်ရန် ၎င်းကို အကျယ်ဖြန့်ကြည့်ပါ၊ :guilabel:`LAStools` category ကိုလည်း အကျယ်ဖြန့်ကြည့်ပါ (algorithm အရေအတွက် ပြောင်းလဲနိုင်ပါသည်)။
* :guilabel:`lasview` algorithm ကိုရှာဖွေပြီး click နှစ်ချက်နှိပ်ကာ ဖွင့်ပါ။
* :guilabel:`Input LAS/LAZ file` နေရာတွင် :file:`exercise_data\\forestry\\lidar\\` folder ကိုဖွင့်ပြီး :file:`rautjarvi_lidar.laz` ကိုရွေးချယ်ပါ။

.. figure:: img/lasview_dialog.png
   :align: center

* :guilabel:`Run` ကိုနှိပ်ပါ။

ယခုအခါ :guilabel:`just a little LAS and LAZ viewer` dialog window ထဲတွင် LiDAR data ကို မြင်တွေ့နိုင်ပြီဖြစ်ပါသည်-

.. figure:: img/full_lidar.png
   :align: center

ထို viewer အတွင်းတွင် လုပ်ဆောင်နိုင်သည့်အရာများစွာ ရှိပါသည်၊ သို့သော် အခုလောလောဆယ် viewer ပေါ်တွင် click နှိပ်ဖိဆွဲကြည့်ကာ LiDAR point cloud ကို မြင်ကွင်းရွှေ့ကြည့်ပါ။

.. note:: LAStools အလုပ်လုပ်ပုံအကြောင်း ပိုမိုအသေးစိတ်သိရှိလိုပါက tool တစ်ခုချင်းစီ၏အကြောင်းကို :file:`C:\\lastools\\bin\\` folder ထဲရှိ :file:`README` text ဖိုင်တွင် ဖတ်ရှုနိုင်ပါသည်။ Tutorial များနှင့်အခြားအရာများကို `Rapidlasso webpage <https://rapidlasso.com/>`_ တွင်ရရှိနိုင်ပါသည်။

* အသင့်ဖြစ်ပါက viewer ကိုပိတ်လိုက်ပါ။

LAStools ဖြင့် DEM တစ်ခုဖန်တီးခြင်းကို အဆင့် ၂ ဆင့်ဖြင့် လုပ်ဆောင်နိုင်ပါသည်၊ ပထမအဆင့်မှာ point cloud များကို :kbd:`ground` နှင့် :kbd:`no ground` point များအဖြစ် classify ပြုလုပ်မည်ဖြစ်ပြီး နောက်တစ်ဆင့်အနေဖြင့် :kbd:`ground` point များကိုသာ အသုံးပြုပြီး DEM တစ်ခုကို တွက်ချက်မည်ဖြစ်သည်။

* :guilabel:`Processing Toolbox` သို့ပြန်သွားပါ။
* :guilabel:`Search...` box တွင် :kbd:`lasground` ဟုရေးပါ။
* :guilabel:`lasground` tool ကိုဖွင့်ရန် click နှစ်ချက်နှိပ်ပြီး အောက်ပါပုံတွင် ပြထားသည့်အတိုင်း သတ်မှတ်ပါ-

.. figure:: img/lasground_dialog.png
   :align: center

* Output ဖိုင်ကို :file:`rautjarvi_lidar.laz` ဖိုင်ရှိသည့် folder ထဲတွင်ပင် သိမ်းဆည်းပြီး :file:`rautjarvi_lidar_1.las` ဟုအမည်ပေးပါ။

၎င်းကို စစ်ဆေးကြည့်လိုပါက :guilabel:`lasview` ဖြင့်ဖွင့်နိုင်ပါသည်။

.. figure:: img/lasground_result.png
   :align: center

အညိုရောင် point များသည် ground အနေဖြင့် classify ပြုလုပ်ထားသော point ဖြစ်ပြီး မီးခိုးရောင် point များသည် အခြားအရာများဖြစ်သည်၊ ground point များကိုသာ မြင်ရနိုင်စေရန်  :kbd:`g` ကိုနှိပ်နိုင်ပြီး classify မလုပ်ထားသော point များကိုသာ မြင်ရနိုင်စေရန် :kbd:`u` ကိုနှိပ်နိုင်ပါသည်။ Point များအားလုံးကို ပြန်မြင်ရစေရန် :kbd:`a` ကိုနှိပ်ပါ။ နောက်ထပ်စေခိုင်းမှုများအတွက် :file:`lasview_README.txt` ဖိုင်တွင် ကြည့်ပါ။ LiDAR point များကို manual edit ပြုလုပ်ခြင်းအကြောင်း စိတ်ဝင်စားပါက ဤ `tutorial
<https://rapidlasso.com/2014/03/02/tutorial-manual-lidar-editing/>`_ တွင် viewer အတွင်း အမျိုးမျိုးသော လုပ်ဆောင်မှုများကို တွေ့ရနိုင်ပါသည်။

* Viewer ကို ပိတ်လိုက်ပါ။
* :guilabel:`Processing Toolbox` ထဲတွင် :kbd:`las2dem` ကိုရိုက်ရှာပါ။
* :guilabel:`las2dem` tool ကိုဖွင့်ပြီး အောက်ပါပုံတွင်ပြထားသည့်အတိုင်း သတ်မှတ်ပါ-

.. figure:: img/las2dem_dialog.png
   :align: center

ရလာဒ် DEM ကို :kbd:`Output raster file` ဟူသော အမည်ဖြင့် မြေပုံထဲသို့ ထည့်သွင်းပေးမည်ဖြစ်သည်။

.. note:: The :guilabel:`lasground` and :guilabel:`las2dem` tools require licensing.
  You can use the unlicensed tool as indicated in the license file, but you get
  the diagonals you can appreciate in the image results.

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Terrain Hillshade တစ်ခုဖန်တီးခြင်း (Follow Along: Creating a Terrain Hillshade)
-----------------------------------------------------------------------------------------------------------------------------

DEM တစ်ခုမှထုတ်ယူထားသော hillshade တစ်ခုသည် မြေမျက်နှာသွင်ပြင်ကို ပုံဖော်ပြသရာတွင် ပိုမိုကောင်းမွန်ပါသည်-

* :menuselection:`Raster --> Terrain analysis --> Hillshade` ကိုဖွင့်ပါ။
* :guilabel:`Output layer` တွင် :file:`exercise_data\\forestry\\lidar\\` folder ကိုရွေးပေးပြီး ဖိုင်ကို :file:`hillshade.tif` ဟုအမည်ပေးပါ။
* အခြားကျန်ရှိသော parameter များကို default အတိုင်းချန်ထားပါ။

.. figure:: img/dem_hillshade.png
   :align: center

* CRS မေးမြန်းလာပါက :kbd:`ETRS89 / ETRS-TM35FIN` ကိုရွေးချယ်ပါ။

Hillshade raster ရလာဒ်တွင် ထောင့်ဖြတ်မျဉ်းများ ပါရှိနေသော်လည်း ဧရိယာ၏တိကျသောရုပ်ကြွ ကိုရှင်းရှင်းလင်းလင်းမြင်တွေ့ရနိုင်ပါသည်။ တောထဲ၌ အမျိုးမျိုးသော မြောင်းများတူးဆွထားသည်ကိုပင် တွေ့ရနိုင်ပါသည်။

.. figure:: img/hillshade_result.png
   :align: center


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

အထူးသဖြင့် တောဧရိယာများတွင် DEM တစ်ခုရရှိရန် LiDAR data ကိုအသုံးပြုခြင်းသည် များစွာအားစိုက်ထုတ်ရန်မလိုပဲ ရလာဒ်ကောင်းများရရှိနိုင်ပါသည်။ LiDAR မှ အဆင့်သင့်ထုတ်ယူထားပြီးသော DEM များကိုလည်း အသုံးပြုနိုင်သလို `SRTM 9m resolution DEMs <https://srtm.csi.cgiar.org/srtmdata/>`_ ကဲ့သို့သော အခြားအရင်းအမြစ်များကိုလည်း အသုံးပြုနိုင်ပါသည်။ တစ်နည်းမဟုတ်တစ်နည်းဖြင့် ၎င်းတို့ကို အသုံးပြုပြီး မြေပုံတွင် ပုံဖော်ပြသရန် hillshade raster တစ်ခုကိုဖန်တီးနိုင်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ဤမော်ဂျူး၏ နောက်ဆုံးအဆင့်ဖြစ်သော နောက်လာမည့်သင်ခန်းစာတွင် hillshade raster နှင့် forest inventory ရလာဒ်များကို အသုံးပြုပြီး မြေပုံတစ်ခုကို ဖန်တီးမည်ဖြစ်ပါသည်။
