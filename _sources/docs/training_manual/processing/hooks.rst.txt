Pre- and post-execution script hooks
====================================

.. note:: ဤသင်ခန်းစာတွင် processing မလုပ်ဆောင်မီနှင့် လုပ်ဆောင်ပြီးချိန်တွင် ထပ်ဆောင်း operation များဆောင်ရွက်နိုင်စေသော pre- နှင့် post-execution hooks များ အသုံးပြုနည်းကို လေ့လာရပါမည်။

Pre- နှင့် post-execution hooks များသည် တကယ့် data processing မလုပ်ဆောင်မီနှင့် လုပ်ဆောင်ပြီးချိန်တွင် run နိုင်သော Processing script များဖြစ်ကြပါသည်။ Algorithm တစ်ခုကိုလုပ်ဆောင်ချိန်တိုင်း ဆောင်ရွက်သင့်သော task များကို အလိုအလျောက်ဖြစ်စေရန် ၎င်းတို့ကို အသုံးပြုနိုင်ပါသည်။

Hooks များ၏ syntax သည် Processing script များ၏ syntax နှင့် တစ်ထပ်တည်းတူညီပါသည်၊ QGIS အသုံးပြုသူလမ်းညွှန်ထဲရှိ သက်ဆိုင်ရာ `အခန်း <https://docs.qgis.org/testing/en/docs/user_manual/processing/console.html>`_ တွင် အသေးစိတ်ကြည့်ရှုနိုင်ပါသည်။

Script feature များအားလုံးအပြင် hook များတွင် ``alg`` ဟုခေါ်သော အထူး variable တစ်ခုကို အသုံးပြုနိုင်ပြီး၊ ထို variable သည် လုပ်ဆောင်ပြီးသည့် (သို့မဟုတ် လုပ်ဆောင်တော့မည့်) algorithm ကို ကိုယ်စားပြုပါသည်။

အောက်တွင် Post-execution script ဥပမာတစ်ခုပြထားပါသည်။ Default အားဖြင့် Processing သည် analysis ရလာဒ်များကို ယာယီဖိုင်များထဲတွင် သိမ်းဆည်းထားပါသည်။ ဤ script သည် ရလာဒ်များကို သီးခြားဖိုင်လမ်းကြောင်းတစ်ခုထဲသို့ ကူးယူပေးမည်ဖြစ်သောကြောင့် QGIS ပိတ်လိုက်ပြီးလျှင် ရလာဒ်များ ပျက်သွားတော့မည်မဟုတ်ပါ။

::

    import os
    import shutil
    from processing.core.outputs import OutputVector, OutputRaster, OutputFile

    MY_DIRECTORY = '/home/alex/outputs'

    for output in alg.outputs:
        if isinstance(output, (OutputVector, OutputRaster, OutputFile)):
            dirname = os.path.split(output.value)[0]
            shutil.copytree(dirname, MY_DIRECTORY)


ပထမဆုံး စာကြောင်း ၂ ကြောင်းတွင် လိုအပ်သော Python package များ- ဖိုင်လမ်းကြောင်းကိုင်တွယ်ခြင်း (ဥပမာ- ဖိုင်အမည်ကို ဆွဲထုတ်ခြင်း) အတွက် ``os`` နှင့် ဖိုင်ကူးယူခြင်းကဲ့သို့ ဖိုင်စနစ်လုပ်ဆောင်မှုအမျိုးမျိုးအတွက်  ``shutil`` package ကို ထည့်သွင်းပါသည်။ တတိယစာကြောင်းတွင် Processing output များကို ထည့်သွင်းပါသည်။ ထိုအကြောင်းကို ဤသင်ခန်းစာနောက်ပိုင်းတွင် အသေးစိတ်ရှင်းပြပေးပါမည်။

ထို့နောက်တွင် ``MY_DIRECTORY`` ကိန်းသေတစ်ခုကို သတ်မှတ်ပါသည်၊ ၎င်းသည် analysis ရလာဒ်များကိုကူးယူလိုသည့် ဖိုင်လမ်းကြောင်းဖြစ်ပါသည်။

Script ၏နောက်ဆုံးတွင် အဓိက hook code ရှိပါသည်။ Loop (အဖန်ဖန်ပြန်ကျော့သောလုပ်ဆောင်မှု) ထဲတွင် algorithm ၏ output များအားလုံးကို တစ်ခုချင်းစီ iterate (ထပ်ခါတလဲလဲ) လုပ်ဆောင်ပြီး ဤ output သည် ဖိုင်အခြေခံသော output တစ်ခုဟုတ်/မဟုတ် နှင့် ကူးယူ၍ ရနိုင်/မရနိုင် ကိုစစ်ဆေးပေးပါသည်။ စစ်ဆေးမှုမှန်ကန်ပါက output ဖိုင်များတည်ရှိသော top-level ဖိုင်လမ်းကြောင်းကို ဆုံးဖြတ်ပေးပြီး ဖိုင်များအားလုံးကို ကျွန်ုပ်တို့သတ်မှတ်ထားသော ဖိုင်လမ်းကြောင်းထဲသို့ ကူးယူမည်ဖြစ်ပါသည်။

အဆိုပါ hook ကို activate လုပ်ရန် Processing option များကိုဖွင့်ပေးရန် လိုအပ်ပါသည်၊ *General* အုပ်စုထဲတွင် *Post-execution script file* ကိုရှာဖွေပြီး hook script ၏ ဖိုင်နာမည်ကို ထိုနေရာတွင် သတ်မှတ်ပါ။ Processing algorithm တစ်ခုစီ run ပြီးလျှင် သတ်မှတ်ပေးထားသော hook ကိုလုပ်ဆောင်ပေးမည်ဖြစ်သည်။

Pre-execution hook များကို အလားတူလုပ်ဆောင်နိုင်ပါသည်။ ဥပမာ- input vector များတွင် ဂျီဩမေတြီအမှားများ ရှိ/မရှိ စစ်ဆေးရန် hook တစ်ခုကိုဖန်တီးကြည့်ပါမည်။

::

    from qgis.core import QgsGeometry, QgsFeatureRequest
    from processing.core.parameters import ParameterVector

    for param in alg.parameters:
        if isinstance(param, ParameterVector):
            layer = processing.getObject(param.value)
            for f in layer.getFeatures(QgsFeatureRequest().setSubsetOfAttributes([])):
                errors = f.geometry().validateGeometry()
                if len(errors) > 0:
                    progress.setInfo('One of the input vectors contains invalid geometries!')

ယခင်ဥပမာကဲ့သို့ပင် ပထမဦးစွာ လိုအပ်သော QGIS နှင့် Processing package များကိုထည့်သွင်းပါသည်။

ထို့နောက် algorithm parameter များအားလုံးကို iterate လုပ်ဆောင်ပြီး ParameterVector parameter တစ်ခုတွေ့ပါက သက်ဆိုင်ရာ vector layer object ကိုရယူပါသည်။ Layer ၏ feature များအားလုံးကို loop လုပ်ပြီး ဂျီဩမေတြီအမှားကို စစ်ဆေးပါသည်။ Feature တစ်ခုတွင် ဆီလျော်မှုမရှိသော ဂျီဩမေတြီတစ်ခု ပါရှိပါက သတိပေးချက်စာတိုတစ်ခုကို ပြသပေးပါမည်။

ဤ hook ကို activate ပြုလုပ်ရန် Processing configuration dialog ထဲရှိ *Pre-execution script
file* option ထဲတွင် hook ၏ဖိုင်နာမည်ကို ထည့်သွင်းပေးရန်လိုအပ်ပါသည်။ Processing algorithm တစ်ခုခု မ run မီတွင် hook ကို လုပ်ဆောင်မည်ဖြစ်သည်။
