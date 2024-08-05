သင်ခန်းစာ - Data Model အကောင်အထည်ဖော်ခြင်း (Lesson: Implementing the Data Model)
=================================================================================

သီအိုရီအားလုံးကို လေ့လာပြီးဖြစ်ပါသည်၊ database အသစ်တစ်ခုကို ဖန်တီးကြည့်ပါမည်။ ဤ database ကို နောက်လာမည့် သင်ခန်းစာများအတွက် လေ့ကျင့်ခန်းများတွင် အသုံးပြုသွားမည်ဖြစ်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** လိုအပ်သော software install ပြုလုပ်ပြီး နမူနာ database စတင်ရာတွင် အသုံးပြုရန်။

PostgreSQL Install လုပ်ခြင်း (Install PostgreSQL)
-------------------------------------------------------------------------------

.. note:: သင့် ကွန်ပျူတာအတွက် PostgreSQL package များနှင့် installation ညွှန်ကြားချက်များကို  https://www.postgresql.org/download/ တွင် တွေ့နိုင်ပါသည်။ သတိထားရမည်မှာ documentation သည် Ubuntu တွင် run နေသော QGIS အတွက်ဖြစ်ပါသည်။

Under Ubuntu:

.. code-block:: bash

  sudo apt install postgresql-9.1

အောက်ပါအတိုင်း message ရရှိပါလိမ့်မည်-

.. code-block:: bash

  [sudo] password for qgis:
  Reading package lists... Done
  Building dependency tree
  Reading state information... Done
  The following extra packages will be installed:
  postgresql-client-9.1 postgresql-client-common postgresql-common
  Suggested packages:
  oidentd ident-server postgresql-doc-9.1
  The following NEW packages will be installed:
  postgresql-9.1 postgresql-client-9.1 postgresql-client-common postgresql-common
  0 upgraded, 4 newly installed, 0 to remove and 5 not upgraded.
  Need to get 5,012kB of archives.
  After this operation, 19.0MB of additional disk space will be used.
  Do you want to continue [Y/n]?

:kbd:`Y` ကိုနှိပ်ပြီး :kbd:`Enter` ကိုနှိပ်ပါ၊ ဒေါင်းလုဒ်နှင့် installation ပြီးဆုံးသည်အထိ စောင့်ပါ။

အကူအညီ (Help)
-------------------------------------------------------------------------------

PostgreSQL တွင် အလွန်ကောင်းသော `online
<https://www.postgresql.org/docs/9.1/index.html>`_ documentation ရှိပါသည်။

Database user တစ်ခုဖန်တီးခြင်း (Create a database user)
-------------------------------------------------------------------------------

Under Ubuntu:

Installation ပြီးဆုံးသွားသောအခါ postgres user ဖြစ်လာစေရန် အောက်ပါ command ကို run ပြီးနောက် database user အသစ်တစ်ခုဖန်တီးပါ-

.. code-block:: bash

  sudo su - postgres

မေးမြန်းလာပါက သာမန် log in password ရိုက်ထည့်ပါ (sudo right များရှိရန်လိုအပ်ပါသည်)။

ယခုအခါ postgres user ၏ bash prompt တွင် database user ကိုဖန်တီးပါ။ User name သည် unix login name နှင့်ကိုက်ညီရပါမည်- အဆိုပါ user အနေဖြင့် login ဝင်သောအခါ postgres သည် အလိုအလျောက် authenticate လုပ်ပေးပါလိမ့်မည်-

.. code-block:: bash

  createuser -d -E -i -l -P -r -s qgis

မေးမြန်းလာပါက password ရိုက်ထည့်ပါ။ Login password နှင့်မတူသော password တစ်ခုကို အသုံးပြုသင့်ပါသည်။

အဆိုပါ option များသည် ဘာကိုဆိုလိုပါသလဲ?

.. code-block:: bash

  -d, --createdb     role can create new databases
  -E, --encrypted    encrypt stored password
  -i, --inherit      role inherits privileges of roles it is a member of (default)
  -l, --login        role can login (default)
  -P, --pwprompt     assign a password to new role
  -r, --createrole   role can create new roles
  -s, --superuser    role will be superuser

ယခုအခါ အောက်ပါကိုရိုက်ပြီး postgres user ၏ bash shell environment မှ ထွက်ပါ-

.. code-block:: bash

  exit

အကောင့်အသစ်ကို အတည်ပြုခြင်း (Verify the new account)
-------------------------------------------------------------------------------

::

  psql -l

အောက်ပါပုံစံအတိုင်း ပြန်ထုတ်ပေးပါလိမ့်မည်::


    Name      |  Owner   | Encoding | Collation  |   Ctype    |
    ----------+----------+----------+------------+------------+
    postgres  | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 |
    template0 | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 |
    template1 | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 |
    (3 rows)

ထွက်ရန် :kbd:`Q` ဟုရိုက်ထည့်ပါ။

Database တစ်ခုဖန်တီးခြင်း (Create a database)
-------------------------------------------------------------------------------

Database အသစ်တစ်ခုဖန်တီးရန်  ``createdb`` command ကိုအသုံးပြုပါသည်။ ၎င်းကို bash shell prompt မှ run သင့်ပါသည်-

.. code-block:: psql

  createdb address -O qgis

Database အသစ် ရှိမရှိကို အောက်ပါ command အသုံးပြုပြီး အတည်ပြုနိုင်ပါသည်-

.. code-block:: psql

  psql -l

အောက်ပါပုံစံအတိုင်း ပြန်ထုတ်ပေးပါလိမ့်မည်-

.. code-block:: psql

  Name      |  Owner   | Encoding | Collation  |   Ctype    |   Access privileges
  ----------+----------+----------+------------+------------+-----------------------
  address   | qgis     | UTF8     | en_ZA.utf8 | en_ZA.utf8 |
  postgres  | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 |
  template0 | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 | =c/postgres: postgres=CTc/postgres
  template1 | postgres | UTF8     | en_ZA.utf8 | en_ZA.utf8 | =c/postgres: postgres=CTc/postgres
  (4 rows)

ထွက်ရန် :kbd:`Q` ဟုရိုက်ထည့်ပါ။

Database shell session တစ်ခုစတင်ခြင်း (Starting a database shell session)
-------------------------------------------------------------------------------

အောက်ပါအတိုင်း database ကို အလွယ်တကူ ချိတ်ဆက်နိုင်ပါသည်::

  psql address

psql database shell မှထွက်ရန် အောက်ပါကို ရိုက်ထည့်ပါ::

  \q

Shell အသုံးပြုရာတွင် အကူအညီရယူရန် အောက်ပါကို ရိုက်ထည့်ပါ::

  \?

sql command များအသုံးပြုရာတွင် အကူအညီရယူရန် အောက်ပါကို ရိုက်ထည့်ပါ::

  \help

သီးသန့် commnad တစ်ခုနှင့်ပတ်သက်ပြီး အကူအညီရယူရန် အောက်ပါကို ရိုက်ထည့်ပါ (ဥပမာ)::

  \help create table

`Psql cheat sheet <http://www.postgresonline.com/downloads/special_feature/postgresql90_cheatsheet_A4.pdf>`_ တွင်လည်း ကြည့်ရှုပါ။


SQL ထဲတွင် ဇယားများပြုလုပ်ခြင်း (Make Tables in SQL)
-------------------------------------------------------------------------------

Table အချို့ ပြုလုပ်ကြည့်ပါမည်။ ER Diagram ကို guide အနေဖြင့် အသုံးပြုပါမည်။ ဦးစွာ address db နှင့်ချိတ်ဆက်ပါ-

.. code-block:: sql

  psql address

ထို့နောက် :file:`streets` table တစ်ခုကို ဖန်တီးပါ-

.. code-block:: sql

  create table streets (id serial not null primary key, name varchar(50));

:kbd:`serial` နှင့် :kbd:`varchar` သည် **data types** များဖြစ်ကြပါသည်။ Record အသစ်တိုင်းအတွက် :kbd:`id` အလိုအလျောက်ထုတ်ပေးရန် :kbd:`serial` သည် PostgreSQL ကို integer sequence တစ်ခုအစပြုစေခြင်းဖြစ်ပါသည်။ :kbd:`varchar(50)` သည် အလျား 50 character ရှိသော field တစ်ခုကို ဖန်တီးစေပါသည်။

Command တွင် :kbd:`;` ဖြင့်အဆုံးသတ်သည် ကို သတိထားမိပါလိမ့်မည်၊ SQL command အားလုံး ထိုအတိုင်းပင်ဖြစ်ပါသည်။ :kbd:`Enter` နှိပ်သောအခါ psql သည် အောက်ပါအတိုင်း report လုပ်ပေးပါလိမ့်မည်-

.. code-block:: sql

  NOTICE:  CREATE TABLE will create implicit sequence "streets_id_seq"
           for serial column "streets.id"
  NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index
           "streets_pkey" for table "streets"
  CREATE TABLE

ဆိုလိုသည်မှာ table ကို အောင်မြင်စွာ ဖန်တီးပြီးဖြစ်ကာ primary key :kbd:`streets_pkey` နှင့် :kbd:`streets.id` ကိုအသုံးပြုထားပါသည်။

မှတ်ချက်- :kbd:`;` မပါရှိပဲ Enter နှိပ်လျှင် :kbd:`address-#` ကဲ့သို့ prompt တစ်ခုရရှိပါလိမ့်မည်။ အဘယ့်ကြောင့်ဆိုသော PG သည် ထပ်မံရိုက်ထည့်စေလိုသောကြောင့်ဖြစ်သည်။ Commnad ကို run ရန် :kbd:`;` ကိုထည့်ပါ။

Table schema ကိုကြည့်ရှုရန် အောက်ပါအတိုင်း လုပ်နိုင်ပါသည်-

.. code-block:: psql

  \d streets

အောက်ပါပုံစံအတိုင်း ပြသသင့်ပါသည်-

.. code-block:: sql

  Table "public.streets"
  Column  |         Type          |            Modifiers
  --------+-----------------------+--------------------------------------
   id     | integer               | not null default
          |                       | nextval('streets_id_seq'::regclass)
   name   | character varying(50) |
  Indexes:
    "streets_pkey" PRIMARY KEY, btree (id)

Table အကြောင်းအရာများကို ကြည့်ရှုရန် အောက်ပါအတိုင်း လုပ်နိုင်ပါသည်-

.. code-block:: sql

  select * from streets;

အောက်ပါပုံစံအတိုင်း ပြသသင့်ပါသည်-

.. code-block:: sql

   id | name
   ---+------
   (0 rows)

သင်မြင်တွေ့ရသည့်အတိုင်း Table သည် လက်ရှိတွင် ဗလာ ဖြစ်နေပါသည်။

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ (Try Yourself:) :abbr:`★★☆ (Moderate level)`
...............................................................................

အထက်တွင်ဖော်ပြခဲ့သောနည်းအတိုင်း people ဟုခေါ်သော table တစ်ခုပြုလုပ်ပါ-

Phone number ၊ home address ၊ name ၊ အစရှိသည့် field များကို ထည့်သွင်းပါ (နာမည်များဆီလျော်မှုမရှိပါက ဆီလျော်မှုရှိသော နာမည်များ ပြောင်းလဲပါ)။ အထက်တွင်ဖော်ပြခဲ့သည့်အတိုင်း data-type တူညီသော ID column တစ်ခု table တွင် ထည့်သွင်းပါ။

.. admonition:: အဖြေ
  :class: dropdown

  မှန်ကန်သော people table ကိုဖန်တီးရန် လိုအပ်သော SQL မှာ::

    create table people (id serial not null primary key,
                         name varchar(50),
                         house_no int not null,
                         street_id int not null,
                         phone_no varchar null );

  Table အတွက် schema သည် (``\\d people`` ဟုရိုက်ထည့်ပါ) အောက်ပါအတိုင်းဖြစ်ပါမည်::

    Table "public.people"

    Column     |         Type          |                      Modifiers
    -----------+-----------------------+-------------------------------------
    id         | integer               | not null default
               |                       | nextval('people_id_seq'::regclass)
    name       | character varying(50) |
    house_no   | integer               | not null
    street_id  | integer               | not null
    phone_no   | character varying     |
    Indexes:
      "people_pkey" PRIMARY KEY, btree (id)

  ပုံဖော်ပြသခြင်းဖြစ်သည့်အတွက် fkey constraint ကို ရည်ရွယ်ချက်ရှိရှိ ချန်ထားပါသည်။

SQL ထဲတွင် Key များဖန်တီးခြင်း (Create Keys in SQL)
-------------------------------------------------------------------------------

အထက်ပါကိစ္စအတွက် ပြဿနာမှာ database သည် people နှင့် streets တွင် logical relationship တစ်ခုရှိသည်ကို မသိရှိပါ။ ထို relationship ကို ဖော်ပြရန် streets table ၏ primary key ကို ညွှန်ပြသော foreign key တစ်ခုကို သတ်မှတ်ပေးရပါမည်။

.. figure:: img/er-people-streets.png
   :align: center

ထိုသို့လုပ်ဆောင်ရန် နည်းလမ်း ၂ ခုရှိပါသည်-

* Table ကိုဖန်တီးပြီးမှ key ထည့်သွင်းခြင်း
* Table ဖန်တီးချိန်တွင် key ကိုသတ်မှတ်ခြင်း

Table သည် ဖန်တီးပြီးသားဖြစ်နေပါသည်၊ ထို့ကြောင့် ပထမနည်းလမ်းဖြင့် လုပ်ကြည့်ပါမည်-

.. code-block:: sql

  alter table people
    add constraint people_streets_fk foreign key (street_id) references streets(id);


:kbd:`people` table ၏ :kbd:`street_id` field သည် :kbd:`streets` table မှ ဆီလျော်မှုရှိသော street :kbd:`id` နှင့် ကိုက်ညီမှုရှိရမည်ဖြစ်ကြောင်း ဆိုလိုခြင်းဖြစ်ပါသည်။

Constraint တစ်ခုကိုဖန်တီးရန် ပုံမှန်နည်းလမ်းမှာ table ဖန်တီးသောအခါ ၎င်းကို ဖန်တီးရန်ဖြစ်သည်-

.. code-block:: psql

  create table people (id serial not null primary key,
                       name varchar(50),
                       house_no int not null,
                       street_id int references streets(id) not null,
                       phone_no varchar null);

  \d people

Constraint ထည့်သွင်းပြီးသောအခါ table schema သည် အောက်ပါပုံစံအတိုင်း ဖြစ်နေပါမည်-

.. code-block:: sql

  Table "public.people"

    Column   |         Type          |            Modifiers
  -----------+-----------------------+---------------------------------
   id        | integer               | not null default
             |                       | nextval('people_id_seq'::regclass)
   name      | character varying(50) |
   house_no  | integer               | not null
   street_id | integer               | not null
   phone_no  | character varying     |
  Indexes:
    "people_pkey" PRIMARY KEY, btree (id)
  Foreign-key constraints:
    "people_streets_fk" FOREIGN KEY (id) REFERENCES streets(id)

SQL ထဲတွင် Index များဖန်တီးခြင်း (Create Indexes in SQL)
-------------------------------------------------------------------------------

ကျွန်ုပ်တို့သည် People နာမည်များကို လျင်လျင်မြန်မြန်ရှာဖွေလိုပါသည်။ ထိုသို့လုပ်ဆောင်ရန် people table ၏ name column တွင် index တစ်ခုဖန်တီးပေးနိုင်ပါသည်-

.. code-block:: psql

  create index people_name_idx on people(name);

  \d people

ရလာဒ်အနေဖြင့်-

.. code-block:: sql

  Table "public.people"

    Column   |         Type          |                      Modifiers
  -----------+-----------------------+-----------------------------------
   id        | integer               | not null default nextval
             |                       | ('people_id_seq'::regclass)
   name      | character varying(50) |
   house_no  | integer               | not null
   street_id | integer               | not null
   phone_no  | character varying     |
  Indexes:
   "people_pkey" PRIMARY KEY, btree (id)
   "people_name_idx" btree (name)    <-- new index added!
  Foreign-key constraints:
   "people_streets_fk" FOREIGN KEY (id) REFERENCES streets(id)

SQL ထဲတွင် Table များကို ဖြုတ်ချန်/ဖျက်ခြင်း (Dropping Tables in SQL)
-------------------------------------------------------------------------------

Table တစ်ခုကို ဖျက်ပစ်လိုပါက :kbd:`drop` command ကိုအသုံးပြုနိုင်ပါသည်-

.. code-block:: sql

  drop table streets;

လက်ရှိဥပမာတွင် အထက်ပါ commnad သည် အလုပ်မဖြစ်ပါ၊ အဘယ့်ကြောင့်ပါလဲ?

.. admonition:: အဖြေ
  :class: dropdown

  ဤကိစ္စတွင် DROP command အလုပ်မလုပ်ရခြင်း၏ အကြောင်းရင်းမှာ *people* table တွင် *streets* table သို့ချိတ်ထားသော Foreign Key constraint တစ်ခုရှိနေသောကြောင့်ဖြစ်သည်။ ဆိုလိုသည်မှာ *streets* table  ကို drop (သို့မဟုတ် delete) လုပ်ခြင်းသည်  *people* table တွင် *streets* data အကိုးအကားများကျန်ရှိတော့မည်မဟုတ်ပါ။

  ``CASCADE`` command အသုံးပြုပြီး *streets* table ကို အတင်းအကြပ် ဖျက်ပစ်နိုင်ပါသည်၊ သို့သော် ထိုသို့လုပ်ခြင်းသည် *people* table ကိုပါ ဖျက်ပစ်လိုက်နိုင်ပြီး *streets* table နှင့် relationship ရှိနေသော အခြား table များကိုပါ ဖျက်ပစ်လိုက်နိုင်ပါသည်။ သတိထား၍ အသုံးပြုပါ။


`people` table တွက် :kbd:`drop table` command ကိုအသုံးပြုခဲ့ပါက အဆင်ပြေမည်ဖြစ်သည်-

.. code-block:: sql

  drop table people;


.. note:: သင်သည် အဆိုပါ command ကိုရိုက်ထည့်ပြီး :kbd:`people` table ကို ဖျက်ပစ်ခဲ့ပါက ၎င်း table ကို နောက်လေ့ကျင့်ခန်းများတွင် ပြန်လည်လိုအပ်မည်ဖြစ်သည့်အတွက် ပြန်လည်တည်ဆောက်ပေးပါ။

pgAdmin III အကြောင်း (A word on pgAdmin III)
-------------------------------------------------------------------------------

`psql` prompt မှ SQL command များသည် database များအကြောင်းလေ့လာရာတွင် အလွန်အသုံးဝင်သော နည်းလမ်းတစ်ခုဖြစ်ပါသည်။ သို့သော် သင်လေ့လာခဲ့သောအရာများစွာကို လုပ်ဆောင်ရန် ပိုမိုမြန်ဆန်ပြီး လွယ်ကူသော နည်းလမ်းများရှိပါသည်။ pgAdmin III ကို install ပြုလုပ်ပါက table များဖန်တီးခြင်း၊ drop လုပ်ခြင်း၊ ပြောင်းလဲခြင်း အစရှိသည်တို့ကို GUI တစ်ခုထဲတွင် click ပြုလုပ်ပြီး လုပ်ဆောင်နိုင်မည်ဖြစ်ပါသည်။

Ubuntu တွင် အောက်ပါအတိုင်း install လုပ်နိုင်ပါသည်-

.. code-block:: bash

  sudo apt install pgadmin3

pgAdmin III အကြောင်းကို နောက်ထပ် မော်ဂျူးတွင် ပိုမိုအသေးစိတ် လေ့လာရမည်ဖြစ်သည်။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Database အသစ်စက်စက်တစ်ခုကို အစမှအဆုံး မည်သို့ဖန်တီးရမည်ကို လေ့လာခဲ့ပြီးဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် DBMS ကိုအသုံးပြုပြီး data အသစ်များ မည်သို့ထည့်သွင်းရမည်ကို လေ့လာရမည်ဖြစ်ပါသည်။
