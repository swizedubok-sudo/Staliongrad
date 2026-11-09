# Stalliongrad Rework — ТЗ на арт, вторая очередь

Сабмод для Equestria at War (HOI4), страна — Сталлионград (STG). Первая очередь (10 иконок фокусов, 7 событий, 1 портрет) уже в игре. Вторая очередь закрывает новые пути: промышленность, мировую революцию, пути Василия, Синистера, Альтидии и Тёмного Крыла.

**Состав:** 37 иконок фокусов, 28 картинок событий, 7 портретов лидеров, 19 портретов советников, 10 заставок категорий решений. Всего 101 файл.
**Приоритет:** **A** — делать первыми (корни и финалы веток, ключевые сцены, все портреты), **B** — потом. Если объём не помещается в одну сессию, сдавай пачками по приоритету A, затем B.

---

## 1. Общие правила

- **Стиль сохраняется из первой очереди.** Ориентиры — существующие `gfx/interface/goals/STG`, `gfx/leaders/STG`, `gfx/event_pictures/event_stg_*` из Equestria at War (Workshop 1826643372) и наша первая очередь (`STG_ogas`, `STG_event_kontingent`, `STG_anarchist_leader_portrait`).
- **Все персонажи — пони** (земные пони, пегасы, единороги), а в отдельных местах грифоны, яки, драконикус — где указано. Никаких людей, человеческих лиц, рук и пальцев. Копыта, короткие морды, пони-уши, четвероногие пропорции.
- **Все персонажи оригинальные.** Не копировать канонических персонажей MLP и реальных исторических лиц — только намёк через роль, одежду и обстановку.
- **Без текста:** никаких надписей, букв, цифр, логотипов, водяных знаков. Даже на плакатах, газетах и часах — только формы без читаемых знаков.
- **Символика:** серп и молот → **молот и подкова**. Звезда — простая красная, без лишних эмблем, если не указано.
- **Отсылки** (советское кино, литература, перестройка) передаются композицией и обстановкой, а не прямым копированием кадров.

## 2. Форматы и сдача

| Тип | Игровой размер | Мастер | Фон | Путь в игре |
| --- | --- | --- | --- | --- |
| Иконка фокуса | 89×80 | 1024×1024 | прозрачный вокруг значка | `game/gfx/interface/goals/STG/<id>.dds` |
| Картинка события | 210×176 | 1050×880 | без прозрачности, в край | `game/gfx/event_pictures/<id>.dds` |
| Портрет лидера | 156×210 | 780×1050 | без прозрачности | `game/gfx/leaders/STG/<id>.dds` |
| Портрет советника | 65×67 | 650×670 | без прозрачности | `game/gfx/interface/ideas/Advisors/STG/<id>.dds` |
| Заставка категории решений | 114×101 | 1140×1010 | без прозрачности | `game/gfx/interface/decisions/<id>.dds` |

- DDS: **BC3/DXT5, с альфой, без мипмапов**. Как в первой очереди.
- Структура архива как в первой очереди: `game/` (DDS), `masters/` (PNG), `preview_*.jpg` (обзорные листы: крупно и в игровом размере), `manifest.json` (id, тип, пути, размеры), `prompts.json` (точные использованные промпты), `README.txt`.
- Имена файлов — строго как `id` в таблицах ниже.
- Регистрацию спрайтов в `interface/*.gfx` делать не нужно — её делает наш скрипт `tools/stage13_art.py`.

## 3. Базовые промпты (подставлять «Central subject» / «Scene» / «Subject»)

**Иконка фокуса:**
> Use case: stylized-concept. One national focus icon for Hearts of Iron IV Equestria at War STG. Match the provided original STG reference sheet closely: a compact circular heraldic badge with a thick GOLDEN WHEAT WREATH encircling the central object, RED ribbon bands wrapping lower sides and a folded RED RIBBON at bottom, dark charcoal steel circular backing. The frame MUST be conspicuous and consistent across all icons, like goal_socialist_science, goal_market and goal_collectivization. Gold ears of wheat, NOT laurel. The central subject stays large and fills the dark round centre, can overlap inner rim slightly. Semi-realistic hand-painted game graphic with aged metal shading, crisp clear silhouette, high contrast, muted red, warm gold/brass and dark steel. Soft upper-left lighting. Readable at 89x80. Centered, outer silhouette has 8% transparent margin. NO text, letters, numbers or watermark, no extra objects. Use hammer and horseshoe rather than hammer and sickle; do not add any emblem unless the central subject asks for it. Square 1024x1024, genuinely transparent outside the complete wreath badge. Central subject: …

**Картинка события:**
> Use case: illustration-story. One event picture for Hearts of Iron IV Equestria at War STG. Reference sheet is visual style only: painted cartoon ponies embedded in a convincing archival documentary scene, short equine muzzles, expressive large eyes, pony ears, quadruped proportions. Period photograph look, sepia or faded desaturated colour as the scene requires, film grain, subtle vignette, clear composition readable at 210x176. Full bleed rectangular landscape aspect 210:176, target 1050x880, no tilted borders or labels. ALL figures are ponies (earth ponies, pegasi, unicorns) unless the scene names another creature, NEVER humans, no fingers. All characters original. No captions, lettering, text, numbers, logos, watermark. Scene: …

**Портрет лидера:**
> Use case: stylized-concept. One original pony leader portrait for Equestria at War STG. Reference sheet is style only: match the Vasya / Darkwing portraits' polished painted cartoon pony anatomy, large expressive eyes, short equine muzzle, soft modeled shading and crisp silhouette. No photorealistic horse, human face, human hands, or copied canon character. Official portrait manner of the era named in the subject, muted colours, plain dark gradient backdrop, no text or frame. Vertical aspect 156:210, target 780x1050. Head and shoulders. Subject: …

**Портрет советника:** как портрет лидера, но
> … small adviser portrait, square-ish aspect 65:67, target 650x670, head and shoulders filling the frame, readable at 65x67, plain dark backdrop. Subject: …

**Заставка категории решений:**
> Use case: illustration-story. One decision category banner picture for Hearts of Iron IV Equestria at War STG, same archival painted style as STG event pictures, ponies only, no humans, no text or numbers. Aspect 114:101, target 1140x1010, clear central motif readable at 114x101, subtle vignette. Scene: …

---

## 4. Иконки фокусов (37)

### Промышленность (6)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_ind_giganto` | A | A colossal blast furnace and factory chimneys towering over a tiny steppe settlement, red glow from the furnace mouth. |
| `STG_gig_two_plus_two` | B | A monumental stepped pyramid ministry building of white concrete with a single huge watching eye-shaped window, searchlights. (Ministry of Plenty, 1984 homage.) |
| `STG_ind_bases` | A | A massive armoured door set into a snowy mountainside, factory light spilling from the gap, pine trees around. |
| `STG_bas_northern_forge` | B | An anvil and hammer inside a rock cavern, sparks flying, horseshoe glowing on the anvil. |
| `STG_ind_quality` | A | A rounded 1960s refrigerator with a small embossed pentagon quality mark on its door. |
| `STG_q_science_towns` | B | Modern laboratory towers among tall northern pines, a small radio dish and a glowing window. |

### Мировая революция (5)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_wr_comintern` | A | A globe-shaped lectern draped with a red banner, three small flags (pony, griffon feather, zebra stripe motifs) planted around it. |
| `STG_wr_coups` | B | A shadowy pegasus silhouette in a grey coat at a telegraph key, a sealed red envelope beside it. |
| `STG_wr_liberation` | A | A landing ship's bow ramp dropping onto a foreign beach with palm-like trees, red pennant on the mast. |
| `STG_wr_doomsday` | A | A plain clock face WITHOUT any numerals, both hands almost at the top, a faint mushroom-cloud silhouette behind it. |
| `STG_wr_world_soviets` | A | A globe with three continents glowing red, a red star orbiting it like a satellite. |

### Путь Василия (7)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_vas_socialist_camp` | A | One large red banner surrounded by five smaller red banners on poles, arranged like a fan. |
| `STG_vas_comecon` | B | Five interlocking brass cogwheels of different sizes forming a ring. |
| `STG_vas_pact` | B | A steel shield with five small red stars in a circle, two crossed rifles behind it. |
| `STG_vas_anadyr` | A | A long missile under a canvas tarpaulin on the deck of a cargo ship at night, sea spray. |
| `STG_vas_projects` | A | A railway line cutting straight through dense taiga toward low mountains, a tent and a red flag beside the rails. |
| `STG_vas_psychiatry` | B | A white hospital door with a small barred window, a hanging straitjacket beside it, cold blue light. |
| `STG_vas_dear_comrade` | A | A dark suit jacket chest completely covered with medals and five golden hero stars. |

### Путь Синистера (7)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_sin_permanent_revolution` | A | A flaming torch whose fire spirals upward in an endless red helix. |
| `STG_sin_labour_armies` | B | A shovel and a rifle crossed, a soldier's greatcoat hanging over them. |
| `STG_sin_armored_train` | A | The front of a 1920s armoured train with a red star on the boiler, steam and searchlight. |
| `STG_sin_bunker` | B | A basement door covered with punk-style paper flyers (no readable text), a hand grenade-shaped red-black badge above it. Original design, not any real party symbol. |
| `STG_sin_equusianism` | A | A stylised continent map silhouette entirely in red, a north star above it. |
| `STG_sin_posadism` | B | A small mushroom cloud on a distant horizon with three glowing round lights hovering in the sky above it. |
| `STG_sin_red_north` | A | A blazing red north star over snowy mountain peaks. |

### Путь Альтидии (6)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_alt_state_and_revolution` | A | An open book and an oil lantern inside a small reed hut by a marsh. |
| `STG_alt_goelro` | A | A single glowing light bulb hanging from a wire above a wooden village cottage. |
| `STG_alt_tenth_congress` | B | Many raised hooves holding red voting cards in a hall, seen from behind. |
| `STG_alt_kitchen_maid` | B | A kitchen ladle crossed with a fountain pen over an official paper with a red seal. |
| `STG_alt_niichavo` | B | A unicorn horn crackling with blue sparks above a laboratory flask and a punched tape. |
| `STG_alt_letter_to_congress` | A | A sealed envelope with a large red wax seal bearing a horseshoe. |

### Путь Тёмного Крыла (6)
| id | Приор. | Central subject |
| --- | --- | --- |
| `STG_dw_process` | A | A heavy door swinging open, warm daylight pouring into a dark office. |
| `STG_dw_glasnost` | A | A megaphone with newspapers flying out of it (no readable text). |
| `STG_dw_archipelago` | B | Barbed wire unwinding and turning into the pages of an open book. |
| `STG_dw_free_elections` | B | A transparent ballot box full of folded papers, several different-coloured ballots on top. |
| `STG_dw_new_thinking` | A | A white dove perched on a missile cut in half. |
| `STG_dw_union_treaty` | A | A golden sun and a red star intertwined above a signed treaty with several wax seals. |

---

## 5. Картинки событий (28)

| id | Приор. | Событие | Scene |
| --- | --- | --- | --- |
| `STG_event_foundation_pit` | A | Промышленность: «Котлован» | An engineer pony with rolled blueprints on a windy frozen steppe, a foreman driving a shovel into the snow, empty horizon. 1930s photo. |
| `STG_event_rewritten_archive` | B | Промышленность: ревизия приписок | A long archive hall, clerks at desks rewriting old reports, a furnace chute swallowing papers. Cold 1930s photo. 1984 homage. |
| `STG_event_comintern_hall` | A | Мировая революция: Северный Коминтерн | A crowded column hall: pony delegates, a griffon docker turning a cap in his talons, a young zebra student taking notes. 1930s photo. |
| `STG_event_white_waste_test` | A | Мировая революция: испытание «Зари» | A unicorn scientist in glasses in a bunker window, a second sun rising over the tundra. Harsh light. |
| `STG_event_midnight` | B | Мировая революция: Полночь | Grey snow falling in summer over a ruined city square, ponies in coats looking up. |
| `STG_event_tanks_spring` | A | Василий: «Танки на улицах» | Tanks with red stars in an old European-style city street, ponies arguing with tank crews, flowers on the tank. 1968 colour photo. |
| `STG_event_granma` | B | Василий: «Гранма» | An overloaded old pleasure yacht at night on a rough sea, bearded pony fighters crowded on deck. |
| `STG_event_blockade` | A | Василий: Карибский кризис | Aerial reconnaissance photo of launch pads on a tropical island, warships on the sea at the edge. 1962 black-and-white. |
| `STG_event_golden_link` | B | Василий: «Золотое звено» | Two Komsomol brigades meeting on railway tracks in the taiga, a brass band, one pony driving a gilded spike. 1984 colour photo. |
| `STG_event_gun_carriage` | A | Василий: похороны вождя | A funeral gun carriage with a coffin crossing a snowy square, honour guard, red-and-black ribbons. 1982 colour photo. |
| `STG_event_tyorkin` | B | Василий: «Василий Тёркин» | A soldier pony reading a front newspaper aloud in a trench, comrades laughing, winter. 1942 photo. |
| `STG_event_stalker` | B | Василий: «Сталкер» | Three ponies walking through flooded abandoned factory halls, greenish light, slow and dreamlike. 1979 film-still look. |
| `STG_event_plenum_debate` | A | Синистер: «Социализм в одной стране?» | A smoky night plenum: one calm pony speaking from notes, another fiery pony standing without notes, a packed hall. 1920s photo. |
| `STG_event_armored_train` | A | Синистер: поезд Предреввоенсовета | An armoured train at a frontline station at dawn, a commissar pony speaking from the platform to soldiers. 1919 photo. |
| `STG_event_kronstadt` | A | Синистер: Кронштадт | Pony soldiers in white camouflage advancing across sea ice toward a fortress and battleships. 1921 photo. |
| `STG_event_villa_by_the_sea` | B | Синистер: «Убийство на вилле у моря» | A quiet study in a seaside villa: typewriter, scattered manuscripts, an open window, an ice axe lying on the floor. No body, no blood. 1940 photo. |
| `STG_event_lights_over_tundra` | B | Синистер: «Огни над тундрой» | Three glowing lights hovering over the tundra at night, a giant hammer-and-horseshoe trodden into the snow below. |
| `STG_event_bunker_action` | B | Синистер: «Да, смерть!» | Young ponies in black coats on a city square throwing paint bags at a ministry building, flyers in the air. 1990s photo look. |
| `STG_event_armored_car_speech` | A | Альтидия: «С броневика» | A mare speaking from an armoured car at a railway station at night, searchlights, a huge crowd. 1917 photo. |
| `STG_event_black_magic_seance` | A | Альтидия: «Сеанс чёрной магии» | A theatre stage: an original draconequus magician in a checked jacket with a large cat and a lanky companion, banknotes falling from the ceiling over the audience. 1930s photo. |
| `STG_event_heart_of_a_dog` | B | Альтидия: «Собачье сердце» | A professor pony in a rich apartment arguing with a house committee in leather jackets, a scruffy diamond dog in a suit in the doorway. 1920s photo. |
| `STG_event_funeral_train` | A | Альтидия: «Траурный поезд» | A funeral train in a snowstorm, peasant ponies standing bareheaded along the tracks. 1924 photo. |
| `STG_event_ilyich_lamp` | B | Альтидия: «Лампочка Ильича» | Old peasant ponies in a log cottage staring at a single electric bulb under the ceiling, a stove behind them. 1920s photo. |
| `STG_event_vzglyad` | B | Тёмное Крыло: «Взгляд» | A TV studio set like a kitchen, young presenters in sweaters interviewing a sweating official, a rock band behind them. 1988 colour photo. |
| `STG_event_swan_lake` | A | Тёмное Крыло: «Лебединое озеро» | A dim apartment, a family of ponies frozen in front of a television showing ballet dancers. 1991 colour photo. |
| `STG_event_barricades` | A | Тёмное Крыло: баррикады | A crowd at a parliament building, trolleybuses as barricades, a pony standing on a tank reading an appeal. 1991 colour photo. |
| `STG_event_union_treaty` | B | Тёмное Крыло: Новый союзный договор | Leaders of several republics signing a treaty at a long table in a country residence, a photographer. 1991 colour photo. |
| `STG_event_orbit_handshake` | A | Тёмное Крыло: «Рукопожатие на орбите» | Inside a docked spacecraft hatch: a pegasus cosmonaut and a unicorn astronaut shaking hooves, Earth-like planet in the window. 1975 colour photo. |

---

## 6. Портреты лидеров (7, все A)

Портреты эпохи, по которой правит персонаж. Все — оригинальные пони.

| id | Кто | Subject |
| --- | --- | --- |
| `STG_succ_chekist` | Юрий Твердокопытов, председатель органов, преемник Василия (Андропов) | An elderly earth pony stallion, grey coat, thinning dark mane combed back, rimless glasses, cold intelligent eyes, dark suit and tie. Early 1980s official portrait. |
| `STG_succ_apparatchik` | Константин Черноплёт, аппаратчик (Черненко) | A very old, frail earth pony stallion, pale grey coat, white mane, tired puffy eyes, heavy dark coat with medals. Early 1980s official portrait. |
| `STG_succ_technocrat` | Нина Счётова, технократ, ОГАС | A unicorn mare in her 40s, light blue coat, short neat dark mane, thoughtful sharp eyes, white blouse and dark jacket, small slide rule pin. 1980s portrait. |
| `STG_succ_reformer` | Михаил Ставров, молодой реформатор (Горбачёв) | A middle-aged earth pony stallion, warm brown coat, high forehead with a faint birthmark-like coat marking, energetic open smile, modern suit. Mid-1980s portrait. |
| `STG_alt_succ_sovetova` | Мария Советова, председатель Совнаркома, преемница Альтидии | A pegasus mare in her 30s, soft cream coat, red mane in a bun, steady eyes, plain dark dress with a red armband. 1920s portrait. |
| `STG_alt_succ_lyubimov` | Николай Любимов, «любимец партии», НЭП (Бухарин) | A young earth pony stallion, sandy coat, small goatee-like chin tuft, lively smiling eyes, Russian-style tunic shirt. 1920s portrait. |
| `STG_alt_succ_krzhinsky` | Глеб Кржинский, инженер ГОЭЛРО (Кржижановский) | A unicorn stallion in his 50s, grey coat, neat beard-like muzzle tuft, pince-nez, engineer's jacket, electric arc faintly around his horn. 1920s portrait. |

## 7. Портреты советников (19)

Любимов и Кржинский из таблицы выше нужны ещё и как советники — в размере советника (A). Остальные:

| id | Путь | Кто | Приор. | Subject |
| --- | --- | --- | --- | --- |
| `STG_alt_succ_lyubimov` (советник) | Альтидия | см. выше | A | Same character as the leader portrait, adviser framing. |
| `STG_alt_succ_krzhinsky` (советник) | Альтидия | см. выше | A | Same character as the leader portrait, adviser framing. |
| `STG_adv_planova` | Василий | Алевтина Планова, председатель Госплана (Косыгин) | A | Earth pony mare in her 50s, grey-brown coat, severe bun, reading glasses, dark suit, folder of charts. |
| `STG_adv_serogriv` | Василий | Михаил Серогрив, серый кардинал (Суслов) | A | Gaunt elderly earth pony stallion, pale grey coat, grey mane, thick glasses, grey suit, ascetic expression. |
| `STG_adv_chief_designer` | Василий | Главный конструктор (Королёв) | A | Stocky pegasus stallion in his 50s, dark coat, heavy brows, determined eyes, leather jacket, rocket blueprint behind. |
| `STG_adv_snezhneva` | Василий | профессор Снежнева, главный психиатр | B | Unicorn mare in her 60s, white coat, white lab coat, cold polite smile, steel-rimmed glasses. |
| `STG_adv_vekhov` | Синистер | Николай Вехов, философ «Смены вех» (Устрялов) | B | Earth pony stallion, émigré professor, tweed coat, neat moustache-like muzzle marking, pensive. 1920s. |
| `STG_adv_granatov` | Синистер | Эдди Гранатов, поэт-провокатор (Лимонов) | A | Wiry earth pony stallion with round glasses, spiky dark mane, black leather jacket, provocative grin. 1990s look. |
| `STG_adv_soren` | Синистер | Жорж Сорен, философ насилия и мифа (Сорель) | A | An older GRIFFON (not a pony), white head feathers, beard-like chin feathers, pince-nez, 1900s French-style coat. |
| `STG_adv_glubokiy` | Синистер | Михаил Глубокий, красный маршал (Тухачевский) | B | Handsome earth pony stallion in his 40s, dark coat, marshal's uniform with collar diamonds, confident gaze. 1930s. |
| `STG_adv_posadova` | Синистер | товарищ Посадова, теоретик небесных явлений (Посадас) | A | Unicorn mare in her 50s, wild silver mane, intense eyes, 1960s suit, a faint starry glow behind her. |
| `STG_adv_kollontaeva` | Альтидия | Александра Коллонтаева, Рабочая оппозиция (Коллонтай) | B | Elegant pegasus mare in her 40s, dark coat, wavy mane, fur stole over a plain dress, confident smile. 1920s. |
| `STG_adv_lunacharov` | Альтидия | Анатолий Луначаров, нарком просвещения (Луначарский) | B | Unicorn stallion, pince-nez, small goatee-like tuft, scholarly jacket, book in magic grip. 1920s. |
| `STG_adv_zheleznyi` | Альтидия | Феликс Железный, председатель ВЧК (Дзержинский) | A | Thin earth pony stallion, gaunt face, pointed beard-like tuft, burning eyes, plain military tunic. 1920s. |
| `STG_adv_yakovtsev` | Тёмное Крыло | Александр Яковцев, архитектор перестройки (Яковлев) | A | Heavy-set elderly earth pony stallion, bald-looking pale crown, thick glasses, kind tired eyes, grey suit. 1980s. |
| `STG_adv_shevardin` | Тёмное Крыло | Эдуард Шевардин, министр нового мышления (Шеварднадзе) | B | Earth pony stallion with a full silver mane, warm smile, diplomatic suit. 1980s. |
| `STG_adv_korotkov` | Тёмное Крыло | Виталий Коротков, редактор «Огонька» (Коротич) | B | Lively earth pony stallion in his 50s, short beard-like tuft, sweater over a shirt, stack of magazines. 1980s. |
| `STG_adv_shatalov` | Тёмное Крыло | Станислав Шаталов, «500 дней» (Шаталин) | B | Unicorn stallion economist in his 50s, glasses, cardigan, charts glowing faintly in his magic. 1990. |
| `STG_adv_konzansky` | Тёмное Крыло | Борис Конзанский, радикальный популист (Ельцин) | A | Big earth pony stallion with a white swept mane, strong jaw, defiant look, open coat. 1991. |

## 8. Заставки категорий решений (10, все B)

| id | Категория | Scene |
| --- | --- | --- |
| `STG_cat_mega` | Великие стройки | A giant construction site with cranes and a half-built furnace at sunset. |
| `STG_cat_bases` | Северные базы | A hidden factory entrance in a snowy pine forest, trucks driving inside. |
| `STG_cat_quality` | Товары народу | A department store counter with refrigerators and a queue of smiling ponies. |
| `STG_cat_world_revolution` | Экспорт революции | A world map on a war-room table with red pins on two foreign continents. |
| `STG_cat_socialist_camp` | Социалистический лагерь | Leaders of fraternal countries on a reviewing stand, red flags of different designs. |
| `STG_cat_developed_socialism` | Развитой социализм | A long new railway bridge over a northern river, Komsomol banners. |
| `STG_cat_fervor` | Перманентная революция | A night rally with torches and red flags, a speaker on a high platform. |
| `STG_cat_altidiya_economy` | Хозяйство Альтидии | A busy NEP-era market square with carts of grain and a cooperative shop. |
| `STG_cat_reform_tempo` | Темп реформ | A crowd reading newspapers posted on a street stand, 1980s. |
| `STG_cat_sun_and_star` | Солнце и Звезда | A northern and an Equestrian flag side by side over a joint space launch pad. |

---

## 9. Проверка перед сдачей

- Все размеры и форматы — как в разделе 2, имена — как `id`.
- В превью видно игровой размер: иконка читается в 89×80, портрет советника — в 65×67.
- Ни одного человека, человеческой руки, текста или цифры.
- Рамка иконок одинакова у всех: золотые колосья, красные ленты, тёмный стальной круг.
- `manifest.json` и `prompts.json` заполнены для каждого файла.
