---
outdated_since: 18bc8cacbc8b5a3dbed527ddc9f385e630ea2666
outdated_translation: true
---

# .osu (формат файлу)

**`.osu`** - це придатний до читання людиною формат файлу, що зберігає інформацію про бітмапу.

## Структура

На першому рядку зазначена версія формату файлу. Наприклад, `osu file format v14` є останньою версією.

Наступний вміст розділений на розділи, позначені назвами в квадратних дужках.

| Розділ | Опис | Тип вмісту |
| :-- | :-- | :-- |
| `[General]` | Загальна інформація про бітмапу | пари `ключ: значення` |
| `[Editor]` | Збережені налаштування редактора бітмап | пари `ключ: значення` |
| `[Metadata]` | [Інформація](/wiki/Client/Beatmap_editor/Song_setup#song-and-map-metadata), що використовується для ідентифікації бітмапи | пари `ключ: значення` |
| `[Difficulty]` | [Налаштування складності](/wiki/Client/Beatmap_editor/Song_setup#difficulty) | пари `ключ: значення` |
| `[Events]` | Графічні події карти та сторіборду | Розділені комами списки |
| `[TimingPoints]` | Точки таймінгу та управління | Розділені комами списки |
| `[Colours]` | Кольори комбо та скіну | пари `ключ: значення` |
| `[HitObjects]` | Об'єкти карти | Розділені комами списки |

## Загальний

| Опція | Тип змінної | Опис | Значення за замовчуванням |
| :-- | :-- | :-- | :-- |
| `AudioFilename` | String | Локація аудіо-файлу відносно поточної папки |  |
| `AudioLeadIn` | Integer | Мілісекунди тиші перед початком гри аудіо | 0 |
| `AudioHash` | String | *Застаріле* |  |
| `PreviewTime` | Integer | Час в мілісекундах, коли має початись прев'ю аудіо | -1 |
| `Countdown` | Integer | Швидкість відліку часу перед першим об'єктом (`0` = без відліку, `1` = звичайна, `2` = в два рази повільніше, `3` = в два рази швидше) | 1 |
| `SampleSet` | String | Комплект семплів, що буде використовуватись, якщо точки таймінгу не перезапишуть його (`Normal`, `Soft`, `Drum`) | Normal |
| `StackLeniency` | Decimal | [Коефіцієнт](/wiki/Beatmap/Stack_leniency) порогу часу, при якому об'єкти, розташовані близько один до одного, складаються (0–1) | 0.7 |
| `Mode` | Integer | Режим гри (`0` = osu!, `1` = osu!taiko, `2` = osu!catch, `3` = osu!mania) | 0 |
| `LetterboxInBreaks` | 0 or 1 | Чи мають перерви [ефект каше](https://uk.wikipedia.org/wiki/Letterbox) | 0 |
| `StoryFireInFront` | 0 or 1 | *Застаріле* | 1 |
| `UseSkinSprites` | 0 or 1 | Чи може сторіборд використовувати зображення скіна користувача | 0 |
| `AlwaysShowPlayfield` | 0 or 1 | *Застаріле* | 0 |
| `OverlayPosition` | String | Порядок малювання оверлеїв кругів у порівнянні з числами попадань (`NoChange` = використовувати налаштування скіна, `Below` = малювати оверлеї під числами, `Above` = малювати оверлеї поверх чисел) | NoChange |
| `SkinPreference` | String | Бажаний скін для використання під час ігрового процесу |  |
| `EpilepsyWarning` | 0 or 1 | Чи має з'являтись попередження про миготливі кольори на початку карти | 0 |
| `CountdownOffset` | Integer | Час у тактах, коли починається відлік перед першим об'єктом | 0 |
| `SpecialStyle` | 0 or 1 | Чи використовувати стиль розташування клавіш "N+1" для osu!mania | 0 |
| `WidescreenStoryboard` | 0 or 1 | Чи підтримує сторіборд перегляд на широкому екрані | 0 |
| `SamplesMatchPlaybackRate` | 0 or 1 | Чи змінюватиметься швидкість звукових семплів при грі з модами, що змінюють швидкість аудіо | 0 |

## Редактор

Ці опції застосовуються лише при відкритті бітмапи в [редакторі](/wiki/Client/Beatmap_editor). Вони не впливають на ігровий процес.

| Опція | Тип змінної | Опис |
| :-- | :-- | :-- |
| `Bookmarks` | Розділений комами список цілих чисел | Час [закладок](/wiki/Client/Beatmap_editor/Compose#bottom-(song's-timeline)) в мілісекундах |
| `DistanceSpacing` | Decimal | Коефіцієнт [Визначеної відстані](/wiki/Client/Beatmap_editor/Distance_snap) |
| `BeatDivisor` | Integer | [Дільник поспішності ударів](/wiki/Client/Beatmap_editor/Beat_snap_divisor) |
| `GridSize` | Integer | [Розмір сітки](/wiki/Beatmapping/Grid_snapping) |
| `TimelineZoom` | Decimal | Коефіцієнт масштабу для [таймлайну об'єктів](/wiki/Client/Beatmap_editor/Compose#top-left-(hit-objects-timeline)) |

## Метадата

| Опція | Тип змінної | Опис |
| :-- | :-- | :-- |
| `Title` | String | Романізована назва пісні |
| `TitleUnicode` | String | Назва пісні |
| `Artist` | String | Романізоване ім'я виконавця |
| `ArtistUnicode` | String | Ім'я виконавця |
| `Creator` | String | Творець бітмапи |
| `Version` | String | Назва складності |
| `Source` | String | Оригінальне медіа, для якого була написана пісня |
| `Tags` | Розділений пробілами список строк | Слова для пошуку |
| `BeatmapID` | Integer | ID складності |
| `BeatmapSetID` | Integer | ID карти |

## Difficulty

| Опція | Тип змінної | Опис |
| :-- | :-- | :-- |
| `HPDrainRate` | Decimal | Показник HP (0–10) |
| `CircleSize` | Decimal | Показник CS (0–10) |
| `OverallDifficulty` | Decimal | Показник OD (0–10) |
| `ApproachRate` | Decimal | Показник AR (0–10) |
| `SliderMultiplier` | Decimal | Базова швидкість слайдера в сотнях [osu!-пікселів](/wiki/Client/Beatmap_editor/osu!_pixel) за удар |
| `SliderTickRate` | Decimal | Кількість тіків слайдеру за удар |

## Події

*Синтаксис події:* `eventType,startTime,eventParams`

- **`eventType` (String чи Integer):** Тип події. На деякі події можна посилатися як за назвою, так і за числом.
- **`startTime` (Integer):** Час початку події в мілісекундах з початку аудіо бітмапи. Для подій, що не використовують час початку, `0` є значенням за замовчуванням.
- **`eventParams` (Розділений комами список):** Додаткові параметри, специфічні для кожного типу події.

### Фони

*Синтаксис фону:* `0,0,filename,xOffset,yOffset`

- **`filename` (String):** Локація зображення фону відносно папки з картою. Назва файлу, зазвичай, береться в подвійні лапки, але це не є обов'язковим.
- **`xOffset` (Integer)** та **`yOffset` (Integer):** Зсув у [osu!-пікселях](/wiki/Client/Beatmap_editor/osu!_pixel) від центру екрану. Для прикладу, зсув `50,100` показуватиме фон на 50 osu!-пікселів правіше і 100 osu!-пікселів нижче від центру екрану. Якщо зсув рівний (`0,0`), його можна не записувати.

### Відео

*Синтаксис відео:* `Video,startTime,filename,xOffset,yOffset`

`Video` можна замінити на `1`.

- **`filename` (String)**, **`xOffset` (Integer)**, та **`yOffset` (Integer)** працюють так само, як і для фонів.

### Перерви

*Синтаксис перерви:* `2,startTime,endTime`

`2` можна замінити на `Break`.

- **`endTime` (Integer):** Час кінця перерви в мілісекундах з початку аудіо бітмапи.

### Сторіборди

*За інформацією про синтаксис сторіборду дивіться [Написання сторіборду](/wiki/Storyboard/Scripting).*

Сторіборди опціонально можуть бути визначені в окремому файлі з розширенням `.osb`. Зовнішні сторіборди є спільними для всіх складностей бітмапи.

Кожна карта може зберігати власний сторіборд, унікальний для складності, який може бути сам по собі або об'єднуватись із зовнішнім.

## Точки таймінгу

Кожна таймінгова точка впливає на визначену частину карти, яка, зазвичай, називається "таймінговою секцією". Формат файлу `.osu` вимагає, щоб вони були відсортовані в хронологічному порядку.

*Синтаксис точок таймінгу:* `time,beatLength,meter,sampleSet,sampleIndex,volume,uninherited,effects`

- **`time` (Integer):** Час початку таймінгової секції в мілісекундах з початку аудіо бітмапи. Кінцем таймінгової секції є час наступної точки таймінгу (якщо ця точка є останньою, він відсутній).
- **`beatLength` (Decimal):** Ця властивість може означати:
  - Для неуспадкованих таймінгових точок - тривалість удару в мілісекундах.
  - Для успадкованих таймінгових точок - від’ємний зворотний множник швидкості слайдера у відсотках. Наприклад, `-50` пришвидшить всі слайдери цієї таймінгової секції в два рази відносно `SliderMultiplier`.
- **`meter` (Integer):** Кількість ударів у такті. Успадковані точки таймінгу ігнорують цю властивість.
- **`sampleSet` (Integer):** Стандартний набір семплів для об’єктів (0 = за замовчуванням, 1 = звичайний, 2 = soft, 3 = drum).
- **`sampleIndex` (Integer):** Користувацький індекс семплу для об’єктів. `0` позначає хітсаунди osu! за замовчуванням.
- **`volume` (Integer):** Гучність для об'єктів у відсотках.
- **`uninherited` (0 or 1):** Чи є таймінгова точка неуспадкованою.
- **`effects` (Integer):** Бітові позначення, що дають точкам таймінгу додаткові ефекти. Дивіться [розділ про ефекти](#ефекти).

### Ефекти

Точки таймінгу мають два додаткових ефекта, які можна перемикати, використовуючи біти 0 і 3 (від менш до більш значного) у числі `effects`:

- 0: Чи активний [час кіаю](/wiki/Gameplay/Kiai_time)
- 3: Чи пропущений перший барлайн в osu!taiko і osu!mania

Решта бітів не використовуються.

### Приклади

```
10000,333.33,4,0,0,100,1,1
12000,-25,4,3,0,100,0,1
```

Перша таймінгова точка на 10 секундах є неуспадкованою та виставляє:

- BPM на 180 (`1 / 333.33 * 1000 * 60`)
- Тактовий розмір на 4/4
- Набір семплів за замовчуванням
- Індекс семплу на хітсаунди osu! за замовчуванням
- Гучність на 100%
- Час кіаю

Друга таймінгова точка на 12 секундах є успадкованою, змінюючи швидкість слайдера на 4x, а набір семплів на drum.

## Кольори

Всі опції в цьому розділі представляють кольори. Вони мають вигляд розділених комою трійок цілих чисел від 0 до 255, представляючих червоний, зелений та синій складники кольорів.

| Опція | Опис |
| :-- | :-- |
| `Combo#`, де `#` є цілим числом | Додаткові кольори комбо |
| `SliderTrackOverride` | Додатковий колір доріжки слайдера |
| `SliderBorder` | Колір границі слайдера |

## Об'єкти

*Синтаксис об'єкту:* `x,y,time,type,hitSound,objectParams,hitSample`

- **`x` (Integer)** та **`y` (Integer):** Позиція об'єкту в [osu!-пікселях](/wiki/Client/Beatmap_editor/osu!_pixel).
- **`time` (Integer):** Час, коли по об'єкту треба попасти, в мілісекундах з початку аудіо бітмапи.
- **`type` (Integer):** Бітові позначення, що вказують на тип об'єкта. Дивіться [розділ про типи](#тип).
- **`hitSound` (Integer):** Бітові позначення, що вказують на застосовані до об'єкта хітсаунди. Дивіться [розділ про хітсаунди](#хітсаунди).
- **`objectParams` (Список, розділений комою):** Додаткові параметри, унікальні для кожного типу об'єкту.
- **`hitSample` (Список, розділений двокрапкою):** Інформація про те, які семпли програються при попаданні по об'єкту. Вона сильно пов'язана з `hitSound`; дивіться [розділ про хітсаунди](#хітсаунди). Якщо вона не написана, `0:0:0:0:` буде значенням за замовчуванням.

### Тип

Параметр типу об'єкту - це 8-бітне ціле число, де кожен біт має спеціальне значення.

| Індекс біта | Значення |
| :-- | :-- |
| 0 | Позначає об'єкт кругом |
| 1 | Позначає об'єкт слайдером |
| 2 | Позначає початок нового комбо |
| 3 | Позначає об'єкт спінером |
| 4, 5, 6 | 3-бітне ціле число, вказуюче на те, скільки кольорів комбо треба пропустити. На практиці використовують назву "colour hax". Актуальне лише якщо об'єкт починає нове комбо. |
| 7 | Позначає об'єкт довгою нотою в osu!mania. |

### Хітсаунди

Бітові позначення `hitSound` визначають, які звуки програватимуться при попаданні по об'єкту:

| Індекс біта | Значення |
| :-- | :-- |
| 0 | Звичайний |
| 1 | Whistle |
| 2 | Finish |
| 3 | Clap |

Якщо жодного біта не вказано, за замовчуванням використовуватиметься стандартний звук.

В кожному режимі, крім osu!mania, властивість скіна `LayeredHitSounds` примусово включає звичайний звук, незалежно від того, встановлений біт 0 чи ні. За замовчуванням вона активована.

#### Користувацькі семпли

Використання `hitSample` може ще більше кастомізувати звуки, що програються. За замовчуванням його значення `0:0:0:0:`, якщо не написано іншого.

*Синтаксис семплу:* `normalSet:additionSet:index:volume:filename`

- **`normalSet` (Integer):** Набір семплів зі звичайним звуком.
- **`additionSet` (Integer):** Набір семплів зі звуками whistle, finish та clap.
- **`index` (Integer):** Індекс семплу. Якщо `0`, замість нього буде використано індекс семплу таймінгової точки.
- **`volume` (Integer):** Гучність семплу від 1 до 100. Якщо `0`, замість цього буде використана гучність таймінгової точки.
- **`filename` (String):** Користувацька назва файлу з додатковим звуком.

`normalSet` і `additionSet` можуть мати будь-яке з наступних значень:

- `0`: Без користувацького набору семплів
  - Для звичайних звуків набір визначається набором семплів точки таймінгу.
  - Для додаткових набір визначається набором семплів звичайного звуку.
- `1`: Звичайний набір
- `2`: Набір Soft
- `3`: Набір Drum

Всі ці опції (крім гучності) використовуються для визначення, який файл звуку програватиметься для даного хітсаунду. Назва файлу має вигляд `<sampleSet>-hit<hitSound><index>.wav`, де:

- `sampleSet` є `normal`, `soft`, чи `drum`, що визначає або `normalSet`, або `additionSet`, в залежності від того, який хітсаунд грає
- `hitSound` є `normal`, `whistle`, `finish`, або `clap`
- `index` - це той же `index`, що й вище, за винятком того, що він не пишеться, якщо значенням є `0` чи `1`

Файл звуку завантажується з першої із наступних папок, яка містить файл з відповідною назвою:

- Папка бітмапи, якщо `index` не `0`
- Папка скіну, при цьому `index` прибирається
- Ресурси osu! за замовчуванням, при цьому `index` прибирається

При наданні `filename` додаткові звуки не програватимуться, замість них гратиме цей файл у папці бітмапи.

### Круги

Круги не мають додаткових параметрів `objectParams`.

### Слайдери

*Синтаксис слайдеру:* `x,y,time,type,hitSound,curveType|curvePoints,slides,length,edgeSounds,edgeSets,hitSample`

- **`curveType` (Літера):** Тип кривої, що використовується для побудови цього слайдера (`B` = безьє, `C` = доцентровий кетмелл-ром, `L` = лінійна, `P` = ідеальне коло)
- **`curvePoints` (Список строк, розділений вертикальною лінією):** Опорні точки, що використовуються для побудови слайдера. Кожна точка має формат `x:y`.
- **`slides` (Integer):** Скільки разів гравець повинен слідувати за кривою слайдера туди й назад, перш ніж слайдер буде закінчено. Це також можна інтерпретувати як кількість повторів плюс один.
- **`length` (Decimal):** Візуальна довжина слайдера в [osu!-пікселях](/wiki/Client/Beatmap_editor/osu!_pixel).
- **`edgeSounds` (Список цілих чисел, розділений вертикальною лінією):** Хітсаунди, що відтворюються при попаданні по краю кривої слайдера. Перший звук - той, що програється під час першого натискання на слайдер, а останній – звук, який відтворюється при закінченні слайдера.
- **`edgeSets` (Список строк, розділений вертикальною лінією):** Набори семплів, що використовуються для `edgeSounds`. Кожен набір має формат `normalSet:additionSet` з таким самим значенням, як і в [розділі про хітсаунди](#хітсаунди).

#### Криві для слайдера

При побудові кривих для слайдера `x` та `y` використовуються для першої точки, а `curvePoints` постачає всі інші.

Є чотири типи кривих для слайдера в osu!:

- **Безьє (B):** [Криві Безьє](https://uk.wikipedia.org/wiki/%D0%9A%D1%80%D0%B8%D0%B2%D0%B0_%D0%91%D0%B5%D0%B7%D1%8C%D1%94) довільного ступеня можуть бути зроблені. Декілька кривих Безьє можуть бути об'єднані в один слайдер за допомогою повторення їх точок перетину.
- **Доцентровий кетмелл-ром (C):** [Криві Кетмелла](https://en.wikipedia.org/wiki/Centripetal_Catmull–Rom_spline) є інтерполяційною альтернативою кривим Безьє. Сьогодні вони рідко використовуються через відсутність візуальної привабливості.
- **Лінійна (L):** Ці криві утворюють прямий шлях між усіма своїми точками.
- **Ідеальне коло (P):** Криві ідеального кола обмежені трьома точками (включно з положенням об’єкта), які визначають межу кола. Використання більше трьох точок призведе до зміни типу кривої на Безьє.

Якщо `length` слайдеру є довшою за визначену криву, слайдер буде продовжуватись, поки не досягне цільової довжини:

- Для Безьє, Кетмелла й лінійної кривих продовження буде прямою лінією з кінця кривої.
- Для кривих ідеального кола це продовжуватиме дугу кола.

*Зауважте: `length` слайдера може бути використана для визначення часу, необхідного для закінчення слайдера. `length / (SliderMultiplier * 100 * SV) * beatLength` вказує, скільки мілісекунд потрібно для завершення одного слайда слайдера (де `SV` - це коефіцієнт швидкості слайдера, який задається діючою успадкованою точкою таймінгу, або `1`, якщо такої немає).*

#### Хітсаунди слайдерів

Окрім крайових хітсаундів, слайдери також мають постійний хітсаунд весь час, поки гравець в зоні слідуючого кола слайдера. Звуковий файл зациклюється весь той час, поки він активний.

Цей хітсаунд використовує властивості `hitSound` і `hitSample` об'єкта, але підтримуються тільки звичайний та whistle звуки. Його назва файлу має вигляд `<sampleSet>-slider<hitSound><index>.wav`, де `hitSound` - це або `slide` для звичайного звуку, або `whistle` для whistle.

### Спінери

*Синтаксис спінера:* `x,y,time,type,hitSound,endTime,hitSample`

- **`endTime` (Integer):** Час закінчення спінера в мілісекундах з початку аудіо бітмапи.
- `x` та `y` не впливають на спінери. Вони за замовчуванням вказують на центр ігрового поля, тобто рівні `256,192`.

### Довгі ноти (лише в osu!mania)

*Синтаксис довгої ноти:* `x,y,time,type,hitSound,endTime:hitSample`

- **`endTime` (Integer):** Час закінчення довгої ноти в мілісекундах з початку аудіо бітмапи.
- `x` визначає індекс колонки, в якій буде довга нота. Вираховується це за формулою `floor(x * columnCount / 512)` і приймає значення між `0` та `columnCount - 1`.
- `y` не впливає на довгі ноти. За замовчуванням вказує не центр ігрового поля, тобто рівний `192`.

### Приклади

```
256,192,11000,21,2
256,192,11200,8,12,12000,3:0:0:80:
100,100,12600,6,1,B|200:200|250:200|250:200|300:150,2,310.123,2|1|2,0:0|0:0|0:2,0:0:0:0:
```

Перший об'єкт - це круг:

- В центрі екрану
- На 11 секундах
- Починає нове комбо і пропускає один додатковий колір комбо
- Має хітсаунд whistle

Другий об'єкт - це спінер:

- На 11.2 секундах
- Закінчується на 12 секундах
- Має хітсаунди finish і clap, що грають з гучністю 80%
- Має звичайний хітсаунд, що грає з набором drum з гучністю 80%

Третій об'єкт - це слайдер:

- В позиції (100,100)
- На 12.6 секундах
- Починає нове комбо
- Зі змішаною кривою Безьє, де першими контрольними точками кривої є (100,100), (200,200) та (250,200), і другими контрольними точками кривої є (250,200) та (300,150). Контрольні точки, що повторюються, позначають [червону опорну точку](/wiki/Gameplay/Hit_object/Slider/Slider_anchor).
- Повторюється один раз
- Має довжину в 310.123 osu!-пікселів
- Має хітсаунд whistle на початку і хітсаунд whistle з набором soft у кінці

### osu!taiko

Об'єкти osu!taiko використовують лише `time` для визначення, як вони будуть розміщені на ігровому полі, тому `x` та `y` ігноруються. Так само і для кривих слайдерів єдиною значущою частиною є `length`; `curveType` і `curvePoints` актуальні лише при відкритті карти в редакторі. Кольори комбо і нові комбо ігноруються, а хітсаунди, що використовуються, є специфічними для цього режиму.

- Круги з хітсаундами whistle або clap стають катами, а всі інші круги - донами. Додавання хітсаунду finish перетворює їх на великі версії.
- Слайдери стають драмролами.
- Спінери стають денден нотами.

### osu!catch

Поле гри osu!catch використовує тільки вісь x, отже, `y` не грає ролі. Криві слайдера можуть використовувати вертикальний простір для досягнення горизонтального прискорення, коли вони сплющені до одновимірного ігрового поля.

- Круги стають фруктами.
- Слайдери стають потоками соку з фруктами на кожному краю.
- Спінери стають дощами з бананів

### osu!mania

Так само, як і в osu!catch, об'єкти в osu!mania не використовують `y`. `x` використовується для визначення колонки; дивіться [розділ про довгі ноти](#довгі-ноти-(лише-в-osu!mania)).

- Круги стають звичайними нотами.
- Слайдери і спінери в osu!mania не використовуються.
