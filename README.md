### Установка
> Установить https://brew.sh/index_ru

> Установить Ruby 2.2 или выше https://gorails.com/setup/osx/10.14-mojave

> Выполнить `gem install generamba`

### Интеграция в проект

> Изменить project format на "Xcode 8.0-compatible"

> В файле "project.pbxproj" удалить строки `inputFileListPaths = ();` `outputFileListPaths = ();`

> Выполнить `generamba setup`

> Открыть 'Rambafile' добавить строки

```
### Templates
catalogs:
- 'git@gitlab.sequenia.com:templates/TemplatesIOS.git'`
```
> Проверить пути

```
# The file path for new modules
project_file_path: PROJECT_NAME/Modules

# The Xcode group path to new modules
project_group_path: PROJECT_NAME/Modules
```

> Выполнить `generamba template install`

### Установка шаблона
> Выполнить `generamba gen MODULE_NAME TEMPLATE_NAME`
