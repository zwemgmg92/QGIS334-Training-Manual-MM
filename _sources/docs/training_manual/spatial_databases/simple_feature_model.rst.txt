သင်ခန်းစာ - ရိုးရှင်းသော Feature Model (Lesson: Simple Feature Model)
===============================================================================

Database တစ်ခုထဲတွင် geographic feature များကို မည်သို့ သိုလှောင်သိမ်းဆည်းပြီး မည်သို့ ကိုယ်စားပြုဖော်ပြမည်နည်း? ဤသင်ခန်းစာတွင် OGC မှသတ်မှတ်ထားသော Simple Feature Model နည်းလမ်းတစ်ခုကို ပြသပေးမည်ဖြစ်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** SFS Model ဆိုတာဘာလဲနှင့် ၎င်းကို မည်သို့အသုံးပြုရမည်ကို လေ့လာရန်။

OGC ဆိုတာဘာလဲ (What is OGC)
-------------------------------------------------------------------------------

Open Geospatial Consortium (OGC) သည် အပြည်ပြည်ဆိုင်ရာ သဘောတူညီမှု စံနှုန်းအဖွဲ့အစည်းတစ်ခုဖြစ်ပြီး 1994 ခုနှစ်တွင် စတင်ဖွဲ့စည်းခဲ့ပါသည်။ OGC တွင် တစ်ကမ္ဘာလုံးရှိ ပုဂ္ဂလိကအဖွဲ့အစည်းများ၊ အစိုးရအဖွဲ့အစည်းများ၊ အမြတ်အစွန်းအတွက် မရည်ရွယ်သော အဖွဲ့အစည်းများနှင့် သုတေသနအဖွဲ့အစည်းများ ၃၇၀ ကျော် ပူးပေါင်းပါဝင်ပြီး ပထဝီဝင်ဆိုင်ရာအကြောင်းအရာများနှင့်ဝန်ဆောင်မှုများ၊ GIS data processing နှင့် data မျှဝေခြင်းများအတွက် စံချိန်စံနှုန်းများအကောင်အထည်ဖော်ဆောင်ခြင်းနှင့် ဖွံ့ဖြိုးတိုးတက်မှုများအားကောင်းစေရန် ပွင့်လင်းမြင်သာသောသဘောတူညီမှု လုပ်ငန်းစဉ်ကို လုပ်ဆောင်ကြပါသည်။ *- Wikipedia*

SFS Model ဆိုတာဘာလဲ (What is the SFS Model)
-------------------------------------------------------------------------------

SQL အတွက် Simple Feature (SFS) Model ဆိုသည်မှာ database တစ်ခုထဲတွင် geospatial data များကို သိမ်းဆည်းရန် *ဆက်စပ်တည်ရှိမှုအရဖွဲ့စည်းပုံမဟုတ်သော* *(non-topological)* နည်းလမ်းတစ်ခုဖြစ်ပြီး အဆိုပါ data များကို ရယူသုံးစွဲခြင်း၊ လုပ်ကိုင်ဆောင်ရွက်ခြင်းနှင့် တည်ဆောက်ခြင်းများအတွက် function များကို သတ်မှတ်ပေးပါသည်။

.. figure:: img/ogc_sfs.png
   :align: center

Model သည် Point ၊ Linestring နှင့် Polygon အမျိုးအစားများမှ geospatial data များကို သတ်မှတ်ပေးပါသည် (ထိုအမျိုးအစားများကို object များစွာအဖြစ်သို့ စုပေါင်းပေးပါသည်)။

နောက်ထပ်အချက်အလက်များအတွက် `OGC Simple Feature for SQL
<https://www.ogc.org/standards/sfs>`_ standard တွင် ကြည့်ရှုပါ။

ဇယားထဲသို့ ဂျီဩမေတြီ field တစ်ခုထည့်သွင်းခြင်း (Add a geometry field to table)
-------------------------------------------------------------------------------

People table ထဲသို့ point field တစ်ခု ထည့်သွင်းကြည့်ပါမည်-

.. code-block:: sql

  alter table people add column the_geom geometry;


ဂျီဩမေတြီအမျိုးအစားပေါ်အခြေခံပြီး constraint (ကန့်သတ်ချက်) တစ်ခုထည့်သွင်းခြင်း (Add a constraint based on geometry type)
-------------------------------------------------------------------------------------------------------------------------

ဂျီဩမေတြီ field အမျိုးအစားကို တိတိကျကျသတ်မှတ်ထားခြင်းမရှိသည်ကို သတိထားမိပါလိမ့်မည်- ထို့အတွက် constraint တစ်ခုလိုအပ်ပါသည်-

.. code-block:: sql

  alter table people
  add constraint people_geom_point_chk
      check(st_geometrytype(the_geom) = 'ST_Point'::text
            OR the_geom IS NULL);

ထို code သည် point ဂျီဩမေတြီတစ်ခု သို့မဟုတ် null တန်ဖိုးတစ်ခုကိုသာ လက်ခံသော constraint တစ်ခုကို table ထဲသို့ ထည့်သွင်းပေးမည်ဖြစ်သည်။

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ (Try Yourself:) :abbr:`★★★ (Advanced level)`
-------------------------------------------------------------------------------

Cities ဟုခေါ်သော table အသစ်တစ်ခုကို ဖန်တီးပြီး သင့်လျော်သော column အချို့ကို ထည့်သွင်းပါ၊ polygon များ (city နယ်နိမိတ်များ) သိမ်းဆည်းရန်အတွက် ဂျီဩမေတြီ field တစ်ခုပါဝင်အောင် ထည့်သွင်းပါ။ ဂျီဩမေတြီများသည် polygon များဖြစ်ရမည်ဆိုသည့် constraint တစ်ခု ပါရှိအောင် ထည့်သွင်းပါ။

.. admonition:: အဖြေ
   :class: dropdown

   ::

     create table cities (id serial not null primary key,
                          name varchar(50),
                          the_geom geometry not null);
      alter table cities
      add constraint cities_geom_point_chk
      check (st_geometrytype(the_geom) = 'ST_Polygon'::text );



geometry_columns ဇယားအား ဖြည့်သွင်းခြင်း (Populate geometry_columns table)
-------------------------------------------------------------------------------

ဤအဆင့်တွင် ``geometry_columns`` table ထဲသို့ entry တစ်ခုကိုလည်း ထည့်သွင်းသင့်ပါသည်-

.. code-block:: sql

  insert into geometry_columns values
    ('','public','people','the_geom',2,4326,'POINT');

အကြောင်းရင်းမှာ database ထဲရှိ မည်သည့် table များထဲတွင် ဂျီဩမေတြီ data များပါဝင်သည်ကို သိရှိစေရန် :kbd:`geometry_columns` ကိုအသုံးပြုသောကြောင့်ဖြစ်သည်။

.. note::

   အထက်ဖော်ပြပါ ``INSERT`` statement သည် error ဖြစ်နေပါက အောက်ပါ query ကို ဦးစွာ run ပါ-
   
   .. code-block:: sql

     select * from geometry_columns;

   :kbd:`f_table_name` column တွင် :kbd:`people` တန်ဖိုးပါဝင်ပါက ထို table သည် register ပြုလုပ်ပြီးသားဖြစ်ကာ နောက်ထပ်မည်သည့်အရာမှ ထပ်လုပ်ရန် မလိုအပ်တော့ပါ။

တန်ဖိုး ``2`` သည် dimension အရေအတွက်ကို ရည်ညွှန်းပါသည်၊ ဤဥပမာတွင် **X**
နှင့် **Y** ဖြစ်ပါသည်။

:kbd:`4326` သည် အသုံးပြုနေသော projection ကို ရည်ညွှန်းပါသည်၊ ဤဥပမာတွင် 4326 သည် WGS84 ဖြစ်ပါသည် (EPSG အကြောင်းရှင်းပြထားသော အပိုင်းကို ကိုးကားပါ)။

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ (Try Yourself:) :abbr:`★☆☆ (Basic level)`
...............................................................................

Cities layer အသစ်အတွက် သင့်လျော်သော `geometry_columns` entry တစ်ခုကို ထည့်သွင်းပါ။

.. admonition:: အဖြေ
   :class: dropdown

   ::

     insert into geometry_columns values
           ('','public','cities','the_geom',2,4326,'POLYGON');



SQL အသုံးပြု၍ ဇယားထဲသို့ ဂျီဩမေတြီ record ထည့်သွင်းခြင်း (Add geometry record to table using SQL)
--------------------------------------------------------------------------------------------------

ယခုအခါ table များသည် geo-enable ဖြစ်နေပြီး table များထဲတွင် ဂျီဩမေတြီများကို သိမ်းဆည်းနိုင်ပြီဖြစ်ပါသည်-

.. code-block:: sql

  insert into people (name,house_no, street_id, phone_no, the_geom)
          values ('Fault Towers',
                   34,
                   3,
                   '072 812 31 28',
                   'SRID=4326;POINT(33 -33)');

.. note:: အထက်တွင် ထည့်သွင်းထားသော entry အသစ်ထဲတွင် သင်အသုံးပြုလိုသော projection (SRID) ကို သတ်မှတ်ပေးရန် လိုအပ်ပါလိမ့်မည်။ Point အသစ်၏ ဂျီဩမေတြီကို ထည့်သွင်းရာတွင် စာသား string ကိုအသုံးပြုထားသောကြောင့် မှန်ကန်သော projection အချက်အလက်ကို အလိုအလျောက်ထည့်သွင်းပေးမည်မဟုတ်ပါ။ Point အသစ်သည် ထည့်သွင်းထားပြီးသော data-set နှင့် SRID တူညီရန် လိုအပ်ပါသည်။

   ဤနေရာတွင် graphical interface တစ်ခုကို အသုံးပြုသည်ဆိုပါက point တစ်ခုချင်းစီအတွက် projection သတ်မှတ်ခြင်းသည် အလိုအလျောက်ဖြစ်ပါလိမ့်မည်။ တစ်နည်းအားဖြင့် data-set အတွက် projection သတ်မှတ်ထားပြီးသားဖြစ်ပါက ထည့်သွင်းလိုသော point တိုင်းအတွက် မှန်ကန်သော projection သတ်မှတ်ရန် မလိုအပ်တော့ပါ။

ယခုအခါ QGIS ကိုဖွင့်ပြီး :kbd:`people` table ကိုဖွင့်ကြည့်ပါ။ ထို့အပြင် record များကို edit လုပ်ခြင်း၊ ပေါင်းထည့်ခြင်း၊ ဖျက်ပစ်ခြင်းများကိုလည်း စမ်းလုပ်ကြည့်ပါ၊ ထို့နောက် data ပြောင်းလဲသွားမှုများကို ကြည့်ရှုရန် database ထဲတွင် select query များလုပ်ဆောင်ကြည့်ပါ။

QGIS ထဲတွင် PostGIS layer တစ်ခု ထည့်သွင်းရန် :menuselection:`Layer --> Add PostGIS Layers` menu option သို့မဟုတ် toolbar ခလုတ်ကို အသုံးပြုပါ-

  |addPostgisLayer|

အောက်ပါ dialog ပွင့်လာပါလိမ့်မည်-

.. figure:: img/add_postgis_layer_dialog.png
   :align: center

အောက်ပါ dialog ကိုဖွင့်ရန် :guilabel:`New` ခလုတ်ကို နှိပ်ပါ-

.. figure:: img/new_postgis_connection.png
   :align: center

ထို့နောက် connection အသစ်တစ်ခုကို သတ်မှတ်ပါ၊ ဥပမာ-::

  Name: myPG
  Service:
  Host: localhost
  Port: 5432
  Database: address
  User:
  Password:

QGIS သည် :kbd:`address` database ကို ရှာတွေ့/မတွေ့ကြည့်ရှုရန်နှင့် username နှင့် password မှန်ကန်မှုရှိ/မရှိ ကြည့်ရှုရန် :guilabel:`Test Connect` ကိုနှိပ်ပါ။ ၎င်းသည် အလုပ်ဖြစ်ပါက :guilabel:`Save Username` နှင့် :guilabel:`Save Password` ဘေးရှိ box များတွင် အမှန်ခြစ်ခြစ်ပါ။ ထို့နောက် connection ကိုဖန်တီးရန် :guilabel:`OK` ကိုနှိပ်ပါ။

:guilabel:`Add PostGIS Layers` dialog ထဲတွင် :guilabel:`Connect` ကိုနှိပ်ပြီး project ထဲသို့ layer များကိုထည့်သွင်းပါ။

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ (Try Yourself:) :abbr:`★★☆ (Moderate level)`
...............................................................................

Person တစ်ဦး၏ name ၊ street name နှင့် တည်နေရာ (the_geom column မှ) ကို plain text အနေဖြင့် ပြသသည့် query တစ်ခုကို ရေးသားပါ။

.. admonition:: အဖြေ
   :class: dropdown

   ::

     select people.name,
            streets.name as street_name,
            st_astext(people.the_geom) as geometry
     from   streets, people
     where  people.street_id=streets.id;

   ရလာဒ်-::

            name     | street_name |   geometry
       --------------+-------------+---------------
        Roger Jones  | High street |
        Sally Norman | High street |
        Jane Smith   | Main Road   |
        Joe Bloggs   | Low Street  |
        Fault Towers | Main Road   | POINT(33 -33)
       (5 rows)

   မြင်တွေ့ရသည့်အတိုင်း constraint သည် database ထဲသို့ null တန်ဖိုးများကို ထည့်သွင်းခွင့်ပြုပါသည်။


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Spatial object များကို database ထဲသို့ မည်သို့ထည့်သွင်းရမည်နှင့် ၎င်းတို့ကို GIS software ထဲတွင် မည်သို့ကြည့်ရှုရမည်ကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် database ထဲသို့ data များထည့်သွင်းနည်းနှင့် database ထဲမှ data များ export ထုတ်ယူနည်းများကို လေ့လာရမည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addPostgisLayer| image:: /static/common/mActionAddPostgisLayer.png
   :width: 1.5em
