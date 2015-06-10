#### [hhFiller](https://greasyfork.org/ru/scripts/10338-hhfiller) - юзерскрипт для вставки шаблона письма ответа на вакансию, работающий на [Headhunter](http://hh.ru), [moikrug](http://moikrug.ru)

* Шаблон вначале предлагается через попап с полем ввода ввести в память браузера при первом заходе на каждый обслуживаемый сайт (рис.1). Его же можно внести непосредственно в код скрипта в поле letterTmpl.

* Скрипт добавляет выделенный текст в конец письма как ответ на требования по вакансии, с добавлением слов "да" в конце каждой строки, для дальнейшего ручного форматирования (рис.2). Выделение можно сменять "на лету", стирая выбранную ранее часть письма.

* Обновление шаблона при очистке поля ввода.

* Устанавливается во всех браузерах. Для Хрома - поместить рядом со скриптом файл manifest.json с содержанием
```
{
   "content_scripts": [ {
      "exclude_globs": [  ],
      "exclude_matches": [  ],
      "include_globs": [
		  "http://hh.ru/*", "https://moikrug.ru/*"  ],
      "js": [ "hhfiller.user.js" ],
      "matches": [ "http://*/*", "https://*/*" ],
      "run_at": "document_idle"
   } ],
   "converted_from_user_script": true,
   "description": "Заполнить отклик на вакансию на hh.ru с помощью шаблона",
   "name": "hhFiller",
   "version": "2.2015.6.10",
   "manifest_version": 2
}
```
и устанавливать как "распакованное расширение" в режиме разработчика (chrome://extensions/).

* Изменять шаблон - удалением прежнего командой "localStorage.tmpl ='';" из консоли браузера (открывается по F12).

* Статья про скрипт: [Свой шаблон отклика-письма на HeadHunter (и moikrug) без Copy-Paste](http://habrahabr.ru/post/259881/)

* Github: https://github.com/spmbt/hhFiller

* Скриншоты:
    * ![Заполнить шаблон вначале / Fill template in first view](img/hhFiller-FillTemplate-20150609.png)
    * ![Автоввод выделенного текста в конец шаблона / Auto insert selected text in the end of template](img/hhFiller-selReqs-hh-20150610.png)
    * ![Запрос подтверждения на вставку на moikrug / Confirm after select text in site moikrug.ru](img/hhFiller-selectReqs-20150610.png)

============[en]==============

Fill response post for vacation in hh.ru and moikrug.ru by template (russian headhunter sites).

* Insert template (fig.1)
* Add selected text to end of letter and formatting it (fig.2)
* Refresh template if clear input area
* Crossbrowser design. For Chrome it need for manifest.json
* For editing of template remove previous one by command "localStorage.tmpl ='';" in console (opened by F12).
* Article (ru) about it: [Own template of response letter in HeadHunter.ru (and moikrug.ru) w/o Copy-Paste](http://habrahabr.ru/post/259881/)
* Github: https://github.com/spmbt/hhFiller