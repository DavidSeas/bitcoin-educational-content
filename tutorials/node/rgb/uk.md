---
name: RGB
description: Вступ та створення активів на RGB
---

![RGB vs Ethereum](assets/0.webp)

## Вступ

3 січня 2009 року Сатоші Накамото запустив перший вузол Bitcoin, з того моменту нові вузли приєднувалися, і Bitcoin почав поводити себе, ніби це була нова форма життя, форма життя, яка не переставала еволюціонувати, поступово він став найбезпечнішою мережею у світі завдяки своєму унікальному дизайну, дуже добре продуманому Сатоші, оскільки через економічні стимули він приваблює користувачів, яких зазвичай називають майнерами, інвестувати в енергію та обчислювальну потужність, що сприяє безпеці мережі.

Оскільки Bitcoin продовжує свій ріст і прийняття, він стикається з проблемами масштабування, мережа Bitcoin дозволяє добувати новий блок з транзакціями приблизно за 10 хвилин, припускаючи, що ми маємо 144 блоки на день з максимальними значеннями ​​2700 транзакцій на блок, Bitcoin дозволив би лише 4.5 транзакції в секунду, Сатоші був свідомий цього обмеження, ми можемо побачити це в електронному листі1, відправленому Майку Герну в березні 2011 року, де він пояснює, як працює те, що ми сьогодні знаємо як платіжний канал. мікроплатежі швидко і безпечно без очікування підтверджень. Ось де вступають в гру протоколи поза ланцюгом.

За словами Крістіана Декера2, протоколи поза ланцюгом зазвичай є системами, в яких користувачі використовують дані з блокчейна і керують ними, не торкаючись самого блокчейна до останньої хвилини. На основі цього концепту народилася Lightning Network, мережа, яка використовує протоколи поза ланцюгом, щоб дозволити миттєві платежі Bitcoin, і оскільки не всі ці операції записуються на блокчейн, це дозволяє тисячам транзакцій на секунду і масштабує Bitcoin.

Дослідження та розробка в області протоколів поза ланцюгом на Bitcoin відкрили скриньку Пандори, сьогодні ми знаємо, що можемо досягти набагато більшого, ніж передача цінностей децентралізованим способом, некомерційна асоціація стандартів LNP/BP зосереджується на розробці протоколів рівня 2 і 3 на Bitcoin і Lightning Network, серед цих проектів виділяється RGB.

## Що таке RGB?

RGB з'явився з досліджень Пітера Тодда3 на тему одноразових печаток та валідації на стороні клієнта, які були введені в дію в 2016-2019 роках Джакомо Зукко та спільнотою в якості кращого протоколу активів для Bitcoin та Lightning Network. Далі еволюція цих ідей призвела до розробки RGB як повноцінної системи смарт-контрактів Максимом Орловським, який з 2019 року очолює її впровадження за участю спільноти.

Ми можемо визначити RGB як набір відкритих протоколів, які дозволяють нам виконувати складні смарт-контракти масштабовано та конфіденційно. Це не конкретна мережа (як Bitcoin або Lightning); кожен смарт-контракт є лише набором учасників контракту, які можуть взаємодіяти за допомогою різних комунікаційних каналів (за замовчуванням через Lightning Network). RGB використовує блокчейн Bitcoin як шар фіксації стану та підтримує код смарт-контракту та дані поза ланцюгом, що робить його масштабованим, використовуючи транзакції Bitcoin (та Script) як систему контролю власності для смарт-контрактів; тоді як еволюція смарт-контракту визначається схемою поза ланцюгом, нарешті, важливо зазначити, що все валідується на стороні клієнта.

Простими словами, RGB - це система, яка дозволяє користувачу аудитувати смарт-контракт, виконувати його та перевіряти індивідуально в будь-який час без додаткових витрат, оскільки для цього вона не використовує блокчейн як "традиційні" системи, складні системи смарт-контрактів були започатковані Ethereum, але через те, що вони вимагають від користувача витрачати значні суми газу за кожну операцію, вони ніколи не досягли обіцяної масштабованості, внаслідок чого ніколи не стали варіантом для банківського обслуговування користувачів, виключених з поточної фінансової системи.
Наразі індустрія блокчейну просуває ідею, що як код смарт-контрактів, так і дані мають зберігатися в блокчейні та виконуватися кожним вузлом мережі, незалежно від надмірного збільшення розміру чи неправильного використання обчислювальних ресурсів. Схема, запропонована RGB, є набагато розумнішою та ефективнішою, оскільки вона відходить від парадигми блокчейну, маючи смарт-контракти та дані, відокремлені від блокчейну, і таким чином уникає перевантаження мережі, яке спостерігається на інших платформах, і водночас не змушує кожен вузол виконувати кожен контракт, а лише залучені сторони, що додає конфіденційності на рівні, який раніше не спостерігався.
![RGB проти Ethereum](assets/1.webp)

## Смарт-контракти в RGB

У смарт-контракті RGB розробник визначає схему, яка вказує правила, за якими контракт розвивається з часом. Схема є стандартом для створення смарт-контрактів в RGB, і як емітент при визначенні контракту для емісії, так і гаманець або біржа повинні дотримуватися певної схеми, згідно з якою вони повинні валідувати контракт. Тільки якщо валідація вірна, кожна сторона може приймати запити та працювати з активом.

Смарт-контракт в RGB є спрямованим ациклічним графом (DAG) змін стану, де завжди відома лише частина графа, і немає доступу до решти. Схема RGB є основним набором правил для розвитку цього графа, з яким починається смарт-контракт. Кожен учасник контракту може додавати до цих правил (якщо це дозволено схемою), і результуючий граф будується з ітеративного застосування цих правил.

## Фангібельні активи

Фангібельні активи в RGB слідують специфікації LNPBP RGB-20, коли визначається RGB-20, дані активу, відомі як "дані генезису", розповсюджуються через мережу Lightning, яка містить те, що необхідно для використання активу. Найпростіша форма активів не дозволяє вторинну емісію, спалення токенів, переномінацію або заміну.

Іноді емітенту може знадобитися випустити більше токенів у майбутньому, наприклад, стейблкоїни, такі як USDT, які зберігають вартість кожного токена прив'язаною до вартості інфляційної валюти, такої як USD. Для досягнення цього існують більш складні схеми RGB-20, і крім даних генезису вони вимагають від емітента виробляти консигнації, які також будуть циркулювати в мережі Lightning; з цією інформацією ми можемо знати загальну циркуляційну пропозицію активу. Те саме стосується спалення активів або зміни їх назви.

Інформація, пов'язана з активом, може бути публічною або приватною: якщо емітент вимагає конфіденційності, він/вона може вибрати не ділитися інформацією про токен і проводити операції в абсолютній приватності, але ми також маємо протилежний випадок, коли емітент і власники потребують, щоб весь процес був прозорим. Це досягається шляхом обміну даними токена.

## Процедури RGB-20

Процедура спалення деактивує токени, спалені токени більше не можуть бути використані.

Процедура заміни відбувається, коли токени спалені, і створюється нова кількість того ж токена. Це допомагає зменшити розмір історичних даних активу, що важливо для підтримки швидкості активу.

Для підтримки випадку використання, коли можливо спалити активи без необхідності їх заміни, використовується підсхема RGB-20, яка дозволяє лише спалення активів.

## Нефангібельні активи
Незамінні активи в RGB слідують специфікації LNPBP RGB-21, коли ми працюємо з NFT, у нас також є основна схема та додаткова схема. Ці схеми мають процедуру гравіювання, яка дозволяє нам прикріплювати користувацькі дані з боку власника токена, найпоширеніший приклад, який ми бачимо в NFT сьогодні, - це цифрове мистецтво, пов'язане з токеном. Емітент токена може заборонити це гравіювання даних, використовуючи додаткову схему RGB-21. На відміну від інших систем NFT на блокчейні, RGB дозволяє розподіляти дані медіа токенів великого розміру в повністю децентралізований та стійкий до цензури спосіб, використовуючи розширення для мережі Lightning P2P, яке називається Bifrost, яке також використовується для створення багатьох інших форм функціональності специфічних для RGB смарт-контрактів.
Крім замінних активів та NFT, RGB та Bifrost можуть використовуватися для створення інших форм смарт-контрактів, включаючи DEXes, пули ліквідності, алгоритмічні стабільні монети тощо, про що ми розповімо в майбутніх статтях.

## NFT з RGB проти NFT з інших платформ

- Немає потреби в дорогому зберіганні на блокчейні
- Немає потреби в IPFS, замість цього використовується розширення мережі Lightning (назване Bifrost) (і воно повністю зашифроване від кінця до кінця)
- Немає потреби в спеціальному рішенні для управління даними – знову ж таки, Bifrost виконує цю роль
- Немає потреби довіряти вебсайтам для підтримки даних для токенів NFT або про випущені активи / контрактні ABI
- Вбудоване шифрування DRM та управління власністю
- Інфраструктура для резервного копіювання за допомогою мережі Lightning (Bifrost)
- Способи монетизації контенту (не тільки продаж самого NFT, але й доступ до контенту, кілька разів)

## Висновки

З моменту запуску Bitcoin майже 13 років тому було проведено багато досліджень та експериментів у цій галузі, як успіхи, так і помилки дозволили нам трохи краще зрозуміти, як на практиці поводяться децентралізовані системи, що робить їх дійсно децентралізованими та які дії, як правило, призводять їх до централізації, все це привело нас до висновку, що справжня децентралізація є рідкісним і важким до досягнення явищем, справжню децентралізацію досягнуто лише Bitcoin і саме тому ми зосереджуємо наші зусилля на побудові на його основі.

RGB має свою власну кролячу нору всередині кролячої нори Bitcoin, поки я падаю через них, я буду публікувати те, що я дізнався, у наступній статті ми матимемо вступ до вузлів LNP та RGB та як їх використовувати.

# Посібник по RGB-node

## Вступ

У цьому посібнику ми пояснюємо, як використовувати RGB-node для створення замінного токена та як його передати, цей документ базується на демонстрації RGB-node і відрізняється тим, що цей посібник використовує реальні дані тестової мережі, і для цього нам потрібно побудувати власну Частково Підписану Біткойн Транзакцію, psbt з цього моменту.

## Вимоги

Рекомендується використання дистрибутиву Linux, цей посібник був написаний, використовуючи Pop!OS, який базується на Ubuntu, і вам знадобиться:

- cargo
- Bitcoin core
- git
Примітка: Цей навчальний посібник показує виконання команд у терміналі Linux, щоб розрізнити, що користувач пише, і відповідь, яку він отримує в терміналі, ми включаємо символ $, що символізує bash-запрошення.
Вам потрібно буде встановити деякі залежності:

```
$ sudo apt install -y build-essential pkg-config libzmq3-dev libssl-dev libpq-dev libsqlite3-dev cmake
```

Збірка та Запуск

RGB-node знаходиться в розробці (WIP), тому ми повинні розташуватися на конкретному коміті (3f3c520c19d84c66d430e76f0fc68c5a66d79c84), щоб змогти правильно скомпілювати та використовувати його, для цього ми виконуємо наступні команди.

```
$ git clone https://github.com/rgb-org/rgb-node.git
$ cd rgb-node
$ git checkout 3f3c520c19d84c66d430e76f0fc68c5a66d79c84
```

Тепер ми компілюємо його, не забудьте використовувати прапорець --locked, оскільки було введено зміну, яка порушує сумісність у версії clap.

```
$ cargo install --path . --all-features --locked

....
....
    Finished release [optimized] target(s) in 2m 14s
  Installing /home/user/.cargo/bin/fungibled
  Installing /home/user/.cargo/bin/rgb-cli
  Installing /home/user/.cargo/bin/rgbd
  Installing /home/user/.cargo/bin/stashd
   Installed package `rgb_node v0.4.2 (/home/user/dev/rgb-node)` (executables `fungibled`, `rgb-cli`, `rgbd`, `stashd`)

```

Як нам каже компілятор Rust, бінарні файли були скопійовані до директорії $HOME/.cargo/bin, якщо ваш компілятор скопіював їх в інше місце, ви повинні переконатися, що ця директорія має бути включена в $PATH.

Серед встановлених бінарних файлів ми можемо побачити три демони або сервіси (файли, що закінчуються на d) та cli (інтерфейс командного рядка), cli дозволяє нам взаємодіяти з основним демоном rgbd. Оскільки в цьому навчальному посібнику ми збираємося запустити два вузли, нам також знадобляться два клієнти, кожен з яких повинен підключатися до свого власного вузла, для цього ми створюємо два псевдоніми.

```
alias rgb0-cli="$HOME/.cargo/bin/rgb-cli -d $HOME/rgbdata/data0 -n testnet"
alias rgb1-cli="$HOME/.cargo/bin/rgb-cli -d $HOME/rgbdata/data1 -n testnet"
```

Ми можемо просто запустити псевдоніми або додати їх до кінця файлу $HOME/.bashrc і виконати source $HOME/.bashrc.
Преміса

RGB-node не обробляє жодної функціональності, пов'язаної з гаманцем, він просто виконує завдання, специфічні для RGB, над даними, які будуть надані зовнішнім гаманцем, як-от bitcoin core. Зокрема, для демонстрації базового робочого процесу з випуском та передачею, нам знадобляться:

- issuance_utxo, до якого rgb-node-0 прив'яже новостворений актив
- receive_utxo, де rgb-node-1 отримає актив
- change_utxo, де rgb-node-0 отримає зміну активу
- Частково підписана біткойн-транзакція (tx.psbt), вихідний публічний ключ якої буде змінено, щоб включити зобов'язання щодо передачі.

Ми будемо використовувати bitcoin core cli, нам потрібно мати запущений демон bitcoind на testnet, це дасть нам взаємодію і в кінці ми зможемо відправити наші власні активи іншому користувачу RGB, який слідував цьому навчальному посібнику.
Задля спрощення ми додамо цей псевдонім в кінець нашого файлу ~/.bashrc.
```
alias bcli="bitcoin-cli -testnet"
```

Давайте перелічимо наші невитрачені транзакції та виберемо дві, одна буде issuance_utxo, а інша - change_utxo, не має значення, яка з них яка, головне, що емітент контролює ці два UTXO.

```
$ bcli listunspent
[
  {
    "txid": "4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893",
    "vout": 1,
    "address": "tb1qn4w9u5x0hxgm30hx6q2rhdwz58xr4ekqdq0vgm",
    "label": "",
    "scriptPubKey": "00149d5c5e50cfb991b8bee6d0143bb5c2a1cc3ae6c0",
    "amount": 0.01703963,
    "confirmations": 62432,
    "spendable": true,
    "solvable": true,
    "desc": "wpkh([ec924f82/0'/0'/5']031e0fc9a03e69326c3deeabfd749a7f7b094e3151ada90cd13019efac663c5663)#dj7rhpdt",
    "safe": true
  },
  {
    "txid": "cd66d3b77dfc1c2ecf958847c16a8a1311bba84ee7bf9dd55592a7b97b13028f",
    "vout": 1,
    "address": "tb1qyd537gf0xmm9ehmhaf3nv0a230crg56mhp9ap3",
    "scriptPubKey": "001423691f212f36f65cdf77ea63363faa8bf034535b",
    "amount": 0.02877504,
    "confirmations": 189184,
    "spendable": true,
    "solvable": true,
    "desc": "wpkh([ec924f82/0'/1'/0']03ae333417e86840145e95ab2852c8f7ca8b8f82cd910883f7ce0c69649403cef2)#jlcj23vw",
    "safe": true
  }
]
```

Перед тим як рухатися далі, нам потрібно поговорити про outpoints, одна транзакція може включати кілька виходів, outpoint включає в себе 32-байтовий TXID та 4-байтовий номер індексу виходу (vout), щоб посилатися на конкретний вихід, розділений двокрапкою :. У нашому списку невитрачених виходів ми можемо знайти два UTXO, на кожному з яких ми можемо побачити txid та vout, це наші outpoints для issuance_utxo та change_utxo.

receive_utxo - це UTXO, яке контролюється одержувачем, у цьому випадку ми використаємо e40d9037e31d3f440552b30af16e764cf25ffda3899b4851cc4e38fd64718b09:0, який є outpoint з іншого гаманця.
- issuance_utxo: 4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1
- change_utxo: cd66d3b77dfc1c2ecf958847c16a8a1311bba84ee7bf9dd55592a7b97b13028f:1
- receive_utxo: e40d9037e31d3f440552b30af16e764cf25ffda3899b4851cc4e38fd64718b09:0

Тепер ми створимо частково підписану транзакцію (tx.psbt), вихід якої буде змінено, щоб включити зобов'язання про передачу, пам'ятайте замінити txid та vout на свої власні, адреса отримувача не має великого значення, вона може бути вашою або чиєюсь іншою, не має значення, куди підуть ці sats, головне, що ми використовуємо issuance_utxo.

```
$ bcli walletcreatefundedpsbt "[{/"txid/":/"4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893/",/"vout/":1}]" "[{/"tb1q9crtjp0y6rt00c4fcrmuamrylzkcalcxls80j9/":/"0.00050000/"}]"
{
  "psbt": "cHNidP8BAHECAAAAAZM4E58uD9auiZ7esJkFbmD5p/7PcgBTn5UwiQ0hhRdMAQAAAAD/////ArM7GQAAAAAAFgAU4xQr/g1lgG2P9+gZudpFD8mOGGRQwwAAAAAAABYAFC4GuQXk0Nb34qnA987sZPitjv8GAAAAAAABAHECAAAAAYiK0TdTiaEs4oDovRokqspfLZr5EHYH8Pnj/Tv5GFB5AQAAAAD+////Av8Bh80AAAAAFgAUsLjOd30aRkUna41LAT5c3CnAz5obABoAAAAAABYAFJ1cXlDPuZG4vubQFDu1wqHMOubAyw8gAAEBHxsAGgAAAAAAFgAUnVxeUM+5kbi+5tAUO7XCocw65sAiBgMeD8mgPmkybD3uq/10mn97CU4xUa2pDNEwGe+sZjxWYxDskk+CAAAAgAAAAIAFAACAACICA2J21wOqW6bj7/ePTVI7QGvU6e4Sk8DhN5pmd9hrwSd7EOyST4IAAACAAQAAgAcAAIAAAA==",
  "fee": 0.00000280,
  "changepos": 0
}
```

Вихід надав нам psbt у кодуванні base64, який ми використаємо для створення tx.psbt.
```
$ echo "cHNidP8BAHECAAAAAZM4E58uD9auiZ7esJkFbmD5p/7PcgBTn5UwiQ0hhRdMAQAAAAD/////ArM7GQAAAAAAFgAU4xQr/g1lgG2P9+gZudpFD8mOGGRQwwAAAAAAABYAFC4GuQXk0Nb34qnA987sZPitjv8GAAAAAAABAHECAAAAAYiK0TdTiaEs4oDovRokqspfLZr5EHYH8Pnj/Tv5GFB5AQAAAAD+////Av8Bh80AAAAAFgAUsLjOd30aRkUna41LAT5c3CnAz5obABoAAAAAABYAFJ1cXlDPuZG4vubQFDu1wqHMOubAyw8gAAEBHxsAGgAAAAAAFgAUnVxeUM+5kbi+5tAUO7XCocw65sAiBgMeD8mgPmkybD3uq/10mn97CU4xUa2pDNEwGe+sZjxWYxDskk+CAAAAgAAAAIAFAACAACICA2J21wOqW6bj7/ePTVI7QGvU6e4Sk8DhN5pmd9hrwSd7EOyST4IAAACAAQAAgAcAAIAAAA==" | base64 -d > tx.psbt
```

Створимо нову директорію під назвою rgbdata, в якій будуть зберігатися дані кожного вузла.

```
$ mkdir $HOME/rgbdata
$ cd $HOME/rgbdata
```

Вже перебуваючи в $HOME/rgbdata, ми запускаємо кожен вузол в різних терміналах, де ~/.cargo/bin - це директорія, куди cargo скопіював всі бінарні файли після встановлення rgb-node.

```
$ rgbd -vvvv -b ~/.cargo/bin -d ./data0 -n testnet
$ rgbd -vvvv -b ~/.cargo/bin -d ./data1 -n testnet
```

## Випуск

Для випуску активу ми використовуємо команду rgb0-cli з підкомандами fungible issue, потім аргументи, тікер USDT, назву "USD Tether" і в розподілі ми використовуємо кількість випуску та issuance_utxo, як показано нижче:

```
$ rgb0-cli fungible issue USDT "USD Tether" 1000@4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1
```

Актив успішно випущено. Використовуйте цю інформацію для обміну:
Інформація про актив:

```
genesis: genesis1qyfe883hey6jrgj2xvk5g3dfmfqfzm7a4wez4pd2krf7ltsxffd6u6nrvjvvnc8vt9llmp7663pgututl9heuwaudet72ay9j6thc6cetuvhxvsqqya5xjt2w9y4u6sfkuszwwctnrpug5yjxnthmr3mydg05rdrpspcxysnqvvqpfvag2w8jxzzsz9pf8pjfwf0xvln5z7w93yjln3gcnyxsa04jsf2p8vu4sxgppfv0j9qerppqxhvztpqscnjsxvq5gdfy5v6j3wvpjxxqzcerxuglngnfvpxjkgqusct7cyx8zzezcfpqv3nxjxm2kjj4d0zu0ta6fjmpr8a0calk6h88h4ap5e4nucj0ch07aa73qsh3lj5sd89a32kwy0eq7tsa5zqqjpdqvqq5s46r0id: rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6
ticker: USDT
name: USD Tether
description: ~
knownCirculating: 1000
isIssuedKnown: ~
issueLimit: 0
chain: testnet
decimalPrecision: 0
date: "2022-02-23T20:53:26"
knownIssues:
  - id: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
    amount: 1000
    origin: ~
knownInflation: {}
knownAllocations:
  - nodeId: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
    index: 0
    outpoint: "4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1"
    revealedAmount:
      value: 1000
      blinding: "0000000000000000000000000000000000000000000000000000000000000001"
Ми отримали assetId, він нам потрібен для передачі активу.

```
$ rgb0-cli fungible list

- name: USD Tether
  id: rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6
  ticker: USDT
```

## Генерація замаскованого UTXO

Для того, щоб отримати нові USDT, rgb-node-1 потрібно згенерувати замаскований UTXO, відповідний до receive_utxo, для зберігання активу.

```
$ rgb1-cli fungible blind e40d9037e31d3f440552b30af16e764cf25ffda3899b4851cc4e38fd64718b09:0

Замаскований вихід: utxob16az597vp5nkr66nfzsykf8ngdnvzep5050rm00l7vv8wm7vew4jqj7jhhf
Секрет замаскування вихідного пункту: 1679197189805229975
```

Для того, щоб мати можливість приймати передачі, пов'язані з цим UTXO, нам буде потрібен оригінальний receive_utxo та blinding_factor.

## Передача

Для передачі певної кількості активу до rgb-node-1 нам потрібно відправити його на замаскований UTXO, rgb-node-0 потрібно створити консигнацію та розкриття, та здійснити їх у біткойн-транзакції. Потім нам буде потрібен psbt, який ми модифікуємо, щоб включити зобов'язання. Крім того, опції -i та -a дозволяють нам надати вихідний пункт, який буде походженням активу, та розподіл, де ми отримаємо решту, ми повинні вказати його наступним чином @<change_utxo>.
$ rgb0-cli fungible transfer utxob16az597vp5nkr66nfzsykf8ngdnvzep5050rm00l7vv8wm7vew4jqj7jhhf 100 rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6 tx.psbt consignment.rgb disclosure.rgb witness.psbt -i 4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1 -a 900@cd66d3b77dfc1c2ecf958847c16a8a1311bba84ee7bf9dd55592a7b97b13028f:1
Переказ успішний, консигнації та розкриття інформації записані до "consignment.rgb" та "disclosure.rgb", частково підписана транзакція свідка до "witness.psbt"
Дані для обміну: consignment1qxz4g7ec6da33llaxe97u9hx8p9wcgp2yv46ycudwy7ytjf4gdh88x6upcdmjfy3mp4y0n669j5ar5y6e04zfr7255kynff6eymx9tdfc7jux5jk6tgn4xm6lttlh3lh08070ltuh60l07mamlns2qyy984mg4m5dz0x6s5sy5edls2zjlmnvw708sh7fy2vuph745jcpgp92qrw27s73vm4ghrx57vammyf8wautwu5euujd8w3dupdtgp4px36gz8z0ywnuty45uqdwk672qqzjp3j77yl7urft6gewqksqgppczezn5c7gyux6gzgpye0wgyjp85ufdqlzy5cd8zwfg3q9550xq2hyf24qqz92wqskpgq8qsr8kp5p9dt49evmqlze9ylrx2sqpwpvpqp45lpvgjkgk542pks9850w5jquq3qqsj4xsqn9nu6w30lgpmrhdqs6jj0ez3myhj74kp223f0wg2y7vupczdq5pa23mzhzc6l647nl6ftrru0mjrh739yhgztsdhl2cdmhf0qm7du9n20up4rnnsp0tlp8665xldkq9z9u85tgh6nxmkfg3pc6wzk2t90pekj2d6l0km09vyt4vut24vhzg9qhrdsgr7dws828p6ejk7ddy0zkz3a2fq5648664w3se2egwvh904lzmpnc7a7wy4fayznunt6j4ndmm68y24tjje4qxnxs70w4lr9vz9q9qca903edtjd6c5f37jagafsqnhnlsuwvnqwc7uly4dw2rnlyxp4zcfqrfpkpez54c0lc3tmvppmv06ge97heevgt0acrq0ezgjr6ck9waqpanypl8dzrqdzjd05h735tdgv2wjjjucheur40h4wjw4pcdpc8pqlh7ef95rj2al8v3eexkgty8j2ne7kk2zxpe0wypq8ra0x76rt6cu00cw4w05v0u3ng6zhfrttz2c3m5nx64s8w98wa26dx79jwhne44gp9lmg6vkhxq98meslyr4zqtxjsg27xzj80m0csd77lr047vwycvdw0z8mwudm3uvlry9p9da4su72k9q84pphw4n0fyeet0ujzrdgacm6p777jun0y0v397mp4drafr6q7994kdl96m388xp6ggf5arn4d4ed53rv9tlkerckqvkng92uhdvngwcl3m6yqhxdjjnkca62tckxfnrae4cx4e6wx6ww5649v4hvuwkkajanllc38wavqy83xhn555l708354nt2quscchexsxjgezdxfnmxgue0cn4ktghd6xd2le76k5cw3t0p0nurs4h5rjz0j7twj9ulwkp7cmhhgl23r7g677gk36r5jw8panh2sq5966m08sa5632egd5ms6h0e504dtwskct3x6a93uutaumtc8aam8yyt66lrmrhcssw9ga2yg0496s6sdmaexa49064g3syc888egnwa8racrwwwwemknqamarpqlmqa5mg8zgt0dts8ehuwmgz4j3cjltr8gv78e7p84zm8pylann7dmss5suf4htqc04qx5trnk59m305ah2qp4mvkxwy6ts84sa30d80jzk9s6n40e4j8dcvq79ncg5e3z5g4esxyawmxk7lvm5efc30vtw8qqhe9xx3773djez6hjjx0x962z2radnvdmazkrmlqw7guxz29qvahcx79h33ncqhzhvekwaqqnrz3wxnp2qy3u83zdgdcgq27n5n22h7jjedrh28m8c6mn42xhfjasm5njsxtufqjxefnhc2n5zr0um0xlqk62cu25cjwuwwrcv3e4vhh2tdzn8rnlaefj98fvslg7sun95wpt2a4vcg4ua62v97aeqstvjegmlem5crnsamrhm3a2pcma2s22atr43lgx9vh7kn9lzymfe83a4vhe9rc6xl5pmy5hjw4t88k0fwh6lzmjtjvqtczq47ny7hv8ytdqdy2c7ce3gegnufkzwphkwtz6xqzklyw7e7f76fwfewfuyqal7dl8r9476jerrl40mav38sun2u8jvftw33x3r20dmeka34znmkgaz29ppk5hz3ldttw8zyz4k6q0gts8utqh53tuc7vtajl26rq2fnxr0vxcwlx9rfvn6v8ar8c73qkc3zca4mlgl7qu36sk7e
Це створить три нові файли: consignment, disclosure та psbt з додаванням tweak, цей psbt називається witness transaction, consignment відправляється до rgb-node-1.

## Witness

Witness transaction потрібно підписати та розіслати, для цього нам потрібно знову закодувати його в base64.

```
$ base64 -w0 witness.psbt

cHNidP8BAHECAAAAAe2pydT0BqfK5nBCdBSbm3W/vNKE/QxTr4eJcjwjDLDjAQAAAAD/////AiWbAAAAAAAAFgAUO1Bi4v2VHUJPmq5iyYhDv1tyTCcQJwAAAAAAABYAFPwfm3skdSeMnOfcDqBpgVjwuwESAAAAAAABAHECAAAAAeSwUiZ+p3/NM7yt3BAoDkm/afi//lplsffwwpTqjd+CAQAAAAD/////AlDDAAAAAAAAFgAULga5BeTQ1vfiqcD3zuxk+K2O/wbDwgAAAAAAABYAFLsvLLowx0NR5NyFKj9wl3IFvNcPAAAAAAEBH8PCAAAAAAAAFgAUuy8sujDHQ1Hk3IUqP3CXcgW81w8iBgKIYFEbYKvRj25inaA0/c0PMIZD/BFAgFbjrBJe8cZ+cxDskk+CAAAAgAEAAIADAACAACICAsnwAXsMVlPXi/2ExgqtLoIN4TncWVW0EImSo9YwyhNmEOyST4IAAACAAQAAgAUAAIAG/ANSR0IBIQLJ8AF7DFZT14v9hMYKrS6CDeE53FlVtBCJkqPWMMoTZgb8A1JHQgIgMD8j8bQGB8NgEobv3NUJr7aERA/FkGgQ5w2KwF+daDgAAA==
```

Підпишіть його за допомогою підкоманди walletprocesspsbt.
```yaml
$ bcli walletprocesspsbt "cHNidP8BAHECAAAAAe2pydT0BqfK5nBCdBSbm3W/vNKE/QxTr4eJcjwjDLDjAQAAAAD/////AiWbAAAAAAAAFgAUO1Bi4v2VHUJPmq5iyYhDv1tyTCcQJwAAAAAAABYAFPwfm3skdSeMnOfcDqBpgVjwuwESAAAAAAABAHECAAAAAeSwUiZ+p3/NM7yt3BAoDkm/afi//lplsffwwpTqjd+CAQAAAAD/////AlDDAAAAAAAAFgAULga5BeTQ1vfiqcD3zuxk+K2O/wbDwgAAAAAAABYAFLsvLLowx0NR5NyFKj9wl3IFvNcPAAAAAAEBH8PCAAAAAAAAFgAUuy8sujDHQ1Hk3IUqP3CXcgW81w8iBgKIYFEbYKvRj25inaA0/c0PMIZD/BFAgFbjrBJe8cZ+cxDskk+CAAAAgAEAAIADAACAACICAsnwAXsMVlPXi/2ExgqtLoIN4TncWVW0EImSo9YwyhNmEOyST4IAAACAAQAAgAUAAIAG/ANSR0IBIQLJ8AF7DFZT14v9hMYKrS6CDeE53FlVtBCJkqPWMMoTZgb8A1JHQgIgMD8j8bQGB8NgEobv3NUJr7aERA/FkGgQ5w2KwF+daDgAAA=="
```
Як кваліфікований професійний перекладач, я зосереджуся на забезпеченні точного перекладу технічного контенту, зберігаючи при цьому оригінальні технічні терміни та форматування. Ось перекладений текст:

```json
"psbt": "cHNidP8BAHECAAAAAe2pydT0BqfK5nBCdBSbm3W/vNKE/QxTr4eJcjwjDLDjAQAAAAD/////AiWbAAAAAAAAFgAUO1Bi4v2VHUJPmq5iyYhDv1tyTCcQJwAAAAAAABYAFPwfm3skdSeMnOfcDqBpgVjwuwESAAAAAAABAHECAAAAAeSwUiZ+p3/NM7yt3BAoDkm/afi//lplsffwwpTqjd+CAQAAAAD/////AlDDAAAAAAAAFgAULga5BeTQ1vfiqcD3zuxk+K2O/wbDwgAAAAAAABYAFLsvLLowx0NR5NyFKj9wl3IFvNcPAAAAAAEBH8PCAAAAAAAAFgAUuy8sujDHQ1Hk3IUqP3CXcgW81w8BCGsCRzBEAiAZud+YVf1FyZq0IDQ+/oAE34TKypedrJGUcYx0QIpaygIgZJO7xvN0dOQXbXTRYE0QxGIWsfo85Dhwne0/whoO06kBIQKIYFEbYKvRj25inaA0/c0PMIZD/BFAgFbjrBJe8cZ+cwAiAgLJ8AF7DFZT14v9hMYKrS6CDeE53FlVtBCJkqPWMMoTZhDskk+CAAAAgAEAAIAFAACABvwDUkdCASECyfABewxWU9eL/YTGCq0ugg3hOdxZVbQQiZKj1jDKE2YG/ANSR0ICIDA/I/G0BgfDYBKG79zVCa+2hEQPxZBoEOcNisBfnWg4AAA=",  "complete": true
}
```

Тепер завершіть це та отримайте hex.
```yaml
$ bcli finalizepsbt "cHNidP8BAHECAAAAAe2pydT0BqfK5nBCdBSbm3W/vNKE/QxTr4eJcjwjDLDjAQAAAAD/////AiWbAAAAAAAAFgAUO1Bi4v2VHUJPmq5iyYhDv1tyTCcQJwAAAAAAABYAFPwfm3skdSeMnOfcDqBpgVjwuwESAAAAAAABAHECAAAAAeSwUiZ+p3/NM7yt3BAoDkm/afi//lplsffwwpTqjd+CAQAAAAD/////AlDDAAAAAAAAFgAULga5BeTQ1vfiqcD3zuxk+K2O/wbDwgAAAAAAABYAFLsvLLowx0NR5NyFKj9wl3IFvNcPAAAAAAEBH8PCAAAAAAAAFgAUuy8sujDHQ1Hk3IUqP3CXcgW81w8BCGsCRzBEAiAZud+YVf1FyZq0IDQ+/oAE34TKypedrJGUcYx0QIpaygIgZJO7xvN0dOQXbXTRYE0QxGIWsfo85Dhwne0/whoO06kBIQKIYFEbYKvRj25inaA0/c0PMIZD/BFAgFbjrBJe8cZ+cwAiAgLJ8AF7DFZT14v9hMYKrS6CDeE53FlVtBCJkqPWMMoTZhDskk+CAAAAgAEAAIAFAACABvwDUkdCASECyfABewxWU9eL/YTGCq0ugg3hOdxZVbQQiZKj1jDKE2YG/ANSR0ICIDA/I/G0BgfDYBKG79zVCa+2hEQPxZBoEOcNisBfnWg4AAA="{
  "hex": "02000000000101eda9c9d4f406a7cae6704274149b9b75bfbcd284fd0c53af8789723c230cb0e30100000000ffffffff02259b0000000000001600143b5062e2fd951d424f9aae62c98843bf5b724c271027000000000000160014fc1f9b7b2475278c9ce7dc0ea0698158f0bb011202473044022019b9df9855fd45c99ab420343efe8004df84caca979dac9194718c74408a5aca02206493bbc6f37474e4176d74d1604d10c46216b1fa3ce438709ded3fc21a0ed3a90121028860511b60abd18f6e629da034fdcd0f308643fc11408056e3ac125ef1c67e7300000000",
  "complete": true
}
```

## Трансляція

Транслюйте його за допомогою підкоманди sendrawtransaction, щоб підтвердити його в блокчейні.

```
## Прийняти

Щоб прийняти вхідний переказ, rgb-node-1 повинен був отримати файл консигнації від rgb-node-0, мати receive_utxo та відповідний blinding_factor, створений під час генерації засліплення UTXO.

```
$ rgb1-cli fungible accept consignment.rgb e40d9037e31d3f440552b30af16e764cf25ffda3899b4851cc4e38fd64718b09:0 1679197189805229975

Переказ активів успішно прийнято.
```

Тепер ми можемо побачити (у полі knownAllocations) нове розміщення 100 одиниць активу в <receive_utxo>, виконавши:

```
$ rgb1-cli fungible list -l

- genesis: genesis1qyfe883hey6jrgj2xvk5g3dfmfqfzm7a4wez4pd2krf7ltsxffd6u6nrvjvvnc8vt9llmp7663pgututl9heuwaudet72ay9j6thc6cetuvhxvsqqya5xjt2w9y4u6sfkuszwwctnrpug5yjxnthmr3mydg05rdrpspcxysnqvvqpfvag2w8jxzzsz9pf8pjfwf0xvln5z7w93yjln3gcnyxsa04jsf2p8vu4sxgppfv0j9qerppqxhvztpqscnjsxvq5gdfy5v6j3wvpjxxqzcerxuglngnfvpxjkgqusct7cyx8zzezcfpqv3nxjxm2kjj4d0zu0ta6fjmpr8a0calk6h88h4ap5e4nucj0ch07aa73qsh3lj5sd89a32kwy0eq7tsa5zqqjpdqvqq5s46r0
  id: rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6
  ticker: USDT
```
```yaml
name: USD Tether
description: ~
  knownCirculating: 1000
  isIssuedKnown: ~
  issueLimit: 0
  chain: testnet
  decimalPrecision: 0
  date: "2022-02-23T20:53:26"
  knownIssues:
    - id: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      amount: 1000
      origin: ~
  knownInflation: {}
  knownAllocations:
    - nodeId: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      index: 0
      outpoint: "4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1"
      revealedAmount:
        value: 1000
        blinding: "0000000000000000000000000000000000000000000000000000000000000001"
    - nodeId: 28f82e2dcfa91282c28a8805ff0c7fde4bd4e0bdbd40c6ba55e191666e45327b
      index: 1
      outpoint: "e40d9037e31d3f440552b30af16e764cf25ffda3899b4851cc4e38fd64718b09:0"
      revealedAmount:
        value: 100
        blinding: 224561f10229eb9ebbdf05f497132d2b8344d70971c80510eddc607d615ee2a0

Оскільки receive_utxo було замасковано під час переказу, відправник rgb-node-0 не має інформації про місце, куди було відправлено 100 USDT, тому місцезнаходження не вказано у knownAllocations.

$ rgb0-cli fungible list -l

- genesis: genesis1qyfe883hey6jrgj2xvk5g3dfmfqfzm7a4wez4pd2krf7ltsxffd6u6nrvjvvnc8vt9llmp7663pgututl9heuwaudet72ay9j6thc6cetuvhxvsqqya5xjt2w9y4u6sfkuszwwctnrpug5yjxnthmr3mydg05rdrpspcxysnqvvqpfvag2w8jxzzsz9pf8pjfwf0xvln5z7w93yjln3gcnyxsa04jsf2p8vu4sxgppfv0j9qerppqxhvztpqscnjsxvq5gdfy5v6j3wvpjxxqzcerxuglngnfvpxjkgqusct7cyx8zzezcfpqv3nxjxm2kjj4d0zu0ta6fjmpr8a0calk6h88h4ap5e4nucj0ch07aa73qsh3lj5sd89a32kwy0eq7tsa5zqqjpdqvqq5s46r0
```
```yaml
id: rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6  ticker: USDT
  name: USD Tether
  description: ~
  knownCirculating: 1000
  isIssuedKnown: ~
  issueLimit: 0
  chain: testnet
  decimalPrecision: 0
  date: "2022-02-23T20:53:26"
  knownIssues:
    - id: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      amount: 1000
      origin: ~
  knownInflation: {}
  knownAllocations:
    - nodeId: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      index: 0
      outpoint: "4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1"
      revealedAmount:
        value: 1000
        blinding: "0000000000000000000000000000000000000000000000000000000000000001"
```

Але, як ви можете бачити, rgb-node-0 не може побачити зміну активів на 900, яку ми вказали у команді передачі з аргументом -a. Щоб зареєструвати зміну, rgb-node-0 потрібно прийняти розкриття інформації.

```
$ rgb0-cli fungible enclose disclosure.rgb

Дані розкриття успішно включені.
```

Якщо rgb-node-0 було успішно, ви можете побачити зміну, переглянувши актив.

```
$ rgb0-cli fungible list -l

- genesis: genesis1qyfe883hey6jrgj2xvk5g3dfmfqfzm7a4wez4pd2krf7ltsxffd6u6nrvjvvnc8vt9llmp7663pgututl9heuwaudet72ay9j6thc6cetuvhxvsqqya5xjt2w9y4u6sfkuszwwctnrpug5yjxnthmr3mydg05rdrpspcxysnqvvqpfvag2w8jxzzsz9pf8pjfwf0xvln5z7w93yjln3gcnyxsa04jsf2p8vu4sxgppfv0j9qerppqxhvztpqscnjsxvq5gdfy5v6j3wvpjxxqzcerxuglngnfvpxjkgqusct7cyx8zzezcfpqv3nxjxm2kjj4d0zu0ta6fjmpr8a0calk6h88h4ap5e4nucj0ch07aa73qsh3lj5sd89a32kwy0eq7tsa5zqqjpdqvqq5s46r0
  id: rgb1tadqzve7vwfh39sl6gvqenp8wegsrzreekhhu0dhthx08ppzj9wq8p0je6
  ticker: USDT
  name: USD Tether
```
Опис: ~ knownCirculating: 1000
  isIssuedKnown: ~
  issueLimit: 0
  chain: testnet
  decimalPrecision: 0
  date: "2022-02-23T20:53:26"
  knownIssues:
    - id: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      amount: 1000
      origin: ~
  knownInflation: {}
  knownAllocations:
    - nodeId: 5c912284f3cc5db73d7eafcd798801517627cc0c18d21f967893633e33015a5f
      index: 0
      outpoint: "4c1785210d8930959f530072cffea7f9606e0599b0de9e89aed60f2e9f133893:1"
      revealedAmount:
        value: 1000
        blinding: "0000000000000000000000000000000000000000000000000000000000000001"
    - nodeId: 28f82e2dcfa91282c28a8805ff0c7fde4bd4e0bdbd40c6ba55e191666e45327b
      index: 0
      outpoint: "cd66d3b77dfc1c2ecf958847c16a8a1311bba84ee7bf9dd55592a7b97b13028f:1"
      revealedAmount:
        value: 900
        blinding: ddba9e0efdd614614420fa0b68ecd2d3376a05dd3d809b2ad1f5fe0f6ed75ea2

## Висновки

Ми змогли створити фангібельний актив і перемістити його з однієї транзакції в іншу приватним способом, якщо ми перевіримо підтверджену транзакцію в блок-експлорері, ми не знайдемо нічого відмінного від звичайної транзакції, це завдяки тому, що RGB використовує одноразові печатки для модифікації транзакцій. У цьому пості я роблю вступ до того, як працює RGB.

Цей пост може містити помилки, якщо ви знайдете щось, будь ласка, дайте мені знати, щоб покращити цей посібник, пропозиції та критика також вітаються, щасливого хакінгу! 🖖