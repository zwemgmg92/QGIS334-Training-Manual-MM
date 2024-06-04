သင်ခန်းစာ - နောက်ဆက်တွဲ လေ့ကျင့်ခန်း (Lesson: Supplementary Exercise)
======================================================================

ဤသင်ခန်းစာတွင် GIS analysis အပြည့်အစုံတစ်ခုကို QGIS ထဲတွင် မည်သို့လုပ်ဆောင်ရမည်ကို လမ်းညွှန်ပေးမည်ဖြစ်သည်။

.. note:: ယခုသင်ခန်းစာကို Linfiniti Consulting (South Africa) နှင့်
   Siddique Motala (Cape Peninsula University of Technology) မှ ပြုစုထားပါသည်။

ပြဿနာဖော်ပြချက် (Problem Statement)
----------------------------------------------------------------------

လုပ်ဆောင်ရမည့်တာဝန်မှာ Cape Peninsula အတွင်းနှင့်အနီးပတ်လည်တွင် ရှားပါး fynbos အပင်မျိုးစိတ်အတွက် သင့်တော်သော ရှင်သန်ပေါက်ရောက်ရာနေရာ (habitat) ဧရိယာများကို ရှာဖွေရန်ဖြစ်သည်။ ရှာဖွေရမည့်ဧရိယာ နယ်ပယ်အကျယ်အဝန်းသည် မြောက်ပိုင်းရှိ Melkbosstrand နှင့် တောင်ပိုင်းရှိ Strand အကြား Cape Town နှင့် Cape
Peninsula ကိုလွှမ်းခြုံပါသည်။ ရုက္ခဗေဒပညာရှင်များသည် အပင်မျိုးစိတ်မှ ကြိုက်နှစ်သက်သော အောက်ပါအခြေအနေများကို ပံ့ပိုးပေးထားပါသည်- 

* ၎င်းသည် အရှေ့ဘက်မျက်နှာမူသော slope များတွင် ပေါက်ရောက်သည်
* လျှောစောက် (gradient) ရာခိုင်နှုန်း 15 % နှင့် 60 % အကြားရှိသော slope များတွင် ပေါက်ရောက်သည် 
* နှစ်စဉ်မိုးရေချိန် 1000 မီလီမီတာအထက်ရှိသော ဧရိယာများတွင် ပေါက်ရောက်သည်
* ၎င်းကို လူနေအိမ်များနှင့် အနည်းဆုံး 250 မီတာကွာဝေးသောနေရာတွင်သာ တွေ့နိုင်သည်
* ၎င်းပေါက်ရောက်သော ဧရိယာသည် အနည်းဆုံး 6000 စတုရန်းမီတာအကျယ်ဧရိယာရှိသင့်သည်


သင်သည် တက္ကသိုလ်ကျောင်းသားတစ်ယောက်အနေဖြင့် သင့်တော်မည့် မြေဧရိယာ ၄ ခုတွင် အပင်ကို ရှာဖွေရန် သဘောတူထားပြီးဖြစ်သည်။ သင်သည် အဆိုပါ သင့်တော်မည့် မြေဧရိယာ ၄ ခုကို သင်နေထိုင်ရာ University of Cape Town နှင့်အနီးဆုံး နေရာများဖြစ်စေလိုပါသည်။ သင်အနေဖြင့် မည်သည့်နေရာများတွင်ရှာဖွေမည်ကို ဆုံးဖြတ်ရန် GIS ကျွမ်းကျင်မှုများကို အသုံးပြုပါ။

အကြမ်းဖျင်းဖြေရှင်းချက် (Solution Outline)
----------------------------------------------------------------------

ဤလေ့ကျင့်ခန်းအတွက် data များကို :file:`exercise_data/more_analysis` folder ထဲတွင် တွေ့နိုင်ပါသည်။

သင့်အနေဖြင့် University of Cape Town နှင့်အနီးဆုံးဖြစ်သော သင့်တော်မည့် မြေဧရိယာ ၄ ခုကို ရှာဖွေပါတော့မည်။

ဖြေရှင်းချက်တွင် အောက်ပါတို့ပါဝင်ပါလိမ့်မည်-

#. အရှေ့ဘက်မျက်နှာမူသော slope များနှင့် သတ်မှတ် လျှောစောက်ရာခိုင်နှုန်း (gradient) ရှိသော slope များကို ရှာဖွေရန် DEM raster layer တစ်ခုကို ဆန်းစစ်လေ့လာခြင်း
#. သတ်မှတ်ထားသော မိုးရေချိန်ပမာဏရှိသော ဧရိယာများကိုရှာဖွေရန် rainfall raster layer တစ်ခုကို ဆန်းစစ်လေ့လာခြင်း
#. လူနေအိမ်များနှင့်အဝေးတွင်ရှိပြီး သတ်မှတ်ထားသော အရွယ်အစားရှိသည့် ဧရိယာများကို ရှာဖွေရန် zoning vector layer တစ်ခုကို ဆန်းစစ်လေ့လာခြင်း

လိုက်လုပ်ကြည့်ပါ - မြေပုံ ပြင်ဆင်သတ်မှတ်ခြင်း (Follow Along: Setting up the Map)
---------------------------------------------------------------------------------

#. Screen ၏ ညာဘက်အောက်ခြေထောင့်ရှိ |projectionEnabled| :sup:`Current CRS` ခလုတ်ကိုနှိပ်ပါ။ ပေါ်လာသော dialog ၏ :guilabel:`CRS` tab ထဲတွင် "Filter" tool ကိုသုံးပြီး "33S" ဟုရိုက်ရှာပါ။ :guilabel:`WGS 84 / UTM zone 33S` (EPSG code ``32733`` ဖြင့်) ကိုရွေးပါ။
#. :guilabel:`OK` ကိုနှိပ်ပါ။

   .. figure:: img/crs.png
      :align: center

      CRS သတ်မှတ်ပေးခြင်း

#. |fileSave| :sup:`Save Project` ခလုတ်ကို နှိပ်ပြီး သို့မဟုတ် :menuselection:`Project --> Save As...` menu item ကိုအသုံးပြုပြီး project ကိုသိမ်းဆည်းပါ။

   :file:`Rasterprac` ဆိုသည့် ဖိုင်လမ်းကြောင်းအသစ်ကို သင့်ကွန်ပျူတာထဲတွင် ဖန်တီးထားပြီး project ကို ၎င်းဖိုင်လမ်းကြောင်းထဲတွင် သိမ်းဆည်းပါ။ Layer များကို ဖန်တီးတိုင်း ထိုဖိုင်လမ်းကြောင်းတွင် သိမ်းဆည်းပါ။ Project ကို :file:`your_name_fynbos.qgs` အနေဖြင့် သိမ်းဆည်းပါ။

မြေပုံထဲသို့ Data များထည့်သွင်းခြင်း (Loading Data into the Map)
----------------------------------------------------------------------

Data ကို process လုပ်ဆောင်ရန် လိုအပ်သော layer (street name များ ၊ zone များ ၊ rainfall ၊ DEM ၊ district များ) များကို မြေပုံ canvas ထဲသို့ ထည့်သွင်းရန် လိုအပ်ပါသည်။


Vector များအတွက်---
......................................................................

#. *Data Source Manager Toolbar* ထဲရှိ |dataSourceManager| :sup:`Open Data Source Manager` ကိုနှိပ်ပြီး ပေါ်လာသော dialog ထဲတွင် |addOgrLayer| :guilabel:`Vector` tab ကိုဖွင့်ပါ သို့မဟုတ် :menuselection:`Layer --> Add Layer -->` |addOgrLayer| :menuselection:`Add Vector Layer...` menu item ကိုအသုံးပြုပါ
#. |radioButtonOn| :guilabel:`File` ကိုရွေးချယ်ထားပါ
#. Vector dataset (များ) ကို ဖွင့်ရန် :guilabel:`...` ခလုတ်ကို နှိပ်ပါ
#. ပေါ်လာသော dialog ထဲတွင် :file:`exercise_data/more_analysis/Streets` ဖိုင်လမ်းကြောင်းကို ဖွင့်ပါ
#. :file:`Street_Names_UTM33S.shp` ကိုရွေးပါ
#. :guilabel:`Open` ကိုနှိပ်ပါ

   မူရင်း Dialog ပေါ်လာမည်ဖြစ်ပြီး :guilabel:`Vector dataset(s)` ဘေးရှိ စာသား field ထဲတွင် သတ်မှတ်ပေးထားသော ဖိုင်လမ်းကြောင်းပေါ်နေမည်ဖြစ်သည်။
   ဖိုင်ကို မှန်မှန်ကန်ကန် ရွေးချယ်ထားမထား ထိုထဲတွင် ကြည့်နိုင်ပါသည်။ ထို field ထဲတွင် ဖိုင်လမ်းကြောင်းကို ကိုယ်တိုင်လည်းရိုက်ထည့်ပေးနိုင်ပါသည်။
#. :guilabel:`Add` ကိုနှိပ်ပါ။ Vector layer ကို မြေပုံထဲသို့ ထည့်သွင်းပေးပါလိမ့်မည်။ ၎င်းအတွက် အရောင်ကို အလိုအလျှောက် သတ်မှတ်ပေးပါမည်။ အရောင်ကို နောက်ပိုင်းတွင် ပြောင်းလဲပါမည်။
#. Layer ကို ``Streets`` ဟူ၍ အမည်ပြောင်းပေးပါ။

   #. :guilabel:`Layers` panel ထဲရှိ ၎င်း layer ပေါ်တွင် right-click နှိပ်ပါ
   #. ပေါ်လာသော dialog ထဲတွင် :guilabel:`Rename` ကို click နှိပ်ပြီး layer ကို အမည်ပြောင်းပါ၊ ပြီးလျှင် :kbd:`Enter` နှိပ်ပါ
#. :file:`Zoning` ဖိုင်လမ်းကြောင်းထဲရှိ :file:`Generalised_Zoning_Dissolve_UTM33S.shp` ဖိုင်ကို ထည့်သွင်းပါ။
#. ၎င်းကို ``Zoning`` ဟု အမည်ပြောင်းပါ။
#. :file:`admin_boundaries/Western_Cape_UTM33S.shp` vector layer ကိုလည်း မြေပုံထဲသို့ ထည့်သွင်းပါ။
#. ၎င်းကို ``Districts`` ဟု အမည်ပြောင်းပါ။

Raster များအတွက်---
......................................................................

#. |dataSourceManager| :sup:`Open Data Source Manager` ခလုတ်ကိုနှိပ်ပြီး ပေါ်လာသော dialog ထဲတွင် |addRasterLayer| :guilabel:`Raster` tab ကိုဖွင့်ပေးပါ၊ သို့မဟုတ် :menuselection:`Layer --> Add Layer -->` |addRasterLayer| :menuselection:`Add Raster Layer...` menu item ကိုအသုံးပြုပါ
#. Ensure that |radioButtonOn| :guilabel:`File` is selected
#. |radioButtonOn| :guilabel:`File` ကိုရွေးချယ်ထားပါ
#. သင့်လျော်သည့်ဖိုင်နေရာသို့ ညွှန်ပေးပြီး ဖိုင်ကို ရွေးချယ်ကာ :guilabel:`Open` ကိုနှိပ်ပါ
#. :file:`DEM/SRTM.tif` နှင့် :file:`rainfall/reprojected/rainfall.tif` raster ဖိုင် ၂ ခုကို ထိုအတိုင်းပင်ဖွင့်ပါ
#. SRTM raster ကို ``DEM`` ဟုအမည်ပြောင်းပေးပြီး rainfall raster ကို ``Rainfall`` (အစစာလုံး အကြီးဖြင့်) ဟုအမည်ပြောင်းပေးပါ

Layer အပေါ်အောက်အစီအစဉ် ပြောင်းလဲခြင်း (Changing the layer order)
----------------------------------------------------------------------

:guilabel:`Layers` panel ထဲတွင် layer များကို click နှိပ်ဖိဆွဲပြီး အပေါ်အောက်ရွှေ့ကာ မြေပုံပေါ်တွင် မြင်ရသည့် order ကိုပြောင်းလဲနိုင်ပါသည်။

ယခုဆိုလျှင် data များအားလုံးကို ထည့်သွင်းပြီးဖြစ်ကာ analysis ကို စတင်နိုင်ပြီဖြစ်ပါသည်။ Clipping (တိဖြတ်ခြင်း) လုပ်ဆောင်မှုကို ဦးစွာ လုပ်ဆောင်ထားလျှင် အကောင်းဆုံးဖြစ်ပါသည်။ ထိုသို့လုပ်ဆောင်ခြင်းဖြင့် မလိုအပ်သည့်ဧရိယာများတွင် တန်ဖိုးများတွက်ချက်ရန်မလိုအပ်တော့သောကြောင့် လုပ်ဆောင်မှုစွမ်းအား မြန်ဆန်လာစေပါသည်။

မှန်ကန်သော ခရိုင်များကို ရှာဖွေခြင်း (Find the Correct Districts)
----------------------------------------------------------------------

ရှေ့တွင်ဖော်ပြထားသော ရှာဖွေမည့်ဧရိယာအရ အောက်ဖော်ပြပါ ခရိုင်များအတွင်း ကန့်သတ်ရန် လိုအပ်ပါသည်-

* ``Bellville``
* ``Cape``
* ``Goodwood``
* ``Kuils River``
* ``Mitchells Plain``
* ``Simon Town``
* ``Wynberg``

#. :guilabel:`Layers` panel ထဲရှိ ``Districts`` layer ပေါ်တွင် right-click နှိပ်ပါ။
#. ပေါ်လာသော menu ထဲတွင် :guilabel:`Filter...` menu item ကိုရွေးပါ။ :guilabel:`Query Builder` dialog ပေါ်လာပါမည်။

#. သတ်မှတ်ထားသည့် district များကိုသာ ရွေးချယ်ရန် query တစ်ခုတည်ဆောက်ပါမည်-

   #. :guilabel:`Fields` list ထဲတွင် ``NAME_2`` field ကို click နှစ်ချက်နှိပ်ပါ၊ အောက်တွင်ရှိသည့် :guilabel:`SQL where clause` စာသား field ထဲတွင် ပေါ်လာမည်ဖြစ်သည်။
   #. SQL query ထဲတွင် ဆက်ရေးရန် :guilabel:`IN` ကိုနှိပ်ပါ။
   #. ``(`` လက်သည်းကွင်း အဖွင့်ရေးပါ။
   #. :guilabel:`Values` list အောက်ရှိ :guilabel:`All` ခလုတ်ကိုနှိပ်ပါ။

      အနည်းငယ်ကြာပြီးနောက်တွင် ရွေးချယ်ထားသော field (``NAME_2``) ၏တန်ဖိုးများပါဝင်သော :guilabel:`Values` list ပေါ်လာပါလိမ့်မည်။
   #. SQL query ထဲတွင် ဆက်တွဲရေးသားရန် :guilabel:`Values` list ထဲရှိ ``Bellville`` ကို click နှစ်ချက်နှိပ်ပါ။
   #. ကော်မာ (,) တစ်ခုထည့်ပြီး ``Cape`` district ကိုထည့်ရန် click နှစ်ချက်နှိပ်ပါ။
   #. ကျန်ရှိသော district များအတွက် အထက်ပါအဆင့်အတိုင်း ထပ်ခါထပ်ခါလုပ်ဆောင်ပါ။
   #. ``)`` လက်သည်းကွင်း ပိတ်ပါ။

   .. figure:: img/query_builder.png
      :align: center

      Query builder


      နောက်ဆုံး query သည် အောက်ပါအတိုင်းဖြစ်သင့်ပါသည် (Bracket ထဲရှိ district များ၏ order သည် အရေးမကြီးပါ)-::

        "NAME_2" in ('Bellville', 'Cape', 'Goodwood', 'Kuils River',
                     'Mitchells Plain', 'Simon Town', 'Wynberg')

      .. note:: ``OR`` operator ကိုလည်း အသုံးပြုနိုင်ပါသည်၊ query သည် အောက်ပါပုံစံအတိုင်း ဖြစ်ပါလိမ့်မည်-::

          "NAME_2" = 'Bellville' OR "NAME_2" = 'Cape' OR
          "NAME_2" = 'Goodwood' OR "NAME_2" = 'Kuils River' OR
          "NAME_2" = 'Mitchells Plain' OR "NAME_2" = 'Simon Town' OR
          "NAME_2" = 'Wynberg'

   #. :guilabel:`OK` နှစ်ကြိမ်နှိပ်ပါ။

      အထက်ပါ စာရင်းထဲရှိ district များသာ မြေပုံပေါ်တွင် ပေါ်နေမည်ဖြစ်သည်။

Raster များအား တိဖြတ်ခြင်း (Clip the Rasters)
----------------------------------------------------------------------

ယခုဆိုလျှင် စိတ်ဝင်စားသည့် ဧရိယာတစ်ခုရှိပြီး raster များကို အဆိုပါ ဧရိယာဖြင့် တိဖြတ် (clip) နိုင်ပါသည်။

#. :menuselection:`Raster --> Extraction --> Clip Raster by Mask Layer...` menu item ကိုရွေးချယ်ပြီး clipping dialog ကိုဖွင့်ပါ
#. :guilabel:`Input layer` dropdown list ထဲတွင် ``DEM`` layer ကိုရွေးချယ်ပါ
#. :guilabel:`Mask layer` dropdown list ထဲတွင် ``Districts`` layer ကိုရွေးချယ်ပါ
#. အောက်သို့ scroll လုပ်ပြီး :guilabel:`Clipped (mask)` စာသား field ထဲတွင် output တည်နေရာကိုသတ်မှတ်ရန်  :guilabel:`...` ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Save to File...` ကိုရွေးချယ်ပါ

   #. :file:`Rasterprac` ဖိုင်လမ်းကြောင်းသို့ ညွှန်ပေးပါ
   #. ``DEM_clipped.tif`` ဟူသော ဖိုင်အမည်ကို ရိုက်ထည့်ပါ
   #. Save လုပ်ပါ

#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ

   Clipping လုပ်ဆောင်မှု ပြီးဆုံးသွားပြီးနောက်တွင် clip လုပ်ထားသော ဧရိယာကို ပြန်လည်အသုံးပြုနိုင်စေရန် :guilabel:`Clip Raster by Mask Layer` dialog ကိုဆက်ဖွင့်ထားပါ
#. :guilabel:`Input layer` dropdown list ထဲတွင် ``Rainfall`` raster layer ကိုရွေးချယ်ပြီး output ကို :file:`Rainfall_clipped.tif` ဖိုင်အနေဖြင့် သိမ်းဆည်းပါ
#. အခြား option များကို မပြောင်းလဲပဲ ထားပြီး :guilabel:`Run` ကိုနှိပ်ပါ။
#. ဒုတိယ clipping လုပ်ဆောင်မှု ပြီးဆုံးသွားပြီးနောက်တွင် :guilabel:`Clip Raster by Mask Layer` dialog ကိုပိတ်ထားနိုင်ပါသည်။
#. မြေပုံကို သိမ်းဆည်းပါ။

   .. figure:: img/clipped_r_filtered_v_reordered_l.png
      :align: center

      Filter လုပ်ထားသော vector ၊ clip လုပ်ထားသော raster နှင့် order ပြန်စီထားသော layer များပါဝင်သော မြေပုံမြင်ကွင်း

Raster များကို တန်းညှိခြင်း (Align the rasters)
......................................................................

Analysis အတွက် raster များသည် CRS အတူတူရှိရန် လိုအပ်ပြီး ၎င်းတို့ကို align ပြုလုပ်ပေးရပါမည်။

Rainfall data ၏ resolution ကို 30 မီတာ (pixel အရွယ်အစား) သို့ ဦးစွာပြောင်းလဲပါမည်-

#. :guilabel:`Layers` panel ထဲရှိ  ``Rainfall_clipped`` layer ပေါ်တွင် click နှိပ်ထားပါ (၎င်းကို highlight ဖြင့်ပြနေမည်ဖြစ်သည်)
#. :guilabel:`Warp (Reproject)` dialog ကိုဖွင့်ရန် :menuselection:`Raster --> Projections --> Warp (Reproject)...` menu item ကိုနှိပ်ပါ
#. :guilabel:`Resampling method to use` အောက်တွင် :guilabel:`Bilinear (2x2 kernel)` ကိုရွေးချယ်ပါ
#. :guilabel:`Output file resolution in target georeferenced units` တွင် ``30`` ဟုသတ်မှတ်ပါ
#. အောက်သို့ scroll လုပ်ပြီး :guilabel:`Reprojected` အကွက်ထဲတွင် output ကို :file:`Rainfall30.tif` ဖိုင်အမည်ဖြင့် :file:`rainfall/reprojected` ဖိုင်လမ်းကြောင်းထဲတွင် သိမ်းဆည်းပါ။
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ

   .. figure:: img/wrap_rainfall.png
      :align: center

      Warp (Reproject) Rainfall_clipped


ထို့နောက် DEM ကို align လုပ်ပါမည်-

#. :guilabel:`Layers` panel ထဲရှိ ``DEM_clipped`` ပေါ်တွင် click နှိပ်ထားပါ (၎င်းကို highlight ဖြင့်ပြနေမည်ဖြစ်သည်)
#. :guilabel:`Warp (Reproject)` dialog ကိုဖွင့်ရန် :menuselection:`Raster --> Projections --> Warp (Reproject)...` menu item ကိုနှိပ်ပါ
#. :guilabel:`Target CRS` အောက်တွင် :guilabel:`Project CRS: EPSG:32733 - WGS 84 / UTM zone 33S` ကိုရွေးချယ်ပါ
#. :guilabel:`Resampling method to use` တွင် :guilabel:`Bilinear (2x2 kernel)` ကိုရွေးချယ်ပါ
#. :guilabel:`Output file resolution in target georeferenced units` တွင် ``30`` ဟုသတ်မှတ်ပါ
#. အောက်သို့ scroll လုပ်ပြီး :guilabel:`Georeferenced extents of output file to be created` ၏ညာဘက်ရှိ ခလုတ်ကိုနှိပ်ပြီး :menuselection:`Calculate from Layer --> Rainfall30` ကိုရွေးချယ်ပါ
#. အောက်သို့ scroll လုပ်ပြီး :guilabel:`Reprojected` အကွက်ထဲတွင် output ကို :file:`DEM30.tif` ဖိုင်အမည်ဖြင့် :file:`DEM/reprojected` ဖိုင်လမ်းကြောင်းထဲတွင် သိမ်းဆည်းပါ။
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
   

ကောင်းမွန်စွာမြင်ရနိုင်ရန်အတွက် layer များအတွက် သင်္ကေတများကို ပြောင်းလဲပေးရန် လိုအပ်ပါသည်။

Vector layer များ၏ သင်္ကေတပြောင်းလဲခြင်း (Changing the symbology of vector layers)
-----------------------------------------------------------------------------------

#. :guilabel:`Layers` panel ထဲရှိ :guilabel:`Streets` layer ပေါ်တွင် right-click နှိပ်ပါ
#. ပေါ်လာသော menu မှ :guilabel:`Properties` ကိုရွေးပါ
#. ထပ်မံပေါ်လာသော dialog ထဲတွင် :guilabel:`Symbology` tab သို့သွားပါ
#. အပေါ်ရှိ :guilabel:`Line` entry တွင် click နှိပ်ပါ
#. စာရင်းထဲရှိ သင်္ကေတတစ်ခုကိုရွေးချယ်ပါ သို့မဟုတ် အသစ်တစ်ခုသတ်မှတ်ပါ (အရောင်၊ အလင်းဖောက်နှုန်း၊....)
#. :guilabel:`OK` ကိုနှိပ်ပြီး :guilabel:`Layer Properties` dialog ကိုပိတ်ပါ။ :guilabel:`Streets` layer ၏ ပုံဖော်ပြသမှု ပြောင်းလဲသွားပါလိမ့်မည်။
#. :guilabel:`Zoning` layer အတွက်လည်း ထိုအတိုင်းလုပ်ဆောင်ပြီး သင့်တော်သည့် အရောင်တစ်ခု ရွေးချယ်ပါ

.. _changing_raster_symbology:

Raster layer များ၏ သင်္ကေတပြောင်းလဲခြင်း (Changing the symbology of raster layers)
-----------------------------------------------------------------------------------

Raster layer သင်္ကေတသည် အနည်းငယ်ကွဲပြားပါသည်။

#. :guilabel:`Rainfall30` raster layer အတွက် :guilabel:`Properties` dialog ကိုဖွင့်ပါ
#. :guilabel:`Symbology` tab သို့သွားပါ။ Dialog သည် vector layer များအတွက် dialog နှင့် အလွန်ကွဲပြားသည်ကို သတိထားမိပါလိမ့်မည်။
#. :guilabel:`Min/Max Value Settings` ကို ဖြန့်ကြည့်ပါ
#. :guilabel:`Mean +/- standard deviation` ကိုရွေးချယ်ထားပါ
#. ၎င်း၏သက်ဆိုင်ရာ အကွက်ထဲရှိ တန်ဖိုးကို ``2.00`` ထားပါ 
#. :guilabel:`Contrast enhancement` အတွက် :guilabel:`Stretch to MinMax` ကိုရွေးပါ
#. :guilabel:`Color gradient` အတွက် :guilabel:`White to Black` သို့ပြောင်းပါ
#. :guilabel:`OK` ကိုနှိပ်ပါ

   .. figure:: img/raster_symbology.png
      :align: center

      Raster symbology 

   ``Rainfall30`` raster သည် အရောင်ပြောင်းလဲသွားမည်ဖြစ်ပြီး pixel တစ်ခုချင်းစီအတွက် မတူညီသော တောက်ပမှု (brightness) တန်ဖိုးများကို တွေ့မြင်ရမည်ဖြစ်သည်။
#. ``DEM30`` layer အတွက်လည်း ထိုအတိုင်းလုပ်ဆောင်ပြီး stretching အတွက်အသုံးပြုသော standard deviations တွင် ``4.00`` ဟုသတ်မှတ်ပါ

မြေပုံကို ရှင်းလင်းခြင်း (Clean up the map)
----------------------------------------------------------------------

#. :guilabel:`Layers` panel ထဲမှ မူလ ``Rainfall`` နှင့် ``DEM`` layer များအပြင် ``Rainfall_clipped`` နှင့် ``DEM_clipped`` layer များကို ဖယ်ရှားပါ-

   * အဆိုပါ layer များပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Remove` ကိုရွေးပါ။

     .. note:: ထိုသို့လုပ်ခြင်းသည် သင့်ကွန်ပျူတာ မှ data များကို ဖယ်ရှားလိုက်ခြင်းမဟုတ်ပဲ မြေပုံပေါ်မှသာ ဖယ်ရှားလိုက်ခြင်းဖြစ်သည်။

#. မြေပုံကို သိမ်းဆည်းပါ။
#. :guilabel:`Layers` panel ထဲရှိ vector layer များ၏ဘေးရှိ box တွင် အမှန်ခြစ်ဖြုတ်ထားခြင်းခြင်း ၎င်း vector layer များကို ဖျောက်ထားနိုင်ပါသည်။ ထိုသို့လုပ်ခြင်းဖြင့် မြေပုံထဲတွင်ပုံဖော်ပြသမှု မြန်ဆန်စေပြီး အချိန်ကုန်သက်သာစေပါသည်။ 

တောင်အရိပ် ဖန်တီးခြင်း (Create the hillshade)
----------------------------------------------------------------------

Hillshade ဖန်တီးရန်အတွက် ရေးသားထားသော algorithm တစ်ခုကို အသုံးပြုရန် လိုအပ်ပါလိမ့်မည်။

#. :guilabel:`Layers` panel ထဲတွင် ``DEM30`` ပေါ်တွင် click နှိပ်ထားပါ (၎င်းကို highlight ဖြင့်ပြနေမည်ဖြစ်သည်)
#. :guilabel:`Hillshade` dialog ကိုဖွင့်ရန် :menuselection:`Raster --> Analysis --> Hillshade...` menu item ကိုနှိပ်ပါ 
#. အောက်သို့ scroll လုပ်ပြီး :guilabel:`Hillshade` အကွက်တွင် output ကို :file:`hillshade.tif` ဟူသော အမည်ဖြင့် :file:`Rasterprac` ဖိုင်လမ်းကြောင်းထဲတွင် သိမ်းဆည်းပါ
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ
#. Processing ပြီးဆုံးသည်အထိ စောင့်ပါ။

   .. figure:: img/hillshade.png
      :align: center

      Raster analysis Hillshade 

:guilabel:`Layers` panel ထဲတွင် ``hillshade`` layer အသစ်ပေါ်လာမည်ဖြစ်သည်။

#. :guilabel:`Layers` panel ထဲရှိ ``hillshade`` layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Properties`
   dialog ကိုဖွင့်ပါ
#. :guilabel:`Transparency` tab တွင် :guilabel:`Global Opacity` ၌ ``20%`` သတ်မှတ်ပါ
#. :guilabel:`OK` ကိုနှိပ်ပါ
#. အလင်းဖောက်ထားသော hillshade သည် clip ပြုလုပ်ထားသော DEM ပေါ်တွင် အထင်အရှားရောက်နေသောအခါ မြင်ရသည့် effect ကိုကြည့်ပါ။ Layer များ၏ order ကို ပြောင်းလဲပေးနိုင်ပါသည်၊ သို့မဟုတ် ``Rainfall30`` layer ကို ပိတ်ထားပြီး effect ကို ကြည့်ရှုနိုင်ပါသည်။

လျှောစောက် (Slope)
----------------------------------------------------------------------

#. :guilabel:`Slope` algorithm dialog ကိုဖွင့်ရန် :menuselection:`Raster --> Analysis --> Slope...` menu item ကိုနှိပ်ပါ
#. :guilabel:`Input layer` အနေဖြင့် ``DEM30`` ကိုရွေးချယ်ပါ
#. |checkbox| :guilabel:`Slope expressed as percent instead of degrees` ကိုအမှန်ခြစ်ပါ။ Slope ကို မတူညီသော ယူနစ်များဖြင့် ဖော်ပြပေးနိုင်ပါသည် (ရာခိုင်နှုန်း သို့မဟုတ် ဒီဂရီ)။ ကျွန်ုပ်တို့၏ criteria တွင် အပင်ပေါက်ရောက်နိုင်သည့် slope သည် 15% နှင့် 60% ဖြစ်သည့်အတွက် slope data ကို percent (ရာခိုင်နှုန်း) ဖြင့်ဖော်ပြရန် လိုအပ်ပါသည်။
#. Output အတွက် သင့်တော်မည့် ဖိုင်အမည်နှင့် ဖိုင်လမ်းကြောင်းကို သတ်မှတ်ပါ။
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှတ်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ

   .. figure:: img/slope.png
      :align: center

      Raster analysis Slope 

Slope image ကို တွက်ချက်ပြီး မြေပုံထဲသို့ ထည့်သွင်းပြီးဖြစ်ပါသည်။ ခါတိုင်းလိုပင် ၎င်းကို grayscale ဖြင့် ပုံဖော်ပြသနေပါမည်။ အရောင်ပိုမိုစုံလင်သော သင်္ကေတတစ်ခုသို့ ပြောင်းလဲပါ-

#. Layer ၏ :guilabel:`Properties` dialog  ကိုဖွင့်ပါ (ခါတိုင်းလိုပင် layer ကို right-click နှိပ်ပြီး)
#. :guilabel:`Symbology` tab သို့သွားပါ
#. :guilabel:`Singleband gray` ဟုဖော်ပြထားသော နေရာ (:guilabel:`Render type` dropdown menu ထဲတွင်) တွင် :guilabel:`Singleband pseudocolor` သို့ပြောင်းပါ
#. :guilabel:`Min / Max Value Settings` အတွက် :guilabel:`Mean +/- standard deviation x` ကိုရွေးချယ်ပြီး တန်ဖိုးကို ``2.0`` ဟုသတ်မှတ်ပါ
#. သင့်တော်သော :guilabel:`Color ramp` တစ်ခုရွေးချယ်ပါ 
#. :guilabel:`Run` ကိုနှိပ်ပါ

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - မျက်နှာမူရာအရပ် (Try Yourself: Aspect)
-----------------------------------------------------------------------

:menuselection:`Raster --> Analysis` menu ထဲမှ :guilabel:`Aspect...` ကိုရွေးချယ်ပြီး slope တွက်ချက်သည့်အတိုင်း လုပ်ဆောင်ပါ။

Project ကို အခါအားလျော်စွာ သိမ်းဆည်းပေးရန် မမေ့ပါနှင့်။

Raster များအား အတန်းအစားပြန်လည်ခွဲခြားခြင်း (Reclassifying rasters)
----------------------------------------------------------------------

#. :menuselection:`Raster --> Raster calculator...` ကိုရွေးပါ
#. :guilabel:`Output layer` အတွက် ဖိုင်လမ်းကြောင်းအဖြစ် :file:`Rasterprac` ကို သတ်မှတ်ပြီး :file:`slope15_60.tif` ဖိုင်အမည်ဖြင့် သိမ်းဆည်းပါ
#. :guilabel:`Open output file after running algorithm` တွင် အမှန်ခြစ်ခြစ်ထားပါ
   
   ဘယ်ဘက်ခြမ်းရှိ :guilabel:`Raster bands` စာရင်းထဲတွင် :guilabel:`Layers` panel ထဲရှိ raster layer များအားလုံးကို မြင်တွေ့ရပါလိမ့်မည်။ Slope layer သည် :guilabel:`slope` ဟူသောအမည်ဖြင့်ရှိနေလျှင် ၎င်းကို ``slope@1`` အနေဖြင့် စာရင်းပြုစုထားပါလိမ့်မည်။ Slope raster ၏ band 1 ကို ညွှန်းဆိုခြင်းဖြစ်ပါသည်။
#. Slope သည်  ``15`` နှင့် ``60`` ဒီဂရီကြားတွင် ရှိရန်လိုအပ်ပါသည်။

   Interface ထဲရှိ list item များနှင့် ခလုတ်များကိုအသုံးပြုပြီး အောက်ပါ expression ကိုရေးသားပါ-::

     (slope@1 > 15) AND (slope@1 < 60)

#. :guilabel:`Output layer` field တွင် သင့်တော်မည့် ဖိုင်အမည်နှင့် ဖိုင်လမ်းကြောင်း သတ်မှတ်ပါ။
#. :guilabel:`Run` ကိုနှိပ်ပါ

   .. figure:: img/raster_calculator_slope.png
      :align: center

      Raster calculator Slope 

အထက်ပါနည်းလမ်းအတိုင်း မှန်ကန်သော aspect (အရှေ့ဘက်မျက်နှာမူ- ``45`` နှင့် ``135`` ဒီဂရီအကြား) ကိုရှာဖွေပါ။

#. အောက်ပါ expression ကိုရေးသားပါ-::

     (aspect@1 > 45) AND (aspect@1 < 135)

ရလာဒ် layer ထဲတွင် အရှေ့ဘက်မျက်နှာမူသော slope များအားလုံးသည် အဖြူရောင် ဖြစ်နေမည်ဖြစ်သည် (မနက်ခင်းနေရောင်ခြည် ကျရောက်နေသည့်အတိုင်း)။

ထိုနည်းအတိုင်း မှန်ကန်သော rainfall (``1000`` မီလီမီတာထက် ပိုများသော) ကိုရှာဖွေပါ။ အောက်ပါ expression ကို အသုံးပြုပါ-::

  Rainfall30@1 > 1000

ယခုဆိုလျှင် criteria ၃ ခုစလုံးအား raster တစ်ခုချင်းစီအဖြစ် ရရှိပြီဖြစ်ပါသည်။ မည်သည့်ဧရိယာများသည် criteria အားလုံးနှင့်ကိုက်ညီသည်ကို ရှာဖွေရန် ၎င်း raster များကို ပေါင်းစည်းရန် လိုအပ်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် raster များကို တစ်ခုနှင့်တစ်ခု မြှောက်ပေးရပါမည်။ ထိုသို့မြှောက်ပေးသောအခါ တန်ဖိုး ``1`` ရှိသော ထပ်နေသည့် pixel များအားလုံးသည် တန်ဖိုး ``1`` အဖြစ်သာ ကျန်ရှိပါလိမ့်မည် (ဆိုလိုသည်မှာ ထိုနေရာသည် criteria နှင့်ကိုက်ညီသော နေရာဖြစ်သည်)၊ သို့သော် raster ၃ ခုထဲမှ တစ်ခုခုတွင် pixel တန်ဖိုး ``0`` ရှိနေလျှင် (ဆိုလိုသည်မှာ ထိုနေရာသည် criteria နှင့်မကိုက်ညီသော နေရာဖြစ်သည်) ရလာဒ်တွင် ``0`` ဖြစ်နေပါလိမ့်မည်။ ဤနည်းအားဖြင့် ရလာဒ်တွင် သင့်တော်သည့် criteria များအားလုံးနှင့်ကိုက်ညီသော ဧရိယာများသာပါဝင်ပါလိမ့်မည်။

Raster များပေါင်းစည်းခြင်း (Combining rasters)
----------------------------------------------------------------------

#. *Raster Calculator* ကိုဖွင့်ပါ (:menuselection:`Raster --> Raster Calculator...`)
#. အောက်ပါ expression ကိုရေးသားပါ (layer များအတွက် သင့်တော်သော အမည်များဖြင့်)-::

    [aspect45_135] * [slope15_60] * [rainfall_1000]

#. Output ဖိုင်လမ်းကြောင်းကို :file:`Rasterprac` အဖြစ်သတ်မှတ်ပါ
#. Output raster ကို :file:`aspect_slope_rainfall.tif` ဖိုင်အမည်ပေးပါ
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ

Raster အသစ်သည် Criteria ၃ ခုစလုံးနှင့်ကိုက်ညီသော ဧရိယာများကိုပြသပေးမည်ဖြစ်ပါသည်။

Project ကိုသိမ်းဆည်းပါ။

.. figure:: img/aspect_slope_rainfall.png
   :align: center

   Criteria ၃ ခုစလုံးနှင့်ကိုက်ညီသော မြေပုံမြင်ကွင်း 

နောက်ထပ် ကိုက်ညီရမည့် criterion တစ်ခုမှာ ဧရိယာသည် မြို့ပြလူနေဧရိယာများမှ ``250`` မီတာ ကွာဝေးရပါမည်။ တွက်ချက်မည့်ဧရိယာသည် ကျေးလက်ဒေသဧရိယာ (rural areas) များအတွင်း ရှိရမည်ဖြစ်ပြီး ဧရိယာ၏အစွန်းမှ ``250`` မီတာ သို့မဟုတ် ပိုများသော အကွာအဝေးတွင်ဖြစ်ရပါမည်။ ထို့ကြောင့် ကျေးလက်ဒေသဧရိယာများကို ဦးစွာ ရှာဖွေရန် လိုအပ်ပါသည်။

ကျေးလက်ဒေသဧရိယာများ ရှာဖွေခြင်း (Finding rural areas)
-------------------------------------------------------------------------------

#. :guilabel:`Layers` panel ထဲရှိ layer များအားလုံးကို ဖျောက်ထားပါ
#. ``Zoning`` vector layer ကို ဖွင့်ထားပါ
#. ၎င်း layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Attribute Table` dialog ကိုဖွင့်ပါ။ ဤနေရာတွင် မြေနေရာကို နည်းလမ်းအမျိုးမျိုးဖြင့် zone ခွဲထားပါသည်။ ကျေးလက်ဒေသဧရိယာများကို သီးသန့်ခွဲထုတ်လိုပါသည်။ Attribute table ကိုပိတ်လိုက်ပါ။
#. ``Zoning`` layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Query Builder` dialog ကိုဖွင့်ရန် :guilabel:`Filter...` ကိုရွေးချယ်ပါ
#. အောက်ပါ query ကိုရေးသားပါ-::

     "Gen_Zoning" = 'Rural'

   အခက်အခဲကြုံနေရလျှင် အစောပိုင်းကဖော်ပြခဲ့သော ညွှန်ကြားချက်များကို ကြည့်ပါ။
#. :guilabel:`OK` ကိုနှိပ်ပြီး :guilabel:`Query Builder` dialog ကိုပိတ်ပါ။ Query သည် feature တစ်ခုသာ ပြန်ထုတ်ပေးသင့်ပါသည်။

   .. figure:: img/query_builder_zoning.png
    :align: center

   Query builder Zoning

``Zoning`` layer မှ rural polygon များကို မြင်တွေ့ရပါမည်။ ၎င်းတို့ကို သိမ်းဆည်းရန် လိုအပ်ပါမည်။

#. ``Zoning`` တွင် right-click နှိပ်ပြီး :menuselection:`Export --> Save Features As...` ကိုရွေးချယ်ပါ။
#. Layer ကို :file:`Rasterprac` ဖိုင်လမ်းကြောင်းအောက်တွင် သိမ်းဆည်းပါ
#. Output ဖိုင်ကို :file:`rural.shp` ဟုအမည်ပေးပါ
#. :guilabel:`OK` ကိုနှိပ်ပါ
#. Project ကို သိမ်းဆည်းပါ

Rural ဧရိယာများ၏အစွန်းမှ ``250m`` အတွင်းရှိသော ဧရိယာများကို ချန်လှပ်ထားရန် လိုအပ်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် အောက်တွင်ရှင်းပြထားသည့်အတိုင်း အတွင်းဘက် buffer (negative buffer) တစ်ခု ဖန်တီးပေးပါမည်။

အတွင်းဘက် buffer တစ်ခုဖန်တီးခြင်း (Creating a negative buffer)
----------------------------------------------------------------------

#. :menuselection:`Vector --> Geoprocessing Tools --> Buffer...` ကိုနှိပ်ပါ
#. ပေါ်လာသော dialog ထဲတွင် input vector layer အနေဖြင့် ``rural`` layer ကိုရွေးပါ (:guilabel:`Selected features only` ကိုအမှန်ခြစ်ဖြုတ်ထားသင့်ပါသည်)
#. :guilabel:`Distance` တွင် ``-250`` ဟုသတ်မှတ်ပါ။ အနုတ်တန်ဖိုးသည် buffer ကိုအတွင်းဘက်သို့ ဖန်တီးပေးမည်ဖြစ်သည်။ ယူနစ်များကို မီတာ ရွေးချယ်ထားပါ။
#. |checkbox| :guilabel:`Dissolve result` ကို အမှန်ခြစ်ထားပါ
#. :guilabel:`Buffered` ထဲတွင် output ဖိုင်အား :file:`rural_buffer.shp` ဖိုင်အမည်ပေးပြီး :file:`Rasterprac` ဖိုင်လမ်းကြောင်းတွင် သိမ်းဆည်းပါ
#. :guilabel:`Save` ကိုနှိပ်ပါ
#. :guilabel:`Run` ကိုနှိပ်ပြီး processing ပြီးဆုံးသည်အထိစောင့်ပါ
#. :guilabel:`Buffer` dialog ကိုပိတ်ပါ

   Buffer သည် မှန်မှန်ကန်ကန်အလုပ်ဖြစ်/မဖြစ်ဆိုသည်ကို ``rural`` layer နှင့် ``rural_buffer`` layer နှစ်ခုခြားနားချက်ကို ယှဉ်ကြည့်ပါ။ ခြားနားချက်ကို မြင်တွေ့ရရန် layer order ကို ပြောင်းလဲပေးရန် လိုကောင်းလိုပါလိမ့်မည်။
#. ``rural`` layer ကို ဖယ်ရှားလိုက်ပါ
#. Project ကိုသိမ်းဆည်းပါ

   .. figure:: img/rural_buffer.png
      :align: center

      Rural buffer ဖြင့်မြေပုံမြင်ကွင်း


ယခုဆိုလျှင် ``rural_buffer`` vector layer ကို ``aspect_slope_rainfall`` raster ဖြင့်ပေါင်းစည်းရန် လိုအပ်ပါသည်။ ၎င်းတို့ကိုပေါင်းစည်းရန် layer တစ်ခုခု၏ data format ကို ပြောင်းလဲရန် လိုအပ်ပါမည်။ ဤတွင် raster ကို vector အဖြစ်သို့ပြောင်းလဲပါမည်၊ အဘယ်ကြောင့်ဆိုသော် vector layer များသည် ဧရိယာများတွက်ချက်ရာတွင် ပိုအဆင်ပြေသောကြောင့်ဖြစ်သည်။

Raster အား Vector အဖြစ်သို့ပြောင်းလဲခြင်း (Vectorizing the raster)
----------------------------------------------------------------------

#. :menuselection:`Raster --> Conversion --> Polygonize (Raster to  Vector)...` ကိုနှိပ်ပါ
#. :guilabel:`Input layer` အဖြစ် :file:`aspect_slope_rainfall` raster ကိုရွေးပါ
#. :guilabel:`Name of the field to create` တွင် ``suitable`` ဟုသတ်မှတ်ပါ (default field အမည်သည် ``DN`` - ဒစ်ဂျစ်တယ်ဂဏန်းဒေတာ ဖြစ်ပါသည်) 
#. Output ကို သိမ်းဆည်းပါ။ :guilabel:`Vectorized` အောက်တွင် :guilabel:`Save file as` ကိုရွေးပါ။ ဖိုင်လမ်းကြောင်းကို :file:`Rasterprac` တွင်သတ်မှတ်ပြီး ဖိုင်အမည်ကို :file:`aspect_slope_rainfall_all.shp` ဟုအမည်ပေးပါ။
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ
#. Processing ပြီးဆုံးသွားသောအခါ dialog ကိုပိတ်ပါ။

   .. figure:: img/vectorized.png
      :align: center

      Raster မှ Vector သို့ 

Raster ၏ဧရိယာများအားလုံးကို vector အဖြစ်သို့ ပြောင်းလဲပြီးဖြစ်ပါသည်၊ ထို့ကြောင့် ``suitable`` field ထဲတွင် တန်ဖိုး ``1`` ရှိသော ဧရိယာများကိုသာ ရွေးချယ်ရန် လိုအပ်ပါသည်။

#. Vector layer အသစ်အတွက် :guilabel:`Query Builder` dialog ကိုဖွင့်ပါ (right-click - 
   :guilabel:`Filter...`) 
#. အောက်ပါ query ကိုရေးပါ-::

     "suitable" = 1

#. :guilabel:`OK` ကိုနှိပ်ပါ
#. Query ပြီးဆုံးကြောင်း သေချာပါက (criteria ၃ ခုစလုံးနှင့်ကိုက်ညီသော၊ ဆိုလိုသည်မှာ တန်ဖိုး ``1`` ရှိသော၊ ဧရိယာများကိုသာ မြင်နိုင်လျှင်) layer ကို right-click နှိပ်ပြီး :menuselection:`Export --> Save Features As...` ကိုအသုံးပြု၍ ရလာဒ်များမှ vector ဖိုင်အသစ်တစ်ခု ဖန်တီးပါ
#. ဖိုင်ကို :file:`Rasterprac` ဖိုင်လမ်းကြောင်းတွင် သိမ်းဆည်းပါ
#. ဖိုင်ကို :file:`aspect_slope_rainfall_1.shp` ဟုအမည်ပေးပါ
#. မြေပုံမှ ``aspect_slope_rainfall_all`` layer ကိုဖယ်ရှားပါ
#. Project ကိုသိမ်းဆည်းပါ

Raster တစ်ခုကို vector အဖြစ်သို့ပြောင်းရန် algorithm တစ်ခုကိုအသုံးပြုသောအခါ တစ်ခါတရံတွင် algorithm သည် "Invalid geometries" ("ဆီလျော်မှုမရှိသောဂျီဩမေတြီများ") ဟူ၍ ထုတ်ပေးပါသည်၊ ဆိုလိုသည်မှာ နောက်ပိုင်း ဆန်းစစ်လေ့လာခြင်းတွင် အခက်အခဲဖြစ်စေနိုင်သော polygon အလွတ်များပါနေခြင်း၊ သို့မဟုတ် အမှားများပါဝင်သော polygon များရှိနေခြင်းတို့ဖြစ်သည်။ ထို့ကြောင့် "Fix Geometry" tool ကိုအသုံးပြုရန် လိုအပ်ပါသည်။

ဂျီဩမေတြီမှန်ကန်အောင်ပြုပြင်ခြင်း (Fixing geometry)
----------------------------------------------------------------------

#. :guilabel:`Processing Toolbox` ထဲတွင် "Fix geometries" ဟုရိုက်ရှာပြီး ၎င်းကို :guilabel:`Execute...` လုပ်ပါ။
#. :guilabel:`Input layer` အတွက် ``aspect_slope_rainfall_1`` ကိုရွေးပါ
#. :guilabel:`Fixed geometries` အောက်တွင် :guilabel:`Save file as` ကိုရွေးချယ်ပြီး output ကို :file:`fixed_aspect_slope_rainfall.shp` ဟူသောဖိုင်အမည်ဖြင့် :file:`Rasterprac` ဖိုင်လမ်းကြောင်းတွင် သိမ်းဆည်းပါ။
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ခြစ်ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ
#. Processing ပြီးဆုံးသွားသောအခါ dialog ကိုပိတ်ပါ

ယခုဆိုလျှင် raster ကို vector အဖြစ်သို့ပြောင်းလဲပြီး ရလာဒ် ဂျီဩမေတြီကို မှန်ကန်အောင်ပြုပြင်ပြီးဖြစ်ပါသည်။ ``fixed_aspect_slope_rainfall`` layer နှင့် ``rural_buffer`` layer နှစ်ခု ထိဖြတ်ခြင်း (intersection) ကိုရှာဖွေခြင်းဖြင့် Aspect ၊ slope နှင့် rainfall criteria များကို လူနေအိမ်များမှအကွာအဝေး (distance from human settlement) criteria ဖြင့် ပေါင်းစည်းနိုင်ပြီဖြစ်ပါသည်။

Vector များထိဖြတ်ခြင်းကို ဆုံးဖြတ်ခြင်း (Determining the Intersection of vectors)
----------------------------------------------------------------------------------

#. :menuselection:`Vector --> Geoprocessing Tools --> Intersection...` ကိုနှိပ်ပါ
#. ပေါ်လာသော dialog ထဲတွင် :guilabel:`Input layer` အနေဖြင့် ``rural_buffer`` layer ကိုရွေးပါ
#. :guilabel:`Overlay layer` အတွက်  ``fixed_aspect_slope_rainfall`` layer ကိုရွေးပါ
#. :guilabel:`Intersection` တွင် output ဖိုင်အား :file:`Rasterprac` ဖိုင်လမ်းကြောင်း၌ သိမ်းဆည်းပါ
#. Output ဖိုင်အား :file:`rural_aspect_slope_rainfall.shp` ဟုအမည်ပေးပါ
#. :guilabel:`Save` ကိုနှိပ်ပါ
#. :guilabel:`Run` ကိုနှိပ်ပြီး processing ပြီးဆုံးသည်အထိစောင့်ပါ
#. :guilabel:`Intersection` dialog ကိုပိတ်ပါ

   Intersection သည် မှန်မှန်ကန်ကန်အလုပ်ဖြစ်/မဖြစ်ကို ထပ်နေသည့်ဧရိယာများသာ ကျန်ရှိနေခြင်းကို ကြည့်၍ စစ်ဆေးပါ။
#. Project ကိုသိမ်းဆည်းပါ

သတ်မှတ်စာရင်းထဲရှိ နောက်ထပ် criteria မှာ ဧရိယာသည်  ``6000`` စတုရန်းမီတာထက် ကြီးရမည်ဖြစ်သည်။ ဤ project အတွက် သင့်တော်မည့်အရွယ်အစားရှိသည့် ဧရိယာများကို ဖော်ထုတ်ရန် polygon ဧရိယာများကို တွက်ချက်ပါမည်။

Polygon တစ်ခုချင်းစီအတွက် ဧရိယာတွက်ချက်ခြင်း (Calculating the area for each polygon)
-------------------------------------------------------------------------------------

#. Vector layer အသစ်တွင် right-click နှိပ်ပါ
#. :guilabel:`Open attribute table` ကိုရွေးပါ
#. ဇယား၏ဘယ်ဘက်အပေါ်ရှိ |toggleEditing| :sup:`Toggle editing` ခလုတ်ကိုနှိပ်ပါ၊ သို့မဟုတ် :kbd:`Ctrl+e` ကိုနှိပ်ပါ
#. ဇယား၏ အပေါ်တစ်လျှောက် toolbar ထဲရှိ |calculateField| :sup:`Open field calculator` ခလုတ်ကိုနှိပ်ပါ၊ သို့မဟုတ် :kbd:`Ctrl+i` ကိုနှိပ်ပါ
#. ပေါ်လာသော dialog ထဲတွင် |checkbox| :guilabel:`Create new field` ကိုအမှန်ခြစ်ခြစ်ထားပြီး :guilabel:`Output field name` တွင် ``area`` ဟုသတ်မှတ်ပါ။ Output field အမျိုးအစားသည် decimal number (real) ဖြစ်သင့်ပါသည်။ :guilabel:`Precision` တွင် ``1`` (ဒဿမတစ်နေရာ) ဟု သတ်မှတ်ပါ။
#. :guilabel:`Expression` ထဲတွင် အောက်ပါကို ရိုက်ထည့်ပါ-::

     $area

   ဆိုလိုသည်မှာ field calculator သည် vector layer ထဲရှိ polygon တစ်ခုချင်းစီ၏ ဧရိယာတွက်ချက်ပေးမည်ဖြစ်ပြီး integer column အသစ်တစ်ခု (``area`` ဟုခေါ်သော) ထဲတွင် တွက်ချက်ထားသောတန်ဖိုးကို ထည့်သွင်းပေးမည်ဖြစ်သည်။

   .. figure:: img/field_calculator_area.png
      :align: center

      Field Calculator  

#. :guilabel:`OK` ကိုနှိပ်ပါ
#. ``id`` ဟုခေါ်သော နောက်ထပ် field အသစ်ကိုလည်း ထည့်သွင်းပါ။ :guilabel:`Field calculator expression` ထဲတွင် အောက်ပါကို ရိုက်ထည့်ပါ-::

    $id

   ထိုသို့လုပ်ခြင်းသည် polygon တစ်ခုချင်းစီတွင် သီးခြား ID တစ်ခုစီရှိနေစေမည်ဖြစ်သည်။
#. |toggleEditing| :sup:`Toggle editing` ကိုထပ်မံ၍ နှိပ်ပါ၊ edit လုပ်ထားသည်များကို သိမ်းဆည်းမည်လား မေးမြန်းလာပါက သိမ်းဆည်းပေးပါ။

   .. figure:: img/attribute_table.png
      :align: center

      Area နှင့် id column များပါဝင်သော Attribute table

သတ်မှတ်အရွယ်အစားရှိသည့် ဧရိယာများကို ရွေးချယ်ခြင်း (Selecting areas of a given size)
-------------------------------------------------------------------------------------

ယခုဆိုလျှင် ဧရိယာများကို ရရှိပြီးဖြစ်ပါသည်-

#. ``6000`` စတုရန်းမီတာထက်ကြီးသော polygon များကိုသာ ရွေးချယ်ရန် query တစ်ခုတည်ဆောက်ပါ (ခါတိုင်းလိုပင်)။ Query သည်-::

     "area" > 6000

#. ရွေးချယ်ထားသည်များကို :file:`suitable_areas.shp` ဟူသောအမည်ဖြင့် vector layer အသစ်တစ်ခုအဖြစ် :file:`Rasterprac` ဖိုင်လမ်းကြောင်းတွင် သိမ်းဆည်းပါ။

ယခုဆိုလျှင် ရှားပါး fynbos အပင်အတွက် ပေါက်ရောက်နိုင်သည့် criteria များအားလုံးနှင့်ကိုက်ညီသော သင့်တော်သည့်ဧရိယာများ ရရှိပြီဖြစ်ပါသည်။ ထိုဧရိယာများထဲမှ University of Cape Town နှင့်အနီးဆုံးဖြစ်သော ဧရိယာ ၄ ခုကို ရွေးချယ်မည်ဖြစ်ပါသည်။

University of Cape Town ကို ဂျီဩမေတြီရေးဆွဲခြင်း (Digitize the University of Cape Town)
----------------------------------------------------------------------------------------

#. :file:`Rasterprac` ဖိုင်လမ်းကြောင်းထဲတွင် vector layer အသစ်တစ်ခုဖန်တီးပါ၊ သို့သော် ဤတစ်ကြိမ်တွင် :guilabel:`Geometry type` အနေဖြင့် :guilabel:`Point` ကိုအသုံးပြုပြီး ၎င်းကို :file:`university.shp` ဟု အမည်ပေးပါ။
#. ၎င်း၏ CRS ကိုမှန်ကန်အောင် ပြုလုပ်ပါ (``Project CRS:EPSG:32733 - WGS 84 / UTM zone 33S``)
#. :guilabel:`OK` နှိပ်ပြီး layer အသစ်ဖန်တီးခြင်းကို အဆုံးသတ်ပါ။
#. ``university`` layer အသစ်နှင့် ``Streets`` layer မှလွဲ၍ ကျန် layer များအားလုံးကို ဖျောက်ထားပါ။
#. နောက်ခံမြေပုံ (OSM) တစ်ခုထည့်သွင်းပါ-
   
   #. :guilabel:`Browser` panel မှတဆင့် :menuselection:`XYZ Tiles --> OpenStreetMap` သို့သွားပါ
   #. ``OpenStreetMap`` အား :guilabel:`Layers` panel ၏အောက်ခြေသို့ ဖိဆွဲ၍ရွှေ့ပါ

   Internet browser အသုံးပြုပြီး University of Cape Town ၏တည်နေရာကို ရှာဖွေပါ။ Cape Town ၏ ထူးခြားသောပထဝီဝင်အနေအထားအရ University သည် ထင်သာမြင်သာရှိသော တည်နေရာတွင်တည်ရှိပါသည်။ QGIS သို့ပြန်မသွားခင်တွင် University ၏တည်နေရာနှင့် အနီးအနားရှိနေရာများကို မှတ်သားထားပါ။
   
#. ``Streets`` layer ကို click လုပ်ထားပြီး ``university`` layer သည်  :guilabel:`Layers` panel ထဲတွင် highlight ဖြစ်နေအောင်လုပ်ထားပါ
#. :menuselection:`View --> Toolbars` menu item တွင် :guilabel:`Digitizing` ကိုရွေးချယ်ထားပါ။ ခဲတံပုံဖြင့် toolbar icon တစ်ခု (|toggleEditing| :sup:`Toggle editing`) ကိုမြင်တွေ့ရပါမည်။ ၎င်းသည် *Toggle Editing* ခလုတ်ဖြစ်ပါသည်။
#. *edit mode* ဖွင့်ရန် :guilabel:`Toggle editing` ခလုတ်ကိုနှိပ်ပါ။ ထိုသို့လုပ်ခြင်းဖြင့် vector layer တစ်ခုကို edit လုပ်နိုင်မည်ဖြစ်သည်။
#. |toggleEditing| :sup:`Toggle editing` ခလုတ်၏ အနီးအနားတွင်ရှိသော |capturePoint| :sup:`Add Point Feature` ခလုတ်ကိုနှိပ်ပါ
#. :guilabel:`Add feature` tool ပွင့်လာပါက University of Cape Town ၏တည်နေရာကို အကောင်းဆုံးခန့်မှန်းထားသောနေရာတွင် left-click နှိပ်ပါ
#. ``id`` ထည့်သွင်းရန် မေးမြန်းလာပါက ကိန်းပြည့် (integer) တစ်ခုထည့်ပေးပါ
#. :guilabel:`OK` ကိုနှိပ်ပါ
#. |saveEdits| :sup:`Save Layer Edits` ခလုတ်ကိုနှိပ်ပါ
#. Edit ပြုလုပ်နေသည်ကို ရပ်တန့်ရန် :guilabel:`Toggle editing` ခလုတ်ကိုနှိပ်ပါ
#. Project ကိုသိမ်းဆည်းပါ

University of Cape Town နှင့်အနီးဆုံး နေရာများကိုရှာဖွေခြင်း (Find the locations that are closest to the University of Cape Town)
----------------------------------------------------------------------------------------------------------------------------------

#. *Processing Toolbox* ထဲတွင် *Join Attributes by Nearest* algorithm (:menuselection:`Vector general --> Join Attributes by Nearest`) ကိုဖွင့်ပါ
#. :guilabel:`Input layer` သည် ``university`` ဖြစ်သင့်ပြီး :guilabel:`Input layer 2` သည် ``suitable_areas`` ဖြစ်သင့်ပါသည်။
#. သင့်တော်သော output ဖိုင်အမည်နှင့် ဖိုင်လမ်းကြောင်းတစ်ခုသတ်မှတ်ပါ (:guilabel:`Joined layer`)
#. :guilabel:`Maximum nearest neighbors` တွင် ``4`` ဟုသတ်မှတ်ပါ
#. |checkbox| :guilabel:`Open output file after running algorithm` ကိုအမှန်ခြစ်ထားပါ
#. ကျန်ရှိသော parameter များတွင် default တန်ဖိုးများအတိုင်း ထားပါ
#. :guilabel:`Run` ကိုနှိပ်ပါ

ရလာဒ် point layer တွင် feature ၄ ခုပါဝင်ပါလိမ့်မည် - ၎င်းတို့တွင် University ၏တည်နေရာနှင့် အချက်အလက်များအားလုံးပါရှိသည့်အပြင် အနီးအနားရှိ သင့်လျော်သည့် ဧရိယာများ၏ အချက်အလက်များ (``id`` အပါအဝင်) နှင့် ထို university တည်နေရာသို့ အကွာအဝေး အားလုံးပါရှိပါလိမ့်မည်။

#. Join (ချိတ်ဆက်) ထားသော ရလာဒ်၏ attribute ဇယားကိုဖွင့်ပါ
#. အနီးဆုံးဖြစ်သည့် သင့်တော်သောဧရိယာ ၄ ခု၏ ``id`` ကိုမှတ်သားထားပြီး attribute ဇယားကိုပိတ်ပါ
#. ``suitable_areas`` layer ၏ attribute ဇယားကိုဖွင့်ပါ
#. University နှင့်အနီးဆုံးဖြစ်သော သင့်တော်သည့်ဧရိယာ ၄ ခုကို ရွေးချယ်ရန် query တစ်ခုတည်ဆောက်ပါ (``id`` field ကိုအသုံးပြု၍ရွေးချယ်ခြင်း)

ဤအရာသည် သုတေသနမေးခွန်း၏ နောက်ဆုံးအဖြေဖြစ်ပါသည်။

နောက်ဆုံးရလာဒ်ကိုတင်ပြရန်အတွက် label အပြည့်အစုံထည့်သွင်းထားသော မြေပုံအပြင်အဆင် (layout) တစ်ခုဖန်တီးပါ၊ ထို layout ထဲတွင် DEM သို့မဟုတ် Slope raster ကဲ့သို့သော အောက်ခံတစ်ခုပေါ်တွင် အလင်းဖောက်နှုန်း ပမာဏတစ်ခုသတ်မှတ်ထားသည့် (semi-transparent) hillshade layer ထည့်သွင်းပါ၊ ထို့အပြင် University နှင့် ``suitable_areas`` layer ကိုထည့်သွင်းပေးကာ university နှင့်အနီးဆုံးဖြစ်သည့် သင့်တော်သော ဧရိယာ ၄ ခုကို highlight လုပ်ပေးပါ။ Output မြေပုံကို ဖန်တီးရာတွင် မြေပုံရေးဆွဲခြင်းအတွက် အကောင်းဆုံးအလေ့အထများ အားလုံးအတိုင်း လိုက်နာဆောင်ရွက်ပါ။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addOgrLayer| image:: /static/common/mActionAddOgrLayer.png
   :width: 1.5em
.. |addRasterLayer| image:: /static/common/mActionAddRasterLayer.png
   :width: 1.5em
.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |capturePoint| image:: /static/common/mActionCapturePoint.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataSourceManager| image:: /static/common/mActionDataSourceManager.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |projectionEnabled| image:: /static/common/mIconProjectionEnabled.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |saveEdits| image:: /static/common/mActionSaveEdits.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
