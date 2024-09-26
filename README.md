# ДЗ по инфраструктуре

## Настройте линтер для соответствия сообщений о коммитах формату conventional commits
- Установлен commitlint и husky, пре-коммит хуками проверяется наименование коммита
## Настройте автоматический запуск проверок в CI для пулл реквестов
## обязательно должны запускаться автотесты + опционально можете подключить линтер для кода
## проверки должны запускаться автоматом на каждый коммит в PR
## результат должен быть виден на странице PR в интерфейсе GitHub
## нужно настроить ограничение на мерж изменений, если проверки не прошли
- Сделал. Разве что lint'ер не устанавливал (опционально)

## Настройте релизный процесс
релиз должен запускаться автоматически при появлении в git нового релизного тега. Считаем тег релизным, если он соответствует маске  v<число>   (например,  v12  )
версия релиза должна соответствовать релизному тегу
- вышеуказанное сделано
должен формироваться changelog по истории коммитов от предыдущего релизного тэга
- пробовал различные варианты в интернете готовых экшенов - пока не получается выдернуть историю коммитов в удобоваримом формате

должна создаваться запись в реестре релизов — считаем, что это issue на GitHub с пометкой RELEASE. Там должна сохраняться вся важная информация: автор и дата релиза (можно взять из тэга), номер версии, changelog


предусмотрите корректную работу скрипта при многократном запуске с тем же тэгом (должна обновляться информация в существующей записи реестра релизов, а не создаваться новая)
должны запускаться проверки, аналогичные PR, а ссылка на результат должна добавляться в реестр релизов
если проверки прошли, приложение должно выкладываться на gh-pages (можете использовать готовый инструмент, например, gh-pages), а запись об этом должна добавляться в реестр релизов
после этого релизный issue можно автоматом закрывать
Автоматизацию можно настроить через GitHub Actions или другой бесплатный аналог
секреты должны храниться защищенно

check