သင်ခန်းစာ - ထည့်သွင်းခြင်းနှင့် ထုတ်ယူခြင်း (Lesson: Import and Export)
===============================================================================

Database တစ်ခုထဲသို့ data များထည့်သွင်းခြင်းနှင့် database တစ်ခုထဲမှ data များထုတ်ယူခြင်းကို လွယ်လွယ်ကူကူလုပ်ဆောင်နိုင်ရန် tool များစွာ ရှိပါသည်။

shp2pgsql
-------------------------------------------------------------------------------

shp2pgsql သည် ESRI Shapefile ကို database ထဲသို့ ထည့်သွင်းရန်အသုံးပြုသည့် commandline tool တစ်ခုဖြစ်ပါသည်။ Unix တွင် PostGIS table အသစ်တစ်ခု ထည့်သွင်းခြင်းအတွက် အောက်ပါ command ကိုအသုံးပြုနိုင်ပါသည်-

.. code-block:: bash

  shp2pgsql -s <SRID> -c -D -I <path to shapefile> <schema>.<table> | \
    psql -d <databasename> -h <hostname> -U <username>

Windows တွင် import ပြုလုပ်ရာ၌ အဆင့် ၂ ဆင့်ဖြင့် လုပ်ဆောင်ရပါမည်-

.. code-block:: bash

  shp2pgsql -s <SRID> -c -D -I <path to shapefile> <schema>.<table> > import.sql
  psql psql -d <databasename> -h <hostname> -U <username> -f import.sql

အောက်ပါ error ကိုကြုံတွေ့ရနိုင်ပါသည်-

.. code-block:: bash

  ERROR:  operator class "gist_geometry_ops" does not exist for access method
  "gist"

ထို error သည် သင်ထည့်သွင်းနေသော data အတွက် spatial index တစ်ခု၏ *in situ* ကိုဖန်တီးရာတွင် ကြုံတွေ့နေကြဖြစ်သော ပြဿနာတစ်ခုဖြစ်ပါသည်။ ထို error မဖြစ်ပေါ်စေရန် ``-I`` parameter ကို ထည့်သွင်းအသုံးမပြုပါနှင့်။ ထိုသို့ ထည့်သွင်းအသုံးမပြုပါက spatial index ကို တိုက်ရိုက် ဖန်တီးပေးမည်မဟုတ်ပဲ data ထည့်သွင်းပြီးမှသာ database ထဲတွင် ၎င်း index ကို ဖန်တီးရန်လိုအပ်ပါလိမ့်မည်။ (Spatial index တစ်ခုဖန်တီးခြင်းကို နောက်လာမည့်သင်ခန်းစာတွင် လေ့လာရမည်ဖြစ်သည်)

pgsql2shp
-------------------------------------------------------------------------------

pgsql2shp သည် PostGIS table များ၊ View များ သို့မဟုတ် SQL select query များကို export ထုတ်ရာတွင် အသုံးပြုသည့် commandline tool တစ်ခုဖြစ်ပါသည်။ Unix တွင် လုပ်ဆောင်ရန်-

.. code-block:: bash

  pgsql2shp -f <path to new shapefile> -g <geometry column name> \
    -h <hostname> -U <username> <databasename> <table | view>

Query တစ်ခုကိုအသုံးပြု၍ data ကို export ထုတ်ယူရန်-

.. code-block:: bash

  pgsql2shp -f <path to new shapefile> -g <geometry column name> \
    -h <hostname> -U <username> "<query>"

ogr2ogr
-------------------------------------------------------------------------------

ogr2ogr သည် data များကို postgis မှ အခြား data format များစွာသို့ အပြန်အလှန်ပြောင်းလဲပေးနိုင်သော အလွန်အသုံးဝင်သည့် tool တစ်ခုဖြစ်ပါသည်။ ogr2ogr သည် GDAL library ၏ တစ်စိတ်တစ်ပိုင်းဖြစ်ပြီး သီးခြား install ပြုလုပ်ပေးရပါမည်။ PostGIS မှ table တစ်ခုကို GML သို့ export ထုတ်ယူရန် အောက်ပါ command ကိုအသုံးပြုနိုင်ပါသည်-

.. code-block:: bash

  ogr2ogr -f GML export.gml PG:'dbname=<databasename> user=<username>
          host=<hostname>' <Name of PostGIS-Table>

DB Manager
-------------------------------------------------------------------------------

:guilabel:`Database` menu ထဲတွင် :guilabel:`DB Manager` ဟုခေါ်သော option ရှိပါသည်။ ၎င်း tool တွင် PostGIS အပါအဝင် spatial database များဖြင့် အပြန်အလှန်လုပ်ကိုင်ဆောင်ရွက်နိုင်စေရန်အတွက် တစ်စုတစ်စည်းတည်းပေါင်းစည်းထားသော interface တစ်ခုပါဝင်ပါသည်။ ၎င်းသည် database များထဲမှ အခြား format များသို့ export ထုတ်ယူခြင်းနှင့် အခြား format များမှ database များထဲသို့ import လုပ်ယူခြင်းများကိုလည်း လုပ်ဆောင်နိုင်ပါသည်။ အဆိုပါ tool အသုံးပြုခြင်းကို နောက်လာမည့်မော်ဂျူးတွင် သီးသန့်လေ့လာရမည်ဖြစ်သည့်အတွက် ယခုမော်ဂျူးတွင် အကျဉ်းချုံးမျှသာ ဖော်ပြခြင်းဖြစ်ပါသည်။


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Database ထဲမှ/ထဲသို့ data များ export ထုတ်ယူခြင်းနှင့် import လုပ်ခြင်းကို နည်းလမ်းအမျိုးမျိုးဖြင့် လုပ်ဆောင်နိုင်ပါသည်။ အထူးသဖြင့် မတူညီသော data source များကိုအသုံးပြုသောအခါ ပုံမှန်အားဖြင့် အဆိုပါ function များ (သို့မဟုတ် အလားတူ အခြားအရာများ) ကို အသုံးပြုရပါလိမ့်မည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် ကျွန်ုပ်တို့ဖန်တီးခဲ့ပြီးသော data များကို မည်ကဲ့သို့ query ပြုလုပ်ရမည်ကို လေ့လာရမည်ဖြစ်ပါသည်။
