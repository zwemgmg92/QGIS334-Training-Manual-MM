သင်ခန်းစာ - Spatial Database များဖြင့်အလုပ်လုပ်ရန် QGIS ထဲတွင် DB Manager ကိုအသုံးပြုခြင်း (Lesson: Using DB Manager to work with Spatial Databases in QGIS)
=============================================================================================================================================================

QGIS ဖြင့်သာမက အခြားသော tool များဖြင့် database လုပ်ဆောင်မှုများစွာကို မည်သို့ဆောင်ရွက်ရမည်ကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်၊ ယခုအခါတွင် ထိုကဲ့သို့သော တူညီသည့်လုပ်ဆောင်မှုများအပြင် စီမံခန့်ခွဲမှုဆိုင်ရာ tool များကို အသုံးပြုနိုင်သော DB Manager ကိုလေ့လာမည်ဖြစ်သည်။


**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** QGIS DB Manager အသုံးပြု၍ spatial database များဖြင့် အပြန်အလှန်လုပ်ဆောင်နည်းကို လေ့လာရန်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - DB Manager ဖြင့် PostGIS Database များကို စီမံခြင်း (Follow Along: Managing PostGIS Databases with DB Manager)
------------------------------------------------------------------------------------------------------------------------------------------------------------

Menu ရှိ :menuselection:`Database --> DB Manager --> DB Manager` ကိုရွေးချယ်ပြီး သို့မဟုတ် toolbar ရှိ |dbManager| :sup:`DB Manager` icon ကိုရွေးချယ်ပြီး DB Manager ကို ဦးစွာဖွင့်ပါ။

ယခင်က configure ပြုလုပ်ထားသော connection များကို တွေ့ရမည်ဖြစ်ပြီး ``myPG`` အပိုင်း နှင့် ၎င်း၏ ``public`` schema ကို ဖြန့်ကြည့်ကာ ယခင်အပိုင်းများတွင်လုပ်ဆောင်ခဲ့သော table များကို မြင်တွေ့နိုင်ပါသည်။

Database ထဲတွင်ပါဝင်သော Schemas အကြောင်း metadata အချို့ကို မြင်တွေ့နိုင်ပါသည်။

.. figure:: img/db_manager_dialog.png
   :align: center

Schemas များသည် data table များနှင့်အခြား object များကို PostgreSQL database တစ်ခုထဲတွင် အုပ်စုဖွဲ့ပေးသည့်နည်းလမ်းတစ်ခုဖြစ်ပြီး လုပ်ဆောင်ခွင့်များနှင့်အခြား ကန့်သတ်ချက်များအတွက် container တစ်ခုဖြစ်ပါသည်။ ဤလက်စွဲတွင်  PostgreSQL schemas များ စီမံခန့်ခွဲခြင်းအကြောင်း ပါဝင်မည်မဟုတ်ပါ၊ သို့သော် ထိုအကြောင်းပိုမိုသိရှိလိုပါက `PostgreSQL documentation on Schemas
<https://www.postgresql.org/docs/9.1/ddl-schemas.html>`_ တွင်ကြည့်နိုင်ပါသည်။ Schemas အသစ်များဖြစ်တီးရန် DB Manager ကိုအသုံးပြုနိုင်ပါသည်၊ သို့သော် ၎င်းတို့ကို ထိရောက်စွာ စီမံခန့်ခွဲနိုင်ရန် pgAdmin III ကဲ့သို့ tool တစ်ခု သို့မဟုတ် command line interface ကိုအသုံးပြုရန် လိုအပ်ပါသည်။

DB Manager ကို database အတွင်းရှိ table များကို စီမံခန့်ခွဲရန်လည်း အသုံးပြုနိုင်ပါသည်။ Command line ဖြင့် table များဖန်တီးခြင်းနှင့် စီမံခန့်ခွဲခြင်းကို နည်းအမျိုးမျိုးဖြင့် လေ့လာခဲ့ပြီးဖြစ်ပါသည်၊ သို့သော် ယခုအခါ DB Manager ထဲတွင် လုပ်ဆောင်မည်ဖြစ်သည်။

ပထမဦးစွာ table နာမည်ကို click နှိပ်ပြီး :guilabel:`Info` tab ထဲတွင် table ၏ metadata ကိုကြည့်ပါ။

.. figure:: img/table_info.png
   :align: center

ဤ panel ထဲတွင် table အကြောင်း :guilabel:`ယေဘုယျအချက်အလက်` များအပြင် PostGIS extension မှ သိမ်းဆည်းထားသော ဂျီဩမေတြီနှင့် တည်နေရာရည်ညွှန်းစနစ်အကြောင်းအချက်အလက်များ တွေ့နိုင်ပါသည်။

:guilabel:`Info` tab ထဲတွင် အောက်သို့ဆက်ကြည့်ပါက သင်ကြည့်နေသော table အတွက် :guilabel:`Fields` ၊ :guilabel:`Constraints`
နှင့် :guilabel:`Indexes` အကြောင်း အချက်အလက်များကို ပိုမိုတွေ့နိုင်ပါသည်။

.. figure:: img/table_info_fields.png
   :align: center


Layer တစ်ခု၏ attribute table ကို ကြည့်သကဲ့သို့ပင် database ထဲရှိ record များကိုရိုးရှင်းစွာ ကြည့်ရှုရန် DB Manager ကိုအသုံးပြုလျှင်လည်း အလွန်အသုံးဝင်ပါသည်။ :guilabel:`Table` tab ကိုဖွင့်ပြီး data များကို ရှာဖွေကြည့်ရှုနိုင်ပါသည်။

.. figure:: img/table_panel.png
   :align: center

Layer data ကို မြေပုံ preview တစ်ခုထဲတွင် ပြသပေးသော :guilabel:`Preview` tab တစ်ခုလည်းပါရှိပါသည်။

Tree ထဲရှိ layer တစ်ခုပေါ်တွင် right click နှိပ်ပြီး :guilabel:`Add to Canvas` ကိုနှိပ်ပါက ထို layer ကို မြေပုံထဲသို့ ထည့်သွင်းပေးမည်ဖြစ်သည်။

ယခုအချိန်ထိ database schemas ၊ table များနှင့် ၎င်းတို့၏ metadata များကို ကြည့်ရှုနေခြင်းသာဖြစ်ပါသည်၊ သို့သော် နောက်ထပ် column တစ်ခုထည့်သွင်းရန် table ကို ပြောင်းလဲလိုပါက မည်သို့လုပ်ဆောင်မည်နည်း? ထိုကိစ္စကို DB Manager ထဲတွင် တိုက်ရိုက်လုပ်ဆောင်နိုင်ပါသည်။

#. Tree ထဲရှိ edit လုပ်လိုသော table ကို ရွေးချယ်ပါ။
#. Menu မှ :menuselection:`Table --> Edit Table` ကိုရွေးချယ်ပါ၊ :guilabel:`Table Properties` dialog ပွင့်လာပါမည်။ 

   .. figure:: img/edit_table.png
      :align: center

Column များထည့်သွင်းရန်၊ ဂျီဩမေတြီ columns များထည့်သွင်းရန်၊ ရှိနေပြီးသား column များကို edit လုပ်ရန် သို့မဟုတ် column တစ်ခုကို လုံးဝဖယ်ရှားပစ်ရန် အဆိုပါ dialog ကို အသုံးပြုနိုင်ပါသည်။

:guilabel:`Constraints` tab ထဲတွင် မည်သည့် field များကို primary key အဖြစ်အသုံးပြုမည်ကို စီမံနိုင်သလို ရှိနေပြီးသား constraint များကို ဖယ်ရှားပစ်နိုင်ပါသည်။

.. figure:: img/constraints_panel.png
   :align: center

Spatial index များနှင့် သာမန် index များ နှစ်မျိုးစလုံးကို ထည့်သွင်းရန်နှင့် ဖျက်ပစ်ရန်အတွက် :guilabel:`Indexes` tab ကိုအသုံးပြုနိုင်ပါသည်။

.. figure:: img/indexes_panel.png
   :align: center
 
:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - Table အသစ်တစ်ခုဖန်တီးခြင်း (Follow Along: Creating a New Table)
-------------------------------------------------------------------------------------------------------------

Database ထဲရှိ ရှိနေပြီးသား table များဖြင့် လုပ်ဆောင်ခြင်းလုပ်ငန်းစဉ်ကို သိရှိပြီးဖြစ်ပါသည်၊ DB Manager အသုံးပြုပြီး table အသစ်တစ်ခုဖန်တီးကြည့်ပါမည်။

#. DB Manger ကိုမဖွင့်ရသေးပါက ဖွင့်ပြီး database ထဲရှိ ရှိနေပြီးသား table များစာရင်းကို မြင်ရသည်အထိ ဖြန့်ကြည့်ပါ။
#. Menu မှ :guilabel:`Table --> Create Table` ကိုရွေးချယ်ပါ၊ Create Table dialog ပေါ်လာပါမည်။
#. Default ``Public`` schema ကိုအသုံးပြုပြီး table ကို ``places`` ဟုနာမည်ပေးပါ။
#. အောက်တွင်ပြထားသည့်အတိုင်း ``id`` ၊ ``place_name`` နှင့် ``elevation`` field များကို ထည့်သွင်းပါ။
#. ``id`` field ကို primary key အဖြစ်သတ်မှတ်ထားပါ။
#. :guilabel:`Create geometry column` ကိုအမှန်ခြစ်ပြီး ၎င်းကို ``POINT`` အမျိုးအစားသတ်မှတ်ပါ၊ Name တွင် ``geom`` ဟုပေးပြီး :guilabel:`SRID` တွင် ``4326`` ဟုသတ်မှတ်ပါ။
#. :guilabel:`Create spatial index` တွင် အမှန်ခြစ်ပြီး :guilabel:`Create` ကိုနှိပ်ကာ table ကိုဖန်တီးပါ။

   .. figure:: img/create_table.png
      :align: center
 
#. Table ဖန်တီးပြီးကြောင်းဖော်ပြသော dialog ကိုပိတ်ပြီး Create Table Dialog ကို ပိတ်ရန် :guilabel:`Close` ကိုနှိပ်ပါ။

ယခုအခါ DB Manager ထဲတွင် သင့် table ကို စစ်ဆေးကြည့်နိုင်ပြီး table ထဲတွင် မည်သည့် data မှမရှိသေးသည်ကို တွေ့ရပါလိမ့်မည်။ Menu တွင် :guilabel:`Editing` ကိုဖွင့်ပြီး table ထဲသို့ နေရာများစတင်ထည့်သွင်းနိုင်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - အခြေခံ Database စီမံခန့်ခွဲခြင်း (Follow Along: Basic Database Administration)
----------------------------------------------------------------------------------------------------------------------------

DB Manager တွင် အခြေခံ database စီမံခန့်ခွဲခြင်းအလုပ်များကိုလည်း လုပ်ဆောင်နိုင်ပါသည်။ ၎င်းကို ပိုမိုပြည့်စုံသော database စီမံခန့်ခွဲခြင်း tool တစ်ခုအစား အစားထိုးအသုံးပြုရန်မဟုတ်သော်လည်း database ပြုပြင်ထိန်းသိမ်းရာတွင် အသုံးပြုနိုင်သော လုပ်ဆောင်ချက်အချို့ပါရှိပါသည်။

Database table များသည် အတော်အတန်ကြီးမားလာနိုင်ပါသည်၊ ကြိမ်ဖန်များစွာ မွမ်းမံပြင်ဆင်ထားသော table များမှ မှတ်တမ်း အကြွင်းအကျန်များကျန်ရှိနေနိုင်ပြီး ၎င်းမှတ်တမ်းများကို PostgreSQL မှနောက်ထပ်လိုအပ်တော့မည်မဟုတ်ပါ။ ထိုသို့သော မလိုအပ်သည်များကို  *VACUUM* command ဖြင့်ရှင်းလင်းပစ်နိုင်ပြီး ကျစ်ကျစ်လစ်လစ်ဖြစ်စေကာ table များကို ခွဲခြမ်းစိတ်ဖြာရာတွင် ပိုမိုကောင်းမွန်လာစေပါသည်။

DB Manager အတွင်းတွင် *VACUUM ANALYZE* command ကို မည်ကဲ့သို့လုပ်ဆောင်နိုင်မည်ကို ကြည့်ကြပါမည်။

#. DB Manager Tree ထဲရှိ table တစ်ခုခုကို ရွေးချယ်ပါ။
#. Menu မှ :menuselection:`Table --> Run Vacuum Analyze` ကိုရွေးပါ

PostgreSQL သည် လုပ်ဆောင်မှုကို စတင်မည်ဖြစ်ပြီး table ၏အရွယ်အစားပေါ်မူတည်ပြီး လုပ်ဆောင်ချိန်ကြာမြင့်နိုင်ပါသည်။

VACUUM ANALYZE လုပ်ငန်းစဉ်အကြောင်း အချက်အလက်များကို `PostgreSQL Documentation on VACUUM ANALYZE
<https://www.postgresql.org/docs/9.1/sql-vacuum.html>`_ တွင် ရှာဖွေဖတ်ရှုနိုင်ပါသည်။

:abbr:`★☆☆ (Basic level)` လိုက်လုပ်ကြည့်ပါ - DB Manger ဖြင့် SQL Query များလုပ်ဆောင်ခြင်း (Follow Along: Executing SQL Queries with DB Manager)
------------------------------------------------------------------------------------------------------------------------------------------------

DB Manger ဖြင့် database table များအတွက် query များရေးသားနိုင်ပြီး ရလာဒ်များကို ကြည့်ရှုနိုင်ပါသည်။ ထိုသို့သော လုပ်ဆောင်ချက်ကို :guilabel:`Browser` panel ထဲတွင် မြင်တွေ့ခဲ့ပြီးဖြစ်ပါသည်၊ သို့သော် ယခုအခါ DB Manager ဖြင့်လုပ်ဆောင်မည်ဖြစ်သည်။

#. Tree ထဲရှိ ``lines`` table ကိုရွေးချယ်ပါ။
#. DB Manager toolbar ထဲရှိ :guilabel:`SQL window` ခလုတ်ကိုရွေးပါ။

   .. figure:: img/sql_window_btn.png
      :align: center

#. အောက်ပါ :guilabel:`SQL query` ကိုရေးသားပါ::

       select * from lines where roadtype = 'major';

#. Query ကို run ရန် :guilabel:`Execute (F5)` ခလုတ်ကိုနှိပ်ပါ။
#. ကိုက်ညီမှုရှိသော record များကို :guilabel:`Result` panel ထဲတွင် မြင်တွေ့သင့်ပါသည်။

   .. figure:: img/sql_results.png
      :align: center

#. ရလာဒ်များကို မြေပုံထဲသို့ ထည့်သွင်းရန် :guilabel:`Load as new layer` ကို အမှန်ခြစ်ပါ။
#. :guilabel:`Column with unique integer values` တွင် ``id`` column ကိုရွေးချယ်ပြီး :guilabel:`Geometry column` တွင် ``geom`` column ကိုရွေးချယ်ပါ။
#. :guilabel:`Layer name (prefix)` တွင် ``roads_primary`` ဟုရိုက်ထည့်ပါ
#. ရလာဒ်များကို layer အသစ်တစ်ခုအနေဖြင့် မြေပုံထဲသို့ထည့်သွင်းရန် :guilabel:`Load now!` ကိုနှိပ်ပါ။
 
   .. figure:: img/sql_add_to_map.png
      :align: center

Query နှင့်ကိုက်ညီသော layer များကို မြေပုံပေါ်တွင် ပြသပေးမည်ဖြစ်သည်။ ယခင် မော်ဂျူးများနှင့် အပိုင်းများတွင် လုပ်ဆောင်ခဲ့သော မည်သည့် SQL command မျိုးကိုမဆို ဤ query tool အသုံးပြုပြီး လုပ်ဆောင်နိုင်ပါသည်။

DB Manager အသုံးပြု၍ Database ထဲသို့ Data များထည့်သွင်းခြင်း (Importing Data into a Database with DB Manager)
--------------------------------------------------------------------------------------------------------------

Command line tool များအသုံးပြု၍ spatial database တစ်ခုထဲသို့ data များထည့်သွင်းနည်းကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်၊ ထို့ကြောင့် ယခုအခါ DB Manager သုံး၍ data ထည့်သွင်းနည်းကို လေ့လာပါမည်။

#. DB Manager dialog ၏ toolbar တွင်ရှိသော :guilabel:`Import layer/file` ခလုတ်ကို နှိပ်ပါ။

   .. figure:: img/import_layer_btn.png
      :align: center

#. Input dataset အနေဖြင့် :file:`exercise_data/projected_data` ထဲရှိ :file:`urban_33S.shp` ဖိုင်ကို ရွေးချယ်ပါ
#. Form တန်ဖိုးအချို့ကို ကြိုတင်ဖြည့်သွင်းရန် :guilabel:`Update Options` ခလုတ်ကို နှိပ်ပါ။
#. :guilabel:`Create new table` option ကိုရွေးချယ်ပေးထားပါ။
#. :guilabel:`Source SRID` တွင် ``32722`` ဟုသတ်မှတ်ပြီး :guilabel:`Target SRID` တွင် ``4326`` ဟုသတ်မှတ်ပါ။
#. :guilabel:`Create Spatial Index` ကို အမှန်ခြစ်ပါ။
#. ထည့်သွင်းမှုလုပ်ဆောင်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။

   .. figure:: img/import_urban.png
      :align: center

#. ထည့်သွင်းမှုအောင်မြင်ကြောင်း ပြသပေးသည့် dialog ကိုပိတ်လိုက်ပါ။
#. DB Manager Toolbar ပေါ်ရှိ :guilabel:`Refresh` ခလုတ်ကိုနှိပ်ပါ။

Tree ထဲမှ table ပေါ်တွင် click နှိပ်ပြီး database ထဲရှိ table ကိုစစ်ဆေးနိုင်ပါသည်။ :guilabel:`Spatial ref:` တွင် ``WGS 84 (4326)`` အနေဖြင့်ဟုတ်/မဟုတ် စစ်ဆေးခြင်းဖြင့် data ကို projection ပြောင်းလဲထားကြောင်း အတည်ပြုနိုင်ပါသည်။

.. figure:: img/urban_info.png
   :align: center

Tree ထဲရှိ table ပေါ်တွင် right click နှိပ်ပြီး :guilabel:`Add to Canvas` ကိုရွေးပါက table ကို layer တစ်ခုအနေဖြင့် မြေပုံထဲသို့ ထည့်သွင်းပေးမည်ဖြစ်ပါသည်။

DB Manager အသုံးပြု၍ Database တစ်ခုမှ Data များထုတ်ယူခြင်း (Exporting Data from a Database with DB Manager)
------------------------------------------------------------------------------------------------------------

Spatial database များမှ data များ export ထုတ်ယူရန် DB Manager ကိုအသုံးပြုနိုင်ပါသည်၊ မည်သို့လုပ်ဆောင်ရမည်ကို ကြည့်ပါမည်။

#. Tree ထဲရှိ ``lines`` layer ကိုရွေးချယ်ပြီး toolbar ရှိ :guilabel:`Export to File` ခလုတ်ကိုနှိပ်ပါ၊ :guilabel:`Export to vector file` dialog ပွင့်လာပါလိမ့်မည်။
#. :guilabel:`Output file` ကိုရွေးချယ်ရန် :guilabel:`...` ခလုတ်ကိုနှိပ်ပြီး :file:`exercise_data` ဖိုင်လမ်းကြောင်းထဲတွင် :file:`urban_4326` နာမည်ဖြင့် data ကိုသိမ်းဆည်းပါ။
#. :guilabel:`Target SRID` တွင် ``4326`` ဟုသတ်မှတ်ပါ။
#. Export ထုတ်ခြင်းကို စတင်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။

   .. figure:: img/export_to_vector.png
      :align: center

#. Export ထုတ်ခြင်းအောင်မြင်ကြောင်း ပြသပေးသည့် dialog ကိုပိတ်ပြီး DB Manager ကိုပိတ်လိုက်ပါ။

သင်ဖန်တီးထားသော shapefile ကို Browser panel ဖြင့် စစ်ဆေးကြည့်နိုင်ပါသည်။

.. figure:: img/inspect_vector_output.png
   :align: center

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

ယခုအခါ spatial database များကို စီမံခန့်ခွဲရန်၊ SQL query များလုပ်ဆောင်ရန်နှင့် data များ import/export ပြုလုပ်ရန် QGIS ထဲတွင် DB Manager interface အသုံးပြုနည်းကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် အဆိုပါနည်းစနစ်များကို *SpatiaLite* database များဖြင့် အသုံးပြုနည်းကို လေ့လာရမည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
