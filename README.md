# ОПИ 3 лабораторная работа
## Вариант _435768_

### Задание
Написать сценарий для утилиты **Apache Ant**, реализующий компиляцию, тестирование и упаковку в jar-архив кода проекта из лабораторной работы №3 по дисциплине "Веб-программирование".

Каждый этап должен быть выделен в отдельный блок сценария; все переменные и константы, используемые в сценарии, должны быть вынесены в отдельный файл параметров; `MANIFEST.MF` должен содержать информацию о версии и о запускаемом классе.

Cценарий должен реализовывать следующие цели (targets):

- [X] **compile** -- компиляция исходных кодов проекта. 
- [X] **build** -- компиляция исходных кодов проекта и их упаковка в исполняемый jar-архив. Компиляцию исходных кодов реализовать посредством вызова цели compile.
- [X] **clean** -- удаление скомпилированных классов проекта и всех временных файлов (если они есть).
- [X] **test** -- запуск junit-тестов проекта. Перед запуском тестов необходимо осуществить сборку проекта (цель build).
- [X] **native2ascii** - преобразование native2ascii для копий файлов локализации (для тестирования сценария все строковые параметры необходимо вынести из классов в файлы локализации).
- [X] **xml** - валидация всех xml-файлов в проекте.
- [X] **doc** - добавление в `MANIFEST.MF` MD5 и SHA-1 файлов проекта, а также генерация и добавление в архив javadoc по всем классам проекта.
- [ ] **music** - воспроизведение музыки по завершению сборки (цель build).
- [ ] **history** - если проект не удаётся скомпилировать (цель compile), загружается предыдущая версия из репозитория svn. Операция повторяется до тех пор, пока проект не удастся собрать, либо не будет получена самая первая ревизия из репозитория. Если такая ревизия найдена, то формируется файл, содержащий результат операции diff для всех файлов, измёненных в ревизии, следующей непосредственно за последней работающей.
- [ ] **diff** - осуществляет проверку состояния рабочей копии, и, если изменения касаются классов, указанных в файле параметров выполняет commit в репозиторий git.
- [ ] **report** - в случае успешного прохождения тестов сохраняет отчет junit в формате xml, добавляет его в репозиторий git и выполняет commit.
- [ ] **alt** - создаёт альтернативную версию программы с измененными именами переменных и классов (используя задание replace/replaceregexp в файлах параметров) и упаковывает её в jar-архив. Для создания jar-архива использует цель build.