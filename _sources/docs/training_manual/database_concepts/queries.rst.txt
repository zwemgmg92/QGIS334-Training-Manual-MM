သင်ခန်းစာ - Query များ (Lesson: Queries)
===============================================================================

:kbd:`SELECT ...` command တစ်ခုကိုရေးသားသောအခါ ၎င်းကို query ဟု လူသိများပါသည် - အချက်အလက်များအတွက် database ကို စိစစ်မေးမြန်းခြင်း ဖြစ်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** အသုံးဝင်သော အချက်အလက်များကို ပြန်ထုတ်ပေးမည့် query များဖန်တီးနည်းကို လေ့လာရန်။

.. note:: ယခင်သင်ခန်းစာတွင် မလုပ်ခဲ့ရပါက အောက်ပါ people object များကို :kbd:`people` table ထဲသို့ ထည့်သွင်းပါ။ Foreign key constraint များနှင့်ပတ်သက်သော error တစ်ခုခု ရရှိပါက streets table ထဲသို့ 'Main Road' object ကို ဦးစွာ ထည့်သွင်းပေးရန် လိုအပ်ပါလိမ့်မည်။

.. code-block:: sql

    insert into people (name,house_no, street_id, phone_no)
              values ('Joe Bloggs',3,2,'072 887 23 45');
    insert into people (name,house_no, street_id, phone_no)
              values ('Jane Smith',55,3,'072 837 33 35');
    insert into people (name,house_no, street_id, phone_no)
              values ('Roger Jones',33,1,'072 832 31 38');
    insert into people (name,house_no, street_id, phone_no)
              values ('Sally Norman',83,1,'072 932 31 32');


ရလာဒ်များကို စီ ခြင်း (Ordering Results)
-------------------------------------------------------------------------------

အိမ်နံပါတ်များဖြင့် စီ ထားသော People စာရင်းတစ်ခုကို ဆွဲထုတ်ကြည့်ကြပါစို့- 

.. code-block:: sql

  select name, house_no from people order by house_no;

ရလာဒ်-

.. code-block:: sql

         name     | house_no
    --------------+----------
     Joe Bloggs   |        3
     Roger Jones  |       33
     Jane Smith   |       55
     Sally Norman |       83
    (4 rows)

ရလာဒ်များကို column တစ်ခုထက်မကသော တန်ဖိုးများဖြင့် sort လုပ်နိုင်ပါသည်-

.. code-block:: sql

	select name, house_no from people order by name, house_no;

ရလာဒ်-

.. code-block:: sql

         name     | house_no
    --------------+----------
     Jane Smith   |       55
     Joe Bloggs   |        3
     Roger Jones  |       33
     Sally Norman |       83
    (4 rows)


စစ်ထုတ်ခြင်း (Filtering)
-------------------------------------------------------------------------------

Database ထဲရှိ record တစ်ခုစီတိုင်းကို မြင်တွေ့လိုခြင်းမရှိပဲ ထောင်ပေါင်းများစွာသော record များထဲမှ တစ်ခု သို့မဟုတ် နှစ်ခုကိုသာ မြင်တွေ့လိုပါသည်။

``house_no`` 50 ထက်နည်းသော object များကိုသာ ပြန်ထုတ်ပေးသော ကိန်းဂဏန်း filter တစ်ခု၏ ဥပမာကို အောက်တွင်ပြထားပါသည်-

.. code-block:: sql

  select name, house_no from people where house_no < 50;

        name     | house_no
    -------------+----------
     Joe Bloggs  |        3
     Roger Jones |       33
    (2 rows)

Filter များ (``WHERE`` clause ဖြင့်သတ်မှတ်ထားသော) ကို sorting (``ORDER BY`` clause ဖြင့်သတ်မှတ်ထားသော) ဖြင့် ပေါင်းစပ်နိုင်ပါသည်-

.. code-block:: sql

  select name, house_no from people where house_no < 50 order by house_no;

        name     | house_no
    -------------+----------
     Joe Bloggs  |        3
     Roger Jones |       33
    (2 rows)

စာသား data အပေါ်မူတည်၍လည်း filter လုပ်နိုင်ပါသည်-

.. code-block:: sql

  select name, house_no from people where name like '%s%';

        name     | house_no
    -------------+----------
     Joe Bloggs  |        3
     Roger Jones |       33
    (2 rows)

နာမည်တွင် :kbd:`s` ပါသော နာမည်အားလုံးကိုရှာဖွေရန်  :kbd:`LIKE` clause ကိုအသုံးပြုပါသည်။ ထို query သည် case-sensitive ဖြစ်သည်ကို သတိပြုမိပါလိမ့်မည်၊ ထို့ကြောင့် :kbd:`Sally Norman` entry ကို ပြန်ထုတ်ပေးခြင်းမရှိပါ။

စာသားများ string တစ်ခုကို စာလုံးအကြီးအသေးကို မစဉ်းစားပဲ ရှာဖွေလိုပါက :kbd:`ILIKE` clause ကိုအသုံးပြုပြီး case in-sensitive ရှာဖွေမှုတစ်ခုကို ပြုလုပ်နိုင်ပါသည်-

.. code-block:: sql

  select name, house_no from people where name ilike '%r%';

         name     | house_no
    --------------+----------
     Roger Jones  |       33
     Sally Norman |       83
    (2 rows)

ထို query သည် နာမည်တွင် :kbd:`r` သို့မဟုတ် :kbd:`R` ပါဝင်သော **people** object တိုင်းကို ထုတ်ပေးမည်ဖြစ်ပါသည်။

ချိတ်ဆက်မှုများ (Joins)
-------------------------------------------------------------------------------

Person ၏ အသေးစိတ်အချက်အလက်များနှင့် ID အစား ၎င်းတို့၏ street နာမည်ကို မြင်တွေ့လိုပါက မည်သို့လုပ်မည်နည်း? ထိုသို့လုပ်ဆောင်ရန် query တစ်ခုထဲတွင် table နှစ်ခုကို join လုပ်ပေးရန် လိုအပ်ပါသည်။ ဥပမာ-

.. code-block:: sql

  select people.name, house_no, streets.name
  from people,streets
  where people.street_id=streets.id;

.. note:: Join ပြုလုပ်လျှင် အချက်အလက်များပါရှိသော table နှစ်ခုကို အမြဲတမ်း ဖော်ပြပေးရပါမည်၊ ဤဥပမာတွင် people နှင့် streets တို့ဖြစ်ပါသည်။ ကိုက်ညီမှုရှိရမည့် key နှစ်ခု (foreign key နှင့် primary key) ကိုလည်း သတ်မှတ်ပေးရန်လိုအပ်ပါသည်။ ၎င်းကို သတ်မှတ်မပေးထားပါက ဖြစ်နိုင်ချေရှိသော people နှင့် streets ပေါင်းစပ်မှုများအားလုံးကို ရရှိပါလိမ့်မည်၊ ထို့အတွက်ကြောင့် မည်သည့် street တွင် မည်သူက အမှန်တကယ်နေထိုင်သည်ကို သိရှိနိုင်တော့မည်မဟုတ်ပါ။

ရလာဒ် အမှန်သည် အောက်ပါပုံစံအတိုင်း ဖြစ်ပါလိမ့်မည်-

.. code-block:: sql

         name     | house_no |    name
    --------------+----------+-------------
     Joe Bloggs   |        3 | Low Street
     Roger Jones  |       33 | High street
     Sally Norman |       83 | High street
     Jane Smith   |       55 | Main Road
    (4 rows)

နောက်ပိုင်း ပိုမိုရှုပ်ထွေးသော query များကို ဖန်တီးသည့်အချိန်တွင် join ထပ်လုပ်ပါမည်။ နှစ်ခု သို့မဟုတ် နှစ်ခုထက်ပိုသော table များမှ အချက်အလက်များကို ပေါင်းစည်းရန် ရိုးရှင်းသော နည်းလမ်းတစ်ခုဖြစ်ပါသည်။

Sub-Select
-------------------------------------------------------------------------------

Foreign key relationship တစ်ခုဖြင့် ချိတ်ဆက်ထားသော အခြား table မှ data များပေါ်မူတည်ပြီး table တစ်ခုမှ object များကို select လုပ်ရန် Sub-selection ကိုအသုံးပြုနိုင်ပါသည်။ ဤဥပမာတွင် သီးသန့် street တစ်ခုတွင် နေထိုင်သော people များကို ရှာဖွေလိုပါသည်။

ဦးစွာပထမ data ကို အနည်းငယ်ညှိကြည့်ပါမည်-

.. code-block:: sql

  insert into streets (name) values('QGIS Road');
  insert into streets (name) values('OGR Corner');
  insert into streets (name) values('Goodle Square');
  update people set street_id = 2 where id=2;
  update people set street_id = 3 where id=3;

အဆိုပါပြောင်းလဲမှုများပြုလုပ်ပြီးနောက် data ကို ကြည့်ကြပါစို့- ယခင်သင်ခန်းစာမှ query ကို ပြန်လည်အသုံးပြုနိုင်ပါသည်-

.. code-block:: sql

  select people.name, house_no, streets.name
  from people,streets
  where people.street_id=streets.id;

ရလာဒ်-

.. code-block:: sql

         name     | house_no |    name
    --------------+----------+-------------
     Roger Jones  |       33 | High street
     Sally Norman |       83 | High street
     Jane Smith   |       55 | Main Road
     Joe Bloggs   |        3 | Low Street
    (4 rows)

ယခုအခါ ထို data တွင် sub-selection တစ်ခုလုပ်ကြည့်ပါမည်။ ``street_id`` :kbd:`1` တွင် နေထိုင်သော people များကိုသာ ပြသလိုပါသည်-

.. code-block:: sql

  select people.name
  from people, (
      select *
      from streets
      where id=1
    ) as streets_subset
  where people.street_id = streets_subset.id;

ရလာဒ်-

.. code-block:: sql

         name
    --------------
     Roger Jones
     Sally Norman
    (2 rows)

ဤဥပမာသည် အလွန်ရိုးရှင်းပြီး data-sets အသေးများတွင် မလိုအပ်သော်လည်း ကြီးမားပြီး ရှုပ်ထွေးသော data-sets များကို query လုပ်ဆောင်သောအခါ sub-selection ၏ အသုံးဝင်မှုနှင့် အရေးပါမှုကို ပြသပေးပါသည်။

Query များကို စုပေါင်းခြင်း (Aggregate Queries)
-------------------------------------------------------------------------------

Database တစ်ခု၏ အစွမ်းထက်သော feature များထဲမှတစ်ခုသည် table များထဲရှိ data များကို summarise (အနှစ်ချုပ်) ပြုလုပ်နိုင်ခြင်းဖြစ်သည်။ ထို summary များကို aggregate query များဟု ခေါ်ဆိုပါသည်။ အောက်ပါဥပမာသည် people table ထဲတွင် people object မည်မျှရှိသည်ကို ပြောပြပေးပါသည်- 

.. code-block:: sql

  select count(*) from people;

ရလာဒ်-

.. code-block:: sql

   count
  -------
       4
  (1 row)

Street name ဖြင့် အနှစ်ချုပ်ထားသော အရေအတွက်ကို လိုချင်ပါက အောက်ပါအတိုင်းပြုလုပ်နိုင်ပါသည်-

.. code-block:: sql

  select count(name), street_id
  from people
  group by street_id;

ရလာဒ်-

.. code-block:: sql

     count | street_id
    -------+-----------
         2 |         1
         1 |         3
         1 |         2
    (3 rows)

.. note:: :kbd:`ORDER BY` clause ကိုအသုံးမပြုထားသောကြောင့် သင့်ရလာဒ်များ၏ order သည် ဤဥပမာတွင် ပြထားသည်နှင့် ကိုက်ညီချင်မှ ကိုက်ညီပါလိမ့်မည်။

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:) :abbr:`★★☆ (Moderate level)`
...............................................................................

Street name ဖြင့် people များကို summarise ပြုလုပ်ပြီး street_ids အစား street name အမှန်များကိုပြသပေးပါ။

.. admonition:: အဖြေ
  :class: dropdown

  မှန်ကန်သော SQL statement မှာ::

    select count(people.name), streets.name
    from people, streets
    where people.street_id=streets.id
    group by streets.name;

  ရလာဒ်::

       count |    name
       ------+-------------
           1 | Low Street
           2 | High street
           1 | Main Road
       (3 rows)

  Field name များကို table name များဖြင့် prefix (ရှေ့ဆက်) ထည့်သွင်းထားသည်ကို သတိပြုမိပါလိမ့်မည် (ဥပမာ- people.name နှင့် streets.name)။ Field name သည် ဒွိဟဖြစ်နေသည့် အချိန်တိုင်းတွင် ၎င်းကို ပြုလုပ်ရန်လိုအပ်ပါသည် (ဥပမာ- database ထဲရှိ table များအားလုံးအကြား unique ဖြစ်မနေလျှင်) 


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Database ထဲမှ အသုံးဝင်သော အချက်အလက်များကို ဆွဲထုတ်ရန် query များအသုံးပြုနည်းကို မြင်တွေ့ခဲ့ရပြီးဖြစ်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

နောက်လာမည့်သင်ခန်းစာတွင် သင်ရေးသားထားသော query များမှ view များကို မည်သို့ဖန်တီးရမည်ကို လေ့လာရမည်ဖြစ်သည်။
