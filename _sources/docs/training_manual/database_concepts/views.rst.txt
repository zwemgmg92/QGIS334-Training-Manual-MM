သင်ခန်းစာ - View များ (Lesson: Views)
===============================================================================

Query တစ်ခုရေးသားသောအခါ အချိန်နှင့်အားစိုက်မှုများစွာ လိုအပ်ပါသည်။ View များအသုံးပြု၍ SQL query တစ်ခု၏ အဓိပ္ပါယ်သတ်မှတ်ချက်ကို ပြန်လည်အသုံးပြုနိုင်သော 'virtual table' ထဲတွင် သိမ်းဆည်းထားနိုင်ပါသည်။

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Query တစ်ခုကို View တစ်ခုအနေဖြင့် သိမ်းဆည်းရန်။

View တစ်ခုဖန်တီးခြင်း (Creating a View)
-------------------------------------------------------------------------------

View တစ်ခုကို table တစ်ခုကဲ့သို့ လုပ်ဆောင်နိုင်ပါသည်၊ သို့သော် ၎င်း၏ data ရင်းမြစ်သည် query တစ်ခုမှလာပါသည်။ ယခင်သင်ခန်းစာရှိ query ကိုအခြေခံပြီး ရိုးရှင်းသော view တစ်ခုဖန်တီးကြည့်ပါမည်-

.. code-block:: sql

  create view roads_count_v as
    select count(people.name), streets.name
    from people, streets where people.street_id=streets.id
    group by people.street_id, streets.name;

မြင်တွေ့ရသည့်အတိုင်း အစပိုင်းတွင်ရေးသားထားသော :kbd:`create view roads_count_v as` အပိုင်းသာလျှင် ပြောင်းလဲသွားပါသည်။ အဆိုပါ view မှ data များကို select လုပ်နိုင်ပြီဖြစ်ပါသည်-

.. code-block:: sql

  select * from roads_count_v;

ရလာဒ်-

.. code-block:: sql

     count |    name
    -------+-------------
         1 | Main Road
         2 | High street
         1 | Low Street
    (3 rows)

View တစ်ခုကို မွမ်းမံပြင်ဆင်ခြင်း (Modifying a View)
-------------------------------------------------------------------------------

View ကို ပုံသေသတ်မှတ်မထားပါ၊ ၎င်းတွင် 'data အစစ်' များမပါဝင်ပါ။ ဆိုလိုသည်မှာ database ထဲရှိ data များကိုထိခိုက်မှုမရှိစေပဲ view ကို အလွယ်တကူပြောင်းလဲမှုပြုလုပ်နိုင်ပါသည်-

.. code-block:: sql

  CREATE OR REPLACE VIEW roads_count_v AS
    SELECT count(people.name), streets.name
    FROM people, streets WHERE people.street_id=streets.id
    GROUP BY people.street_id, streets.name
    ORDER BY streets.name;

(ဤဥပမာတွင် SQl keyword များအားလုံးအတွက် UPPER CASE အသုံးပြုခြင်းကို ပြသထားပါသည်)

View row များကို ကောင်းမွန်စွာ sort ပြုလုပ်စေရန် :kbd:`ORDER BY` clause ကိုထည့်သွင်းထားသည်ကို မြင်တွေ့ရပါမည်-

.. code-block:: sql

    select * from roads_count_v;

     count |    name
    -------+-------------
         2 | High street
         1 | Low Street
         1 | Main Road
    (3 rows)

View တစ်ခုကို ဖယ်ရှားခြင်း (Dropping a View)
-------------------------------------------------------------------------------

View တစ်ခုကို မလိုအပ်တော့ပါက အောက်ပါအတိုင်း ဖျက်ပစ်နိုင်ပါသည်-

.. code-block:: sql

  drop view roads_count_v;

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

View များကိုအသုံးပြုပြီး query တစ်ခုကို သိမ်းဆည်းနိုင်သလို ရလာဒ်များကို table တစ်ခုကဲ့သို့ ရယူသုံးစွဲနိုင်ပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

တစ်ခါတရံတွင် data များကို ပြောင်းလဲသောအခါ database ထဲတွင်ပါ ပြောင်းလဲလိုသည်များရှိပါသည်။ နောက်လာမည့်သင်ခန်းစာတွင် ၎င်းကို မည်သို့လုပ်ဆောင်ရမည်ကို လေ့လာရမည်ဖြစ်ပါသည်။
