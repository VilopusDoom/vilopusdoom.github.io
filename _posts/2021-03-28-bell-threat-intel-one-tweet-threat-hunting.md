---
title: Bell Threat Intel One Tweet
subtitle: ISSessions CTF 2021
author: Pocholo Arangote
permalink: /blog/issctf21/bell-ti-one-tweet
---

#### Problem:
Instructions:
```
We received a new intelligence from our partners at the NSO. They have successfully intercepted a message that contains details on another big scale attacks on Canadian institutions. We believe the parties involved in this conversation are the command center and the operators. Our partners at NSO are expecting us to assist them with finding the main organizations behind this attack, where it can be a low level criminals, financial crime groups or even governmental agencies. We have to find their address of the headquarters and perform necessary action to stop them from launching the attacks. Use Open Source Intelligence (OSINT) methodology to find the information.

Important Notes:
Based on previous investigation, we saw operators were using Facebook, Twitter, LinkedIn, and even reddit to spread messages and instructions. You might need social media account on each platforms to get the full information while performing OSINT. 

Task:
Find the address of the main organization headquarters. 

Flag:
- The flag is JUST the street name of the main organization headquarters
- The street name characters should all be in lowercase and remove space if there's any space
- Hash the street name using sha256sum tool in Linux. 
Take the first 10 characters of the Hash and insert it between the flag container (FLAG{----------})
- Watch out for any invisible characters (space, new line or tab) since it might change the hash value
```

#### Solution:

There's a folder with the intelligence inside. Inside, there are 17 .png files, all of which appear to be a distraction. There is one 'do-not-open.txt' file.

do-not-open.txt:
```
Блок 26165 операторов:

Дескриптор нашего нового офицера в Твиттере прилагается. Заказы на канадское наступление из Москвы будут переведены с этого счета.
использовать домен.tld/имя пользователя для доступа к счету, он не индексируется на поисковых системах

PS: используйте язык моря.

Прощай,
Опорная плита
```

It's in Russian. I don't know Russian, so off to the translator: Google Translate.

Translated:
```
Block 26165 operators:

Our new officer's Twitter handle is attached. Orders for the Canadian offensive from Moscow will be transferred from this account.
use domain.tld / username to access the account, it is not indexed on search engines

PS: use the language of the sea.

Goodbye,
Base plate
```

A lot of things going on here. Note, you cannot take the translations literally, as it *is* Google Translate, and prone to errors. Thus we identify key-words.

keywords.txt:
```
Block
26165
operators
Canada
Moscow
domain.tld
Twitter
```

We use any combination that makes sense from what we think are important keywords.
In this instant, 26165 operators seems relevant, and we have a social media site: Twitter. Thus we search 26165 operator on Twitter. We get a series of Tweets from Dr. Richard Scholtz(@RVS3USA). More keywords can be gleaned. A Unit 26165 is mentioned, as well as DNC, GRU, and some info-sec tools. GRU is mentioned as *GRU OFFICERS* exfiltrating data from victims' computers. So we can probably conclude the following: Block=Unit, which makes sense, as they are similar. Operators = Officers. So, these tweets seem to be related to our intelligence. Unit 26165 Officers are attacking a government infrastructure. They belong to the GRU, a Russian Foreign Military Intelligence Agency. According to Wikipedia, the GRU is headquartered in Grizodubovoy str. 3, Moscow.

Therefore our FLAG is the first 10 characters of the sha256sum of "Grizodubovoy". Our FLAG thus is: FLAG{a1bc6d9df2}
