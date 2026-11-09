# Stalliongrad Rework — арт второй очереди

Графика для сабмода Equestria at War (HOI4).

## Готово 101 / 101 игровых файлов

[Полный список и статусы](progress.json) · [Техническое задание](art/wave2/batch01/art_spec_wave2.md)

| Пачка | Файлов | Состав |
| --- | --- | --- |
| [01](art/wave2/batch01/) | 9 | 7 leader, 2 adviser |
| [02](art/wave2/batch02/) | 9 | 9 adviser |
| [03](art/wave2/batch03/) | 10 | 10 focus |
| [04](art/wave2/batch04/) | 10 | 10 focus |
| [05](art/wave2/batch05/) | 2 | 2 focus |
| [06](art/wave2/batch06/) | 10 | 10 event |
| [07](art/wave2/batch07/) | 5 | 5 event |
| [08](art/wave2/batch08/) | 10 | 10 focus |
| [09](art/wave2/batch09/) | 5 | 5 focus |
| [10](art/wave2/batch10/) | 10 | 10 event |
| [11](art/wave2/batch11/) | 3 | 3 event |
| [12](art/wave2/batch12/) | 8 | 8 adviser |
| [13](art/wave2/batch13/) | 10 | 10 decision |

## Установка

Скопируйте содержимое `game/` из каждой пачки в папку мода. Регистрацию спрайтов выполняет отдельный скрипт проекта.

В каждой пачке: PNG-мастера, игровые DDS BC3/DXT5 с альфа-каналом без мипмапов, обзорные листы с игровым размером 1:1, `manifest.json`, точные промпты `prompts.json`, `README.txt`. Графика создана встроенным image_gen.
