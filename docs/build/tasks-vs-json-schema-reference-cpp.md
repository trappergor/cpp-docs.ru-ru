---
title: Справочник по схеме tasks.vs.json (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: a2aea1b64d5a6c62604c680bf1a4a26478b7b52a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844994"
---
# <a name="tasksvsjson-schema-reference-c"></a>Справочник по схеме tasks.vs.json (C++)

Чтобы сообщить Visual Studio о том, как создать исходный код в проекте "Открытая папка", добавьте файл *tasks.vs.json*. В нем можно определить любую произвольную задачу, а затем вызывать ее из контекстного меню **обозревателя решений**. Проекты CMake не используют этот файл, так как все команды сборки указываются в файле *CMakeLists.txt*. Для систем сборки, отличных от CMake, в файле *tasks.vs.json* можно задавать команды сборки и вызывать скрипты сборки. Общие сведения об использовании *tasks.vs.json* см. в разделе [Настройка задач сборки и отладки для режима разработки "Открытая папка"](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).

Задача имеет свойство `type`, которое может иметь одно из четырех значений: `default`, `launch`, `remote` или `msbuild`. В большинстве задач следует использовать `launch`, если только не требуется удаленное подключение.

## <a name="default-properties"></a>Свойства по умолчанию

Свойства по умолчанию доступны для всех типов задач:

|Свойство|Тип|Описание|
|-|-|-|
|`taskLabel`|string| (Обязательно). Задает метку задачи, используемую в пользовательском интерфейсе.|
|`appliesTo`|string| (Обязательно). Указывает, для каких файлов можно выполнить эту команду. Поддерживается использование подстановочных знаков, например: " *", "* .cpp", "/*.txt"|
|`contextType`|string| Допустимые значения: "custom", "build", "clean", "rebuild". Определяет, где в контекстном меню будет отображаться задача. По умолчанию имеет значение "custom".|
|`output`|string| Указывает выходной тег для задачи.|
|`inheritEnvironments`|array| Задает набор переменных среды, унаследованных из нескольких источников. Можно определить переменные в файлах, например *CMakeSettings.json* или *CppProperties.json*, и сделать их доступными для контекста задачи. **Visual Studio 16.4**. Укажите переменные среды для каждой задачи с помощью синтаксиса `env.VARIABLE_NAME`. Чтобы отменить переменную, задайте для нее значение NULL.|
|`passEnvVars`|boolean| Указывает, следует ли включать дополнительные переменные среды в контекст задачи. Эти переменные отличаются от тех, которые определены с помощью свойства `envVars`. Значение по умолчанию: "true".|

## <a name="launch-properties"></a>Свойства запуска

Если тип задачи — `launch`, доступны следующие свойства:

|Свойство|Тип|Описание|
|-|-|-|
|`command`|string| Указывает полный путь к запускаемому процессу или скрипту.|
|`args`|array| Задает разделенный запятыми список аргументов, передаваемых команде.|
|`launchOption`|string| Допустимые значения: "None", "ContinueOnError","IgnoreError". Указывает, как продолжить выполнение команды при возникновении ошибок.|
|`workingDirectory`|string| Указывает каталог, в котором будет выполняться команда. По умолчанию используется текущая рабочая папка проекта.|
|`customLaunchCommand`|string| Задает глобальную настройку области, применяемую перед выполнением команды. Полезно для задания переменных среды, таких как %PATH%.|
|`customLaunchCommandArgs`|string| Указывает аргументы для customLaunchCommand. (Требует `customLaunchCommand`.)|
 `env`| Указывает список значений ключа для настраиваемых переменных среды. Например, "myEnv": "myVal"|
|`commands`|array| Указывает список команд для вызова по порядку.|

### <a name="example"></a>Пример

Следующие задачи вызывают *make.exe*, когда в папке содержится файл makefile, а среда `Mingw64` определена в файле *CppProperties.json*, как указано в [справочнике по схеме CppProperties.json](cppproperties-schema-reference.md#user_defined_environments):

```json
 {
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "gcc make",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make"
    },
    {
      "taskLabel": "gcc clean",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make",
      "args": ["clean"]
    }
  ]
}
```

Эти задачи можно вызвать из контекстного меню, если щелкнуть правой кнопкой мыши файл *CPP* в **обозревателе решений**.

## <a name="remote-properties"></a>Удаленные свойства

Удаленные задачи включаются при установке разработки Linux с рабочей нагрузкой C++ и добавлении подключения к удаленному компьютеру с помощью диспетчера подключений Visual Studio. Удаленная задача запускает команды в удаленной системе и также может копировать в нее файлы.

Если тип задачи — `remote`, доступны следующие свойства:

|Свойство|Тип|Описание|
|-|-|-|
|`remoteMachineName`|string|Имя удаленного компьютера. Должно соответствовать имени компьютера в **диспетчере подключений**.|
|`command`|string|Команда для отправки на удаленный компьютер. По умолчанию команды выполняются в каталоге $HOME в удаленной системе.|
|`remoteWorkingDirectory`|string|Текущий рабочий каталог на удаленном компьютере.|
|`localCopyDirectory`|string|Локальный каталог для копирования на удаленный компьютер. По умолчанию используется текущий рабочий каталог.|
|`remoteCopyDirectory`|string|Каталог на удаленном компьютере, в который копируется `localCopyDirectory`.|
|`remoteCopyMethod`|string| Метод, используемый для копирования. Допустимые значения: "none", "sftp", "rsync". Для больших проектов рекомендуется использовать rsync.|
|`remoteCopySourcesOutputVerbosity`|string| Допустимые значения: "Normal","Verbose","Diagnostic".|
|`rsyncCommandArgs`|string|По умолчанию используется значение "-t --delete".|
|`remoteCopyExclusionList`|array|Разделенный запятыми список файлов в `localCopyDirectory`, исключаемых из операций копирования.|

### <a name="example"></a>Пример

Следующая задача появится в контекстном меню при щелчке правой кнопкой мыши файла *Main.cpp* в **обозревателе решений**. Она зависит от удаленного компьютера, который называется `ubuntu` в **диспетчере подключений**. Задача копирует текущую открытую папку в Visual Studio в каталог `sample` на удаленном компьютере, а затем вызывает g++ для сборки программы.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Build",
      "appliesTo": "main.cpp",
      "type": "remote",
      "contextType": "build",
      "command": "g++ main.cpp",
      "remoteMachineName": "ubuntu",
      "remoteCopyDirectory": "~/sample",
      "remoteCopyMethod": "sftp",
      "remoteWorkingDirectory": "~/sample/hello",
      "remoteCopySourcesOutputVerbosity": "Verbose"
    }
  ]
}
```

## <a name="msbuild-properties"></a>свойства MSBuild

Если тип задачи — `msbuild`, доступны следующие свойства:

|Свойство|Тип|Описание|
|-|-|-|
|`verbosity`|string| Указывает выходные значения verbosityAllowed сборки проекта MSBuild: "Quiet", "Minimal", "Normal", "Detailed", "Diagnostic".|
|`toolsVersion`|string| Указывает версию набора инструментов для сборки проекта, например "2.0", "3.5", "4.0", "Current". Значение по умолчанию: "Current".|
|`globalProperties`|object|Указывает список ключевых значений глобальных свойств для передачи в проект, например "Configuration":"Release"|
|`properties`|object| Указывает список "ключ-значение" свойств только дополнительного проекта.|
|`targets`|array| Указывает список целевых объектов для вызова по порядку в проекте. Если значение не указано, используется целевой объект проекта по умолчанию.|
