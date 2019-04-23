---
title: Настройка параметров сборки CMake в Visual Studio
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 4864e094ab967a563b153fa79fd0bf5c375f40f7
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124893"
---
# <a name="customize-cmake-build-settings"></a>Настройка параметров сборки CMake

Visual Studio предоставляет несколько конфигураций CMake, которые определяют, как вызывается CMake.exe для создания кэша CMake для данного проекта. Чтобы добавить новую конфигурацию, щелкните раскрывающийся список конфигурации на панели инструментов и выберите **Управление конфигурациями**.

   ![Управление конфигурациями CMake](media/cmake-manage-configurations.png)

Можно выбрать из списка стандартных конфигураций:

   ![Предопределенные конфигурации CMake](media/cmake-configurations.png)

При первом выборе конфигурации Visual Studio создает файл `CMakeSettings.json` в корневой папке проекта. Этот файл используется для повторного создания файла кэша CMake, например после операции **Очистить**. 

Чтобы добавить дополнительную конфигурацию, щелкните правой кнопкой мыши `CMakeSettings.json` и выберите **Добавить конфигурацию**. 

   ![Добавление конфигурации CMake](media/cmake-add-configuration.png "Добавление конфигурации CMake")

JSON IntelliSense помогает изменить файл `CMakeSettings.json`:

   ![JSON IntelliSense CMake](media/cmake-json-intellisense.png "JSON IntelliSense CMake")

Можно также изменить файл с помощью **редактора параметров CMake**. Щелкните правой кнопкой мыши `CMakeSettings.json` в **обозревателе решений** и выберите **Изменить параметры CMake**. Или выберите **Управление конфигурациями** из раскрывающегося списка конфигурации в верхней части окна редактора. 

Вы также можете напрямую изменить `CMakeSettings.json`, чтобы создавать пользовательские конфигурации. Ниже приведен пример конфигурации, который можно использовать в качестве отправной точки:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

- **name**: имя, которое отображается в раскрывающемся списке конфигурации C++. Макрос `${name}` позволяет использовать это значение при создании других значений свойств, например путей. Пример см. в определении **buildRoot** в `CMakeSettings.json`.

- **generator**: сопоставляется с параметром **-G** в CMake и задает используемый генератор. Это свойство можно также использовать как макрос `${generator}`, чтобы задать другие значения свойств. Сейчас Visual Studio поддерживает следующие генераторы CMake:

  - Ninja
  - Visual Studio 14 2015
  - Visual Studio 14 2015 ARM
  - Visual Studio 14 2015 Win64
  - Visual Studio 15 2017
  - Visual Studio 15 2017 ARM
  - Visual Studio 15 2017 Win64

  Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно велеть CMake создать проект Visual Studio.

  Чтобы указать генератор Visual Studio, откройте `CMakeSettings.json` в главном меню, выбрав **CMake | Изменить параметры CMake**. Удалите слово Ninja и введите букву V. Это активирует IntelliSense, позволяя выбрать нужный генератор.

  Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку в файле `CMakeSettings.json`, можно указать дополнительные [аргументы командной строки MSBuild](../build/reference/msbuild-visual-cpp-overview.md) для передачи в систему сборки через свойство `buildCommandArgs`:
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot**: сопоставляется с параметром **-DCMAKE_BINARY_DIR** и указывает, где будет создан кэш CMake. Если папка не существует, она будет создана.

- **variables**: содержит пару имя-значение для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_*. Если инструкции сборки проекта CMake указывают добавление каких-либо переменных непосредственно в файл кэша CMake, рекомендуется вместо этого добавить их сюда. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

Обратите внимание, что, если не определить `"type"`, тип «STRING» предполагается, что будет по умолчанию.

- **cmakeCommandArgs**: указывает любые дополнительные параметры, которые нужно передать в CMake.exe.

- **configurationType**: определяет тип конфигурации сборки для выбранного генератора. Сейчас поддерживаются значения Debug, MinSizeRel, Release и RelWithDebInfo.

- **ctestCommandArgs**: указывает дополнительные параметры, передаваемые в CTest при выполнении тестов.

- **buildCommandArgs**: указывает дополнительные параметры, передаваемые базовой системе сборки. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки.

Дополнительные параметры доступны для проектов CMake Linux. См. раздел [Настройка проекта CMake Linux](../linux/cmake-linux-project.md).

## <a name="environment-variables"></a>Переменные среды

 `CMakeSettings.json` также поддерживает использование переменных среды в любом из указанных выше свойств. Для расширения переменной среды %FOO% используется синтаксис `${env.FOO}`.
Вы также можете обращаться ко встроенным макросам внутри этого файла:

- `${workspaceRoot}` — предоставляет полный путь для папки рабочей области.
- `${workspaceHash}` — хэш расположения рабочей области; удобен для создания уникального идентификатора для текущей рабочей области (например, для использования в путях папок).
- `${projectFile}` — полный путь к корневому файлу CMakeLists.txt.
- `${projectDir}` — полный путь к папке корневого файла CMakeLists.txt.
- `${thisFile}` — полный путь к файлу `CMakeSettings.json`.
- `${name}` — имя конфигурации.
- `${generator}` — имя генератора CMake, используемого в этой конфигурации.

## <a name="ninja-command-line-arguments"></a>Аргументы командной строки Ninja

Если целевые объекты не заданы, создает целевой объект default (см. руководство).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Параметр|Описание|
|--------------|------------|
| --version  | Вывод версии Ninja ("1.7.1")|
|   -C DIR   | Переход в каталог DIR перед выполнением других действий|
|   -f FILE  | Указание файла входных данных для сборки (по умолчанию используется build.ninja)|
|   -j N     | Параллельное выполнение N заданий (по умолчанию 14, в зависимости от доступных ЦП)|
|   -k N     | Продолжение выполнения для сбоя N заданий (по умолчанию 1)|
|   -l N     | Запрет на запуск новых заданий, если средняя нагрузка выше N|
|   -n       | Пробный запуск (команды не выполняются, но считаются успешно выполненными)|
|   -v       | Отображение всех командных строк во время сборки|
|   -d MODE  | Включение отладки (используйте список -d для указания режимов)|
|   -t TOOL  | Запуск подчиненного инструмента (используйте список -t для указания подчиненных инструментов); Завершает параметров верхнего уровня; Дополнительные флаги передаются в средство|
|   -w FLAG  | Настройка предупреждений (используйте список -w для указания предупреждений)|

## <a name="inherited-environments"></a>Унаследованные среды

 `CMakeSettings.json` поддерживает унаследованные среды. Эта функция позволяет: (1) наследовать среды по умолчанию; и (2) создавать пользовательские переменные среды, которые передаются CMake.exe при запуске.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Приведенный выше пример аналогичен запуску **Командной строки разработчика для VS 2017** с аргументами **-arch=amd64 -host_arch=amd64**.

В следующей таблице показаны значения по умолчанию:

|Имя контекста|Описание|
|-----------|-----------------|
|vsdev|Среда Visual Studio по умолчанию|
|msvc_x86|Компиляция для x86 с помощью средств x86|
|msvc_arm| Компиляция для ARM с помощью средств x86|
|msvc_arm64|Компиляция для ARM64 с помощью средств x86|
|msvc_x86_x64|Компиляция для AMD64 с помощью средств x86|
|msvc_x64_x64|Компиляция для AMD64 с помощью 64-разрядных средств|
|msvc_arm_x64|Компиляция для ARM с помощью 64-разрядных средств|
|msvc_arm64_x64|Компиляция для ARM64 с помощью 64-разрядных средств|

### <a name="custom-environment-variables"></a>Пользовательские переменные среды

В `CMakeSettings.json` можно определить пользовательские переменные среды на глобальном уровне или для отдельных конфигураций в свойстве **environments**. Следующий пример определяет одну глобальную переменную **BuildDir**, которая наследуется в конфигурациях x86-Debug и x64-Debug. Каждая конфигурация использует эту переменную, чтобы задать значение свойства **buildRoot** для этой конфигурации. Обратите внимание, как каждая конфигурация использует свойство **inheritEnvironments**, чтобы указать переменную, применяемую только к этой конфигурации.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

В следующем примере конфигурация отладки x86 определяет свое значение для свойства **BuildDir**. Это значение переопределяет значение, заданное в глобальном свойстве **BuildDir**, чтобы **BuildRoot** принимало значение `D:\custom-builddir\x86-Debug`.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)<br/>
