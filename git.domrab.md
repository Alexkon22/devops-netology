## Домашнее задание на тему: «Инструменты Git» Кононенко Александр 
---




  <details><summary><b> Текст Задания.</b> (нажмите, чтобы раскрыть)</summary>
<br>

В клонированном репозитории:

* Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
* Ответьте на вопросы.
* Какому тегу соответствует коммит 85024d3?
* Сколько родителей у коммита b8d720? Напишите их хеши.
* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.
* Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так: func providerSource(...) (вместо троеточия перечислены аргументы).
* Найдите все коммиты, в которых была изменена функция globalPluginDirs.
* Кто автор функции synchronizedWriters?
* В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.

</details>


## Решение 

  <details><summary><b> Текст Решения.</b> (нажмите, чтобы раскрыть)</summary>
<br>

  **Вопрос Первый** 
* Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
 
 * **Результат получен Командой**
    *   `git show aefea`


Вывод:
 * Хеш: `aefead2207ef7e2aa5dc81a34aedf0cad4c32545`
 * Комментарий: `Update CHANGELOG.md`
---


**Вопрос Второй**

* Какому тегу соответствует коммит 85024d3?

*  **Результат получен Командой**
    * `git tag --points-at 85024d3`

 Вывод:
 Тег соответствия **v0.12.23**

 ---
**Вопрос Третий**
 
 * Сколько родителей у коммита b8d720? Напишите их хеши.

 * **Результат получен Командой** 
   *  `git show --format=%P b8d720`

   Вывод
   Два Родителя

   * `56cd7859e05c36c06b56d013b55a252d0bb7e158`
   * `9ea88f22fc6269854151c571162c5bcf958bee2b`
  ---     

 **Вопрос Четвертый**
 
* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.

* **Результат Получен Командой**
  *  `git log v0.12.23..v0.12.24 --oneline`

 Вывод:
Перечисление Хешей и Комментариев 

* 33ff1c03bb (tag: v0.12.24) v0.12.24
* b14b74c493 [Website] vmc provider links
* 3f235065b9 Update CHANGELOG.md
* 6ae64e247b registry: Fix panic when server is unreachable
* 5c619ca1ba website: Remove links to the getting started guide's old location
* 06275647e2 Update CHANGELOG.md
* d5f9411f51 command: Fix bug when using terraform login on Windows
* 4b6d06cc5d Update CHANGELOG.md
* dd01a35078 Update CHANGELOG.md
*225466bc3e Cleanup after v0.12.23 release
---

**Вопрос Пятый**
* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит
    * так: `func providerSource(...)` (вместо троеточия перечислены аргументы).
 
* **Результат Получен Командой**
  * `git log -S "func providerSource" --oneline`


* Вывод:
  функция `func providerSource(...)`
    * была создана в коммите **8c928e8358**
  ---

**Вопрос Шестой**
* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`

* **Результат Получен Командой**
  * `git log -L :globalPluginDirs:plugins.go v0.12.23 --oneline --no-patch`


* Вывод
* 78b1220558 Remove config.go and update things using its aliases
* 52dbf94834 keep .terraform.d/plugins for discovery
* 41ab0aef7a Add missing OS_ARCH dir to global plugin paths
* 66ebff90cd move some more plugin search path logic to command
* 8364383c35 Push plugin discovery down into command package

  ---


  **Вопрос Седьмой**
* Кто автор функции `synchronizedWriters`

* **Результат Получен Командой**
  * `git log -S "synchronizedWriters" --format="%h | %an <%ae> | %s" --no-patch`

 * Вывод 

 **Автор Коммита**  
* **Martin Atkins** `<mart@degeneration.co.uk>`, 

  * Коммит `5ac311e2a9` — `main: synchronize writes to VT100-faker on Windows`.

  
