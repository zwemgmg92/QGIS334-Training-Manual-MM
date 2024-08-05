သင်ခန်းစာ - စည်းမျဉ်းများ (Lesson: Rules)
===============================================================================

Rule များသည် query တစ်ခု၏ "query tree" ကိုရေးသားပေးနိုင်ပါသည်။ အသုံးများသောတစ်ခုမှာ update ပြုလုပ်နိုင်သော view များဖန်တီးခြင်းဖြစ်သည်။ *- Wikipedia*

**ဤသင်ခန်းစာအတွက် ရည်မှန်းချက်-** Database အတွက် rule အသစ်များဖန်တီးနည်းကို လေ့လာရန်။

မှတ်တမ်း စည်းမျဉ်းတစ်ခုဖန်တီးခြင်း (Creating a logging rule)
-------------------------------------------------------------

People table ထဲရှိ phone_no ပြောင်းလဲမှုတိုင်းကို people_log table ထဲတွင် မှတ်တမ်းရေးသားလိုသည်ဆိုပါစို့။ Table အသစ်တစ်ခုကို set up ပြုလုပ်ပါမည်-

.. code-block:: sql

  create table people_log (name text, time timestamp default NOW());

နောက်တစ်ဆင့်အနေဖြင့် people table ထဲရှိ phone_no ပြောင်းလဲမှုတိုင်းကို people_log table ထဲတွင် မှတ်တမ်းရေးသားမည့် rule တစ်ခုကို ဖန်တီးပါ-

.. code-block:: sql

  create rule people_log as on update to people
    where NEW.phone_no <> OLD.phone_no
    do insert into people_log values (OLD.name);

Rule အလုပ်ဖြစ်/မဖြစ် စမ်းသပ်ရန် phone number တစ်ခုကို ပြင်ကြည့်ပါမည်-

.. code-block:: sql

  update people set phone_no = '082 555 1234' where id = 2;

:kbd:`people` table သည် မှန်မှန်ကန်ကန် update ဖြစ်/မဖြစ် စစ်ဆေးကြည့်ပါ-

.. code-block:: sql

    select * from people where id=2;

     id |    name    | house_no | street_id |   phone_no
    ----+------------+----------+-----------+--------------
      2 | Joe Bloggs |        3 |         2 | 082 555 1234
    (1 row)

ဖန်တီးလိုက်သော rule ကြောင့် :kbd:`people_log` table သည်အောက်ပါပုံစံအတိုင်း ဖြစ်နေပါလိမ့်မည်-

.. code-block:: sql

    select * from people_log;

        name    |            time
    ------------+----------------------------
     Joe Bloggs | 2014-01-11 14:15:11.953141
    (1 row)

.. note:: :kbd:`time` field ၏တန်ဖိုးသည် လက်ရှိ ရက်စွဲနှင့် အချိန်ပေါ်တွင် မူတည်ပါသည်။

နိဂုံးချုပ် (In Conclusion)
-------------------------------------------------------------------------------

Rule များသည် database ထဲတွင် data များအလိုအလျှောက်ထည့်သွင်းခြင်း သို့မဟုတ် ပြောင်းလဲခြင်းများလုပ်ဆောင်ပေးနိုင်ပြီး အဆိုပါ ပြောင်းလဲမှုများကို database ၏အခြားအပိုင်းများတွင် သက်ရောက်စေပါသည်။

နောက်ထပ်ဘာအကြောင်းအရာလဲ (What's Next?)
-------------------------------------------------------------------------------

ဤ database သဘောတရားများဖြင့် GIS data များတွင် အသုံးချမည့် PostGIS အသုံးပြုသော Spatial Database အပိုင်းကို နောက်လာမည့် မော်ဂျူးတွင် မိတ်ဆက်ပေးမည်ဖြစ်ပါသည်။
