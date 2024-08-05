သင်ခန်းစာ - Model ထဲသို့ Data ထည့်သွင်းခြင်း (Lesson: Adding Data to the Model)
================================================================================

The models we've created will now need to be populated with the data they're
intended to contain.

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Database model များထဲသို့ data အသစ်ထည့်သွင်းနည်းကို လေ့လာရန်။

Insert statement
-------------------------------------------------------------------------------

Table တစ်ခုထဲသို့ data မည်သို့ထည့်သွင်းပါသလဲ? sql :kbd:`INSERT` statement ကိုအသုံးပြုနိုင်ပါသည်-

.. code-block:: sql

  insert into streets (name) values ('High street');

မှတ်သားရမည်များမှာ-

* Table name (:kbd:`streets`) နောက်တွင် column နာမည်များကို list လုပ်ပါသည် (ဤဥပမာတွင် :kbd:`name` column တစ်ခုတည်းသာ)။
* :kbd:`values` keyword နောက်တွင် field တန်ဖိုးများကို ထည့်ပါ။
* String (စာသား) များကို single quote (' ') အသုံးပြု၍ ရေးပါ။ 
* :kbd:`id` column အတွက် တန်ဖိုးမထည့်သွင်းသည်ကို သတိပြုကြည့်ပါ၊ အဘယ်ကြောင့်ဆိုသော :kbd:`id` column သည် sequence တစ်ခုဖြစ်ပြီး အလိုအလျောက်ထုတ်ပေးခြင်းဖြစ်သည်။
* :kbd:`id` ကို ကိုယ်တိုင်သတ်မှတ်ပါက database ခိုင်မာမှုနှင့်ပတ်သက်ပြီး ပြဿနာကြီးကြီးမားမားဖြစ်စေနိုင်ပါသည်။

လုပ်ဆောင်မှုအောင်မြင်ပါက :kbd:`INSERT 0 1` ကိုမြင်တွေ့ရပါမည်။

Table ထဲရှိ data များအားလုံးကို select လုပ်ခြင်းဖြင့် insert လုပ်ဆောင်ချက်၏ရလာဒ်ကို ကြည့်နိုင်ပါသည်-

.. code-block:: sql

  select * from streets;

ရလာဒ်မှာ-

.. code-block:: sql

  select * from streets;
   id |    name
  ----+-------------
    1 | High street
  (1 row)


မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:) :abbr:`★☆☆ (Basic level)`
...............................................................................

:kbd:`streets` table တွင် street အသစ်တစ်ခု ထည့်သွင်းရန် :kbd:`INSERT` command ကိုအသုံးပြုပါ။

.. admonition:: အဖြေ
  :class: dropdown

  အသုံးပြုရမည့် SQL command သည် အောက်ပါအတိုင်းဖြစ်ပါသည် (street name နေရာတွင် သင့်စိတ်ကြိုက်နာမည်ဖြင့် အစားထိုးပါ)::

    insert into streets (name) values ('Low Road');


Constraint များအရ Data များအစီအစဉ်တကျပေါင်းထည့်ခြင်း (Sequencing Data Addition According to Constraints)
---------------------------------------------------------------------------------------------------------

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ - (Try Yourself:) :abbr:`★★☆ (Moderate level)`
-------------------------------------------------------------------------------

အောက်ပါအသေးစိတ်အချက်အလက်များဖြင့် :kbd:`people` table ထဲတွင် person object တစ်ခုပေါင်းထည့်ပါ::

  Name: Joe Smith
  House Number: 55
  Street: Main Street
  Phone: 072 882 33 21

.. note:: ဤဥပမာတွင် phone number ကို integer မဟုတ်ပဲ string အနေဖြင့် သတ်မှတ်ခဲ့ပါသည်။

:kbd:`streets` table ထဲတွင် Main Street အတွက် record တစ်ခု ဦးစွာမဖန်တီးပဲ လုပ်ဆောင်ပါက error report တစ်ခုရရှိပါလိမ့်မည်။

အောက်ပါတို့ကိုလည်း သတိပြုမိသင့်ပါသည်-

* Street ၏အမည်ကိုအသုံးပြုပြီး street ကိုထည့်သွင်း၍မရနိုင်ပါ
* Street table တွင် street record ကို ဦးစွာ မဖန်တီးပဲ street :kbd:`id` အသုံးပြုပြီး street ကိုထည့်သွင်း၍မရနိုင်ပါ

Table ၂ ခုသည် Primary/Foreign Key pair ဖြင့် ချိတ်ဆက်ထားပါသည်။ ဆိုလိုသည်မှာ သက်ဆိုင်ရာဆီလျော်သော street record မရှိပဲ person တစ်ဦးကို ဖန်တီး၍မရနိုင်ပါ။

အထက်ဖော်ပြပါ အချက်များကို အသုံးပြု၍ database ထဲတွင် person အသစ်ထည့်သွင်းပါ။

.. admonition:: အဖြေ
  :class: dropdown

  မှန်ကန်သော SQL statement မှာ::
  
    insert into streets (name) values('Main Road');
    insert into people (name,house_no, street_id, phone_no)
      values ('Joe Smith',55,2,'072 882 33 21');
  
  Street table ကို ထပ်ကြည့်ပါက (select statement ကိုအသုံးပြု၍) ``Main Road`` entry အတွက် :guilabel:`id` သည် *2* ဖြစ်နေသည်ကို မြင်တွေ့ရပါလိမ့်မည်။
  
  ထို့အတွက်ကြောင့် ``2`` အထက် ဂဏန်းကိုသာ ရိုက်ထည့်ပေးနိုင်ခြင်းဖြစ်သည်။ Entry ထဲတွင် ``Main Road`` ဟူသော အပြည့်အစုံရေးသားထားသည်ကို မတွေ့ရသော်လည်း database သည် ၎င်းကို :guilabel:`street_id` တန်ဖိုး *2* ဖြင့် ဆက်စပ်ပေးမည်ဖြစ်သည်။
  
  Street object အသစ်တစ်ခုထည့်သွင်းပြီးပါက ``Main Road`` အသစ်တွင် :guilabel:`id` *2* မဟုတ်ပဲ *3* ဖြစ်နေသည်ကို တွေ့ရပါမည်။


Data များရွေးချယ်ခြင်း (Select data)
-------------------------------------------------------------------------------

Record များကို ရွေးချယ်ခြင်းအတွက် syntax ကို ပြသခဲ့ပြီးဖြစ်ပါသည်။ နောက်ထပ်ဥပမာများကို ထပ်ကြည့်ကြပါစို့-

.. code-block:: sql

  select name from streets;


.. code-block:: sql

  select * from streets;

.. code-block:: sql

  select * from streets where name='Main Road';

နောက်လာမည့်အပိုင်းများတွင် data များ select လုပ်ခြင်းနှင့် filter လုပ်ခြင်းဆိုင်ရာ အသေးစိတ်များကို လေ့လာရမည်ဖြစ်သည်။

Data များ Update လုပ်ခြင်း (Update data)
-------------------------------------------------------------------------------

ရှိနေပြီးသား data အချို့ကို ပြောင်းလဲမှုများပြုလုပ်လိုပါက မည်သို့လုပ်ဆောင်မလဲ? ဥပမာအားဖြင့် street name ပြောင်းလဲခြင်း-

.. code-block:: sql

  update streets set name='New Main Road' where name='Main Road';

ထိုကဲ့သို့သော update statement များကို အသုံးပြုရာတွင် များစွာသတိထားပါ၊ သင်ရေးသားသော :kbd:`WHERE` clause တွင် record တစ်ခုထက်ပို၍ ကိုက်ညီနေပါက ကိုက်ညီသည်များအားလုံးကို update လုပ်သွားမည်ဖြစ်သည်။

ပြောင်းလဲမည့် record ကို ရည်ညွှန်းရန် table ၏ primary key ကိုအသုံးပြုခြင်းသည် ပိုကောင်းသော ဖြေရှင်းနည်းဖြစ်ပါသည်-

.. code-block:: sql

  update streets set name='New Main Road' where id=2;

:kbd:`UPDATE 1` ပြန်ထုတ်ပေးသင့်ပါသည်။

.. note:: :kbd:`WHERE` statement criteria သည် case sensitive (စာလုံးအကြီးအသေး သတိပြု) ဖြစ်ပါသည်၊ :kbd:`Main Road` သည် :kbd:`Main road` နှင့်မတူညီပါ။

Data များဖျက်ခြင်း (Delete Data)
-------------------------------------------------------------------------------

Table တစ်ခုမှ object တစ်ခုကိုဖျက်ရန် :kbd:`DELETE` command ကိုအသုံးပြုပါ-

.. code-block:: sql

  delete from people where name = 'Joe Smith';

People table ကိုကြည့်ကြပါစို့-

.. code-block:: sql

  address=# select * from people;

    id | name | house_no | street_id | phone_no
   ----+------+----------+-----------+----------
  (0 rows)

မိမိကိုယ်တိုင်ကြိုးစားကြည့်ပါ (Try Yourself:) :abbr:`★★★ (Advanced level)`
-------------------------------------------------------------------------------

Database ထဲသို့ friend အသစ်များကို ထည့်သွင်းရန် လေ့လာခဲ့ပြီးသော နည်းများကိုအသုံးပြုပါ-

.. code-block:: sql

         name       | house_no | street_id |   phone_no
   -----------------+----------+-----------+--------------
   Joe Bloggs       |        3 |         2 | 072 887 23 45
   Jane Smith       |       55 |         3 | 072 837 33 35
   Roger Jones      |       33 |         1 | 072 832 31 38
   Sally Norman     |       83 |         1 | 072 932 31 32


နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

ယခင်ကဖန်တီးခဲ့သော ရှိနေပြီးသား model များထဲသို့ data အသစ်များ မည်သို့ထည့်သွင်းရမည်ကို သိရှိပြီးဖြစ်ပါသည်။ Data အသစ်များထည့်သွင်းလိုပါက data ကိုထည့်သွင်းမည့် model ကို မွမ်းမံပြင်ဆင်နိုင်ပါသည် သို့မဟုတ် model အသစ်များဖန်တီးနိုင်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ယခုအခါ data အချို့ကို ထည့်သွင်းပြီးဖြစ်ပါသည်၊ ထို data များကို နည်းအမျိုးမျိုးဖြင့် ရယူသုံးစွဲရန် query များအသုံးပြုနည်းကို နောက်လာမည့်သင်ခန်းစာတွင်လေ့လာရမည်ဖြစ်သည်။
