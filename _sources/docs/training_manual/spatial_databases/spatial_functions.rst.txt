သင်ခန်းစာ - PostGIS Setup လုပ်ခြင်း (Lesson: PostGIS Setup)
===============================================================================

PostGIS function များကို setup ပြုလုပ်ခြင်းဖြင့် PostgreSQL အတွင်းမှ spatial function များကို ရယူသုံးစွဲစေနိုင်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Spatial function များကို install ပြုလုပ်ရန်နှင့် ၎င်းတို့၏အကျိုးကျေးဇူးများကို အတိုချုံးနမူနာပြသရန်။

.. note:: ဤလေ့ကျင့်ခန်းတွင် PostGIS ဗားရှင်း 2.1 သို့မဟုတ် ပိုမြင့်သောဗားရှင်းကို အသုံးပြုသည်ဟု ယူဆပါမည်။ ဗားရှင်းအဟောင်းများအတွက် install ပြုလုပ်ခြင်း နှင့် database configuration သည် ကွာခြားပါသည်၊ သို့သော် ဤမော်ဂျူးထဲရှိ ကျန်ရှိသောအပိုင်းများသည် အတူတူပင်ဖြစ်ပါသည်။ Install ပြုလုပ်ခြင်းနှင့် database configuration အတွက် သင်အသုံးပြုသည့် platform နှင့်သက်ဆိုင်သည့် documentation ကိုဖတ်ရှုပါ။

Ubuntu တွင် Install ပြုလုပ်ခြင်း (Installing under Ubuntu)
-------------------------------------------------------------------------------

PostGIS ကို apt မှ အလွယ်တကူ install ပြုလုပ်ပါသည်။

.. code-block:: bash

  $ sudo apt install postgresql
  $ sudo apt install postgis

အမှန်တကယ်ကို လွယ်ကူပါသည်။

.. note:: Install ပြုလုပ်မည့် ဗားရှင်းအတိအကျသည် သင်အသုံးပြုနေသော Ubuntu ဗားရှင်းနှင့် configure ပြုလုပ်ထားသော repository များပေါ်တွင် မူတည်ပါသည်။ Install ပြုလုပ်ပြီးနောက် psql သို့မဟုတ် အခြား tool ဖြင့် ``select PostGIS_full_version();`` query ကိုအသုံးပြုပြီး ဗားရှင်းကိုစစ်ဆေးနိုင်ပါသည်။

ဗားရှင်း အတိအကျကို install ပြုလုပ်ရန် (ဥပမာ- PostgreSQL ဗားရှင်း 13 နှင့် PostGIS 3) အောက်ပါ command များကို အသုံးပြုနိုင်ပါသည်။

.. code-block:: bash

  $ sudo apt install wget ca-certificates
  $ sudo lsb_release -a 
  $ wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
  $ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'
  $ sudo apt-get update
  $ sudo apt install postgis postgresql-13-postgis-3


Windows တွင် Install ပြုလုပ်ခြင်း (Installing under Windows)
-------------------------------------------------------------------------------

Windows တွင် install ပြုလုပ်ခြင်းကို သာမန် Window installation dialog များကို အသုံးပြု၍ binary package များမှ လုပ်ဆောင်နိုင်ပါသည်။ 

ဦးစွာ `ဒေါင်းလုဒ်စာမျက်နှာ <https://www.postgresql.org/download/>`_ ကိုဝင်ကြည့်ပါ။ ထို့နောက် `ဤလမ်းညွှန်ချက်
<https://www.bostongis.com/PrinterFriendly.aspx?content_name=postgis_tut01>`_ အတိုင်း လုပ်ဆောင်ပါ။

Windows တွင် install ပြုလုပ်ခြင်းအကြောင်း ပိုမိုသိရှိလိုပါက `PostGIS website <https://postgis.net/windows_downloads>`_ တွင် တွေ့နိုင်ပါသည်။

အခြား Platform များတွင် Install ပြုလုပ်ခြင်း (Installing on Other Platforms)
-------------------------------------------------------------------------------

`PostGIS website download <https://postgis.net/install/>`_ တွင် macOS နှင့် အခြား Linux အခွဲများပေါ်တွင် install ပြုလုပ်ခြင်းအကြောင်း အချက်အလက်များရှိပါသည်။


PostGIS အသုံးပြုရန် Database များကို ပြင်ဆင်သတ်မှတ်ခြင်း (Configuring Databases to use PostGIS)
------------------------------------------------------------------------------------------------

PostGIS ကို install ပြုလုပ်ပြီးသည်နှင့် extension များကိုအသုံးပြုနိုင်စေရန် database ကို configure ပြုလုပ်ရန်လိုအပ်ပါသည်။ PostGIS ဗားရှင်း 2.0 နှင့်အထက်ကို install ပြုလုပ်ထားပါက ယခင်လေ့ကျင့်ခန်းမှ address database ကိုအသုံးပြုပြီး psql တွင် အောက်ပါ command ကိုရေးသားပြီး ရိုးရိုးရှင်းရှင်းလုပ်ဆောင်နိုင်ပါသည်။

.. code-block:: bash

  $ psql -d address -c "CREATE EXTENSION postgis;"

.. note:: ထည့်သွင်းထားသော ဗားရှင်းပေါ်မူတည်၍ database တစ်ခုကို spatial အရ အသုံးပြုနိုင်အောင် ပြုလုပ်ပေးရမည့်ညွှန်ကြားချက်များကို https://postgis.net/docs/postgis_administration.html#create_spatial_db တွင် ရှာဖွေတွေ့ရှိနိုင်ပါသည်။

Install ပြုလုပ်ထားသော PostGIS function များကို ရှာဖွေခြင်း (Looking at the installed PostGIS functions)
--------------------------------------------------------------------------------------------------------

PostgreSQL ၏ပင်မလုပ်ဆောင်နိုင်စွမ်းများကို တိုးချဲ့ပေးသော in-database function များအစုအစည်းတစ်ခုအဖြစ် PostGIS ကို မှတ်ယူနိုင်ပါသည်၊ သို့မှသာ ၎င်းသည် spatial data များဖြင့် လုပ်ကိုင်ဆောင်ရွက်နိုင်မည်ဖြစ်သည်။ သိုလှောင်သိမ်းဆည်းခြင်း၊ ထုတ်ယူခြင်း၊ query ပြုလုပ်ခြင်းနှင့် ကိုင်တွယ်ခြင်းများ လုပ်ဆောင်နိုင်ခြင်းဖြစ်သည်။ ထိုအရာများလုပ်ဆောင်နိုင်ရန် database ထဲတွင် function တော်တော်များများကို install ပြုလုပ်ပေးထားပါသည်။

ယခုအခါ PostGIS ကြောင့် ကျွန်ုပ်တို့၏ PostgreSQL ``address`` database ကို geospatial အရ အသုံးပြုနိုင်ပြီဖြစ်ပါသည်။ ၎င်းကို နောက်လာမည့်အပိုင်းများတွင် ပိုမိုအသေးစိတ်လေ့လာမည်ဖြစ်သည်၊ သို့သော် အခုအခါတွင်တော့ အမြည်းအနေဖြင့်သာ ပြသပေးပါသည်။ စာသား (text) မှ point တစ်ခုကို ဖန်တီးလိုသည့် ဆိုကြပါစို့။ ဦးစွာ point နှင့်ပတ်သက်သော function များကိုရှာဖွေရန် psql command ကိုအသုံးပြုပါသည်။ ``address`` database နှင့်မချိတ်ဆက်ရသေးလျှင် အခုချိတ်ဆက်ပြီး အောက်ပါကို run ပါ- 

.. code-block:: psql

  \df *point*

ထို command သည် :kbd:`st_pointfromtext` ကိုရှာဖွေသည့် command ဖြစ်ပါသည်။ စာရင်းတွင် ရှာဖွေရန် down arrow ကိုအသုံးပြုပါ၊ ထို့နောက် psql shell သို့ ပြန်သွားရန် :kbd:`Q` ကိုနှိပ်ပါ။

အောက်ပါ command ကို run ကြည့်ပါ-

.. code-block:: sql

  select st_pointfromtext('POINT(1 1)');

ရလာဒ်-

.. code-block:: sql

  st_pointfromtext
  --------------------------------------------
  0101000000000000000000F03F000000000000F03F
  (1 row)

မှတ်သားရမည့် အချက် ၃ ချက်မှာ-

* :kbd:`POINT(1 1)` ကိုအသုံးပြုပြီး တည်နေရာ 1, 1 တွင် point တစ်ခုကို သတ်မှတ်ခဲ့ပါသည် (EPSG:4326 ဟုယူဆပါသည်)၊
* sql statement တစ်ခုကို run ခဲ့ပါသည်၊ သို့သော် table တစ်ခုပေါ်တွင် run ခြင်းမဟုတ်ပဲ SQL prompt မှ ထည့်သွင်းထားသော data ပေါ်တွင်သာ run ခြင်းဖြစ်ပါသည်၊
* ရလာဒ် row သည် အဓိပ္ပါယ်သိပ်မရှိပါ။

ရလာဒ် row သည် 'Well Known Binary' (WKB) ဟုခေါ်သော OGC format ဖြင့်ဖြစ်နေပါသည်။ ဤ format အကြောင်း အသေးစိတ်ကို နောက်လာမည့်အပိုင်းတွင် တွေ့ရမည်ဖြစ်သည်။

ရလာဒ်ကို စာသားအနေဖြင့် ပြန်ရရှိရန် function စာရင်းထဲတွင် စာသားအဖြစ်ပြန်ထုတ်ပေးသော function ကို ခပ်မြန်မြန်ရှာဖွေကြည့်နိုင်ပါသည်-

.. code-block:: psql

  \df *text

ကျွန်ုပ်တို့ရှာဖွေနေသည့် query သည် ``st_astext`` ဖြစ်ပါသည်။ ၎င်း query ကို ယခင်က ရေးသားခဲ့သော query နှင့် ပေါင်းစပ်ကြည့်ပါမည်-

.. code-block:: sql

  select st_astext(st_pointfromtext('POINT(1 1)'));

ရလာဒ်-

.. code-block:: sql

   st_astext
  ------------
    POINT(1 1)
    (1 row)

ဤနေရာတွင် :kbd:`POINT(1,1)` စာသားကို ထည့်သွင်းပေးပြီး :kbd:`st_pointfromtext()` ကိုအသုံးပြုပြီး point တစ်ခုအဖြစ်သို့ ပြောင်းလဲပေးပါသည်၊ ထို့နောက် ၎င်းကို :kbd:`st_astext()` အသုံးပြုပြီး လူများဖတ်ရှုနိုင်သော ပုံစံတစ်ခုသို့ ပြောင်းလဲပေးပါသည်။

PostGIS ကိုအသေးစိတ်အသုံးပြုခြင်းသို့ မသွားမီ နောက်ဆုံးဥပမာတစ်ခုမှာ-

.. code-block:: sql

  select st_astext(st_buffer(st_pointfromtext('POINT(1 1)'),1.0));

၎င်း query သည် point ပတ်ပတ်လည်တွင် 1 ဒီဂရီ buffer တစ်ခုဖန်တီးပေးပြီး text (စာသား) အနေဖြင့် ပြန်ထုတ်ပေးပါသည်။

တည်နေရာဆိုင်ရာရည်ညွှန်းစနစ်များ (Spatial Reference Systems)
-------------------------------------------------------------------------------

PostGIS function များအပြင် European Petroleum Survey Group (EPSG) မှသတ်မှတ်ထားသော spatial reference system (SRS) အဓိပ္ပါယ်သတ်မှတ်ချက်များ ပါရှိပါသည်။ Coordinate
reference system (CRS) ပြောင်းလဲခြင်းကဲ့သို့သော လုပ်ဆောင်မှုများတွင် ၎င်းတို့ကို အသုံးပြုပါသည်။

Database ထဲတွင် အဆိုပါ SRS definition များကို စစ်ဆေးကြည့်နိုင်ပါသည်၊ ၎င်းတို့ကို သာမန် database table များထဲတွင် သိုလှောင်သိမ်းဆည်းထားသောကြောင့် ဖြစ်ပါသည်။

ဦးစွာ psql prompt ထဲတွင် အောက်ပါ command ကိုရိုက်ထည့်ပြီး table ၏ schema ကို ကြည့်ပါ-

.. code-block:: psql

  \d spatial_ref_sys

ရလာဒ်သည် အောက်ပါအတိုင်းဖြစ်သင့်ပါသည်-

.. code-block:: sql

  Table "public.spatial_ref_sys"
     Column   |          Type           | Modifiers
   -----------+-------------------------+-----------
    srid      | integer                 | not null
    auth_name | character varying(256)  |
    auth_srid | integer                 |
    srtext    | character varying(2048) |
    proj4text | character varying(2048) |
    Indexes:
  "spatial_ref_sys_pkey" PRIMARY KEY, btree (srid)

စံ SQL query များကို အသုံးပြုပြီး ဤ table ကို ကြည့်ရှုခြင်းနှင့် ကိုင်တွယ်ခြင်းများ လုပ်ဆောင်နိုင်ပါသည် (မိတ်ဆက်ကဏ္ဍတွင် လေ့လာခဲ့သည့်အတိုင်း)။

သင်စိတ်ဝင်စားသည့် SRID တစ်ခုမှာ EPSG:4326 ဖြစ်ပါသည် - WGS 84 ellipsoid  ကိုအသုံးပြုထားသော geographic / lat lon reference system ဖြစ်ပါသည်။ ၎င်းကို ကြည့်ကြပါစို့-

.. code-block:: sql

  select * from spatial_ref_sys where srid=4326;

ရလာဒ်-

.. code-block:: sql

  srid      | 4326
  auth_name | EPSG
  auth_srid | 4326
  srtext    | GEOGCS["WGS 84",DATUM["WGS_1984",SPHEROID["WGS
  84",6378137,298.257223563,AUTHORITY["EPSG","7030"]],TOWGS84[0,
  0,0,0,0,0,0],AUTHORITY["EPSG","6326"]],PRIMEM["Greenwich",0,
  AUTHORITY["EPSG","8901"]],UNIT["degree",0.01745329251994328,
  AUTHORITY["EPSG","9122"]],AUTHORITY["EPSG","4326"]]
  proj4text | +proj=longlat +ellps=WGS84 +datum=WGS84 +no_defs


:kbd:`srtext` သည် well known text ဖြင့်ရေးထားသော projection definition ဖြစ်ပါသည် (၎င်းကို shapefile အစုထဲရှိ .prj ဖိုင်များထဲတွင် တွေ့နိုင်ပါသည်)။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

ယခုအခါ PostgreSQL ကော်ပီထဲတွင် PostGIS function များကို install ပြုလုပ်ပြီးဖြစ်ပါသည်။ PostGIS ၏ ကျယ်ပြန့်သော spatial function များကို အသုံးပြုနိုင်ပြီဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

Database တစ်ခုထဲတွင် spatial feature များကို မည်သို့ကိုယ်စားပြုဖော်ပြသည်ကို နောက်လာမည့်သင်ခန်းစာတွင် လေ့လာရမည်ဖြစ်ပါသည်။
