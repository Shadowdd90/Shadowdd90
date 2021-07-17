import amino
import requests
import time
import sys
import sys as n
import time as mm
def slow(M):
    for c in M + '\n':
        n.stdout.write(c)
        n.stdout.flush()
        mm.sleep(1. / 200)
slow("""

╔════╦═══╦═══╦═══╗
╚══╗═║╔══╣╔═╗║╔═╗║
──╔╝╔╣╚══╣╚═╝║║─║║
─╔╝╔╝║╔══╣╔╗╔╣║─║║
╔╝═╚═╣╚══╣║║╚╣╚═╝║
╚════╩═══╩╝╚═╩═══╝



""")
client=amino.Client()
listuid=[]
listname=[]
client.login(email="o6ti1p@esiix.com",password="@112233@")
print('Logged in')
client.join_community(comId="162126963")
subclient=amino.SubClient(comId="162126963",profile=client.profile)
nm=subclient.profile.nickname
print(f"Inside Community as {nm}\n")
x=subclient.get_all_users(type="recent",start=0,size=200)
for i,name in zip(x.profile.userId,x.profile.nickname):
    listuid.append(i)
    listname.append(name)

message="""[C]
[C]  ⏜૪⏜
[C] ::♡
[C]❥ . .𝐰𝐞𝐥𝐜𝐨𝐦𝐞 𝒕
[C]↻┊⠀ ོ☁️
[C] — اضَغَط الثَلَاث نقَاط -— ꒰🐇꒱ —
[C]`.~.✿ ᏔᎬᏞᏟϴᎷᎬ .~.
[C]♡‧₊˚◍ꪳꦽ   .
[C]‏✧∘* ೃ ⋆｡˚.☁︎·̩͙
[C]كِن حِلماً للٓـجٰمٰٓـيـع ولأ تـحٰلـم باأحِـد
[C]𝑊𝑒𝑟𝑒 𝑚𝑦 𝑤𝑜𝑟𝑑𝑠 𝑒𝑛𝑜𝑢𝑔ℎ 𝑓𝑜𝑟 𝑦𝑜𝑢 𝑟𝑒𝑎𝑙𝑙𝑦
[C]*⢁✧ ‿︵‿︵‿︵ ✧⡠*✩
[C]｡˚  ✩
[C]المنتدى يضم جميع الناس بتعدد ميولاتهم،
[C]ويمكنك ان تقوم بـ اشياء كثيرة مثل إكتساب،
[C]صداقات جديدة حسب نوع ميول ترغب به،
[C]أو القيام بنشر  المدونات التي تخص المنتدى.

[CU]⁺        .    °       ⑅        ⊹

[C]سَــوف تجّـد كـل ما هو مُــتنوع  
[C]إذا إحتجـــت أي شـيـىء أو لديك اي إستفستار
[C]تفقد هـذه الـروابـط✓
[CU]⁺        .    °       ⑅        ⊹
[C]"مـركـز الـدردشـه الـعـام"
[C] http://aminoapps.com/p/ohmnaj
[C]⏝͝⏝𖠄⏝͝⏝
[C]'مـركـز الـبـلاغـات والـمـسـاعـدة"
[C] http://aminoapps.com/p/1owi5x3
[C]⏝͝⏝𖠄⏝͝⏝
[C]"الـقـاب الـمـنـتـدى"
[C] http://aminoapps.com/p/gmb6vg
[C]⏝͝⏝𖠄⏝͝⏝
[C]"قوانــين الـمـنـتـدى"
[C] http://aminoapps.com/p/hzbovv
[C]⏝͝⏝𖠄⏝͝⏝
[C]"وكـيـل  المنتـــدى"
[C]  http://aminoapps.com/p/514gjg
[C]⏝͝⏝𖠄⏝͝⏝
[C]
[C][C]⌦ : :  ︿︿ ✿
[C]𝐓𝐡𝐞 𝐄𝐧𝐝
[C]حظاً مـوفقاً لك فـي المـُنتـدى !.
[C]
[C]                      ╭┈─────── ೄྀ࿐ ˊˎ-
[C] ╰┈─➤ sρεcιαℓ"""

for s,n in zip(listuid,listname):
    try:
        p=subclient.get_wall_comments(userId=s,sorting="newest",start=0,size=25)
        m=p.content
        if message not in m:
            subclient.comment(message=message,userId=s)
            print(f"welcomed {n} in the community")
    except:
        pass
print("All done")
