---
title: Справочник по схеме CMakeSettings.json
ms.date: 04/25/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 80392eedd5ef50ddd9c9bcb81c1605a534088133
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877107"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

**Cmakesettings.json**"файл содержит сведения о том, как Visual Studio должна взаимодействовать с CMake для построения проекта для указанной платформы. В файле хранятся сведения, такие как переменные среды или аргументы для cmake.exe среды. Вы можете изменить непосредственно или использовать **редактор параметров CMake**. См. в разделе [сборки CMake, настроить параметры в Visual Studio](customize-cmake-settings.md) Дополнительные сведения о редакторе.

## <a name="environments"></a>Среды

`environments` Массив содержит список `items` типа `object` которые определяют набор инструментов компилятора «среда». Среду можно использовать для применения набора переменных к `configuration`. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по умолчанию называется `env` и заполняется определенными переменными среды, в том числе `%USERPROFILE%`.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`: Целое число, указывающее приоритет этих переменных при их вычислении. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`: Массив значений, указывающих набор сред, наследуемых этой группой. Эта функция позволяет наследовать среды по умолчанию и создать пользовательские переменные среды, передаваемые CMake.exe, когда оно работает.

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   Приведенный выше пример аналогичен запуску **Командной строки разработчика для VS 2017** с аргументами **-arch=amd64 -host_arch=amd64**. Можно использовать любую пользовательскую среду или следующие предопределенные среды:
 
  - linux_arm: удаленная ориентация на Linux ARM.
  - linux_x64: удаленная ориентация на Linux x64.
  - linux_x86: удаленная ориентация на Linux x86.
  - msvc_arm: ориентация на Windows ARM с компилятором MSVC.
  - msvc_arm_x64: ориентация на Windows ARM с 64-разрядным компилятором MSVC.
  - msvc_arm64: ориентация на Windows ARM64 с компилятором MSVC.
  - msvc_arm64_x64: ориентация на Windows ARM64 с 64-разрядным компилятором MSVC.
  - msvc_x64: ориентация на Windows x64 с компилятором MSVC.
  - msvc_x64_x64: ориентация на Windows x64 с 64-разрядным компилятором MSVC.
  - msvc_x86: ориентация на Windows x86 с компилятором MSVC.
  - msvc_x86_x64: ориентация на Windows x86 с 64-разрядным компилятором MSVC.

## <a name="configurations"></a>Конфигурации

Массив `configurations` состоит из объектов, представляющих конфигурации CMake, которые применяются к файлу CMakeLists.txt в той же папке. Вы можете использовать эти объекты, чтобы определить несколько конфигураций сборки и с удобством переключаться между ними в IDE. 

`configuration` имеет следующие свойства:
- `name`: имя конфигурации.
- `description`: описание конфигурации, которое отображается в меню.
- `generator`: указывает генератор CMake для этой конфигурации. Может быть одним из вариантов:

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefile
  - Ninja

Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно велеть CMake создать проект Visual Studio.

Чтобы указать генератор Visual Studio, откройте `CMakeSettings.json` в главном меню, выбрав **CMake | Изменить параметры CMake**. Удалите слово Ninja и введите букву V. Это активирует IntelliSense, позволяя выбрать нужный генератор.

Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку в файле `CMakeSettings.json`, можно указать дополнительные [аргументы командной строки MSBuild](../build/reference/msbuild-visual-cpp-overview.md) для передачи в систему сборки через свойство `buildCommandArgs`:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:
 
  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: Указывает один или несколько сред компилятора, от которых зависит эта конфигурация. Может быть любое пользовательское окружение или одной из стандартных сред.
- `buildRoot`: Указывает каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Сопоставляется **-DCMAKE_BINARY_DIR** переключения и указывает, где будут создаваться кэш CMake. Если папка не существует, он создается. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: Указывает дополнительные параметры командной строки, передаваемые CMake при создании кэша.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `buildCommandArgs`: Указывает собственные параметры сборки, передаваемые в CMake после--сборки--. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. См. в разделе [аргументы командной строки Ninja](#ninja) Дополнительные сведения о командах Ninja.
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Это может быть полный путь или имя файла набора правил, установленного Visual Studio.
- `intelliSenseMode`: задает режим, используемый для вычисления сведений IntelliSense. Может быть одним из вариантов:
 
  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm

- `cacheRoot`: задает путь к кэшу CMake. Этот каталог должен содержать существующий файл CMakeCache.txt.

### <a name="additional-settings-for-cmake-linux-projects"></a>Дополнительные параметры для проектов CMake Linux. 

- `remoteMachineName`: задает имя удаленного компьютера Linux, на котором размещается CMake, сборки и отладчик. Используйте диспетчер подключений для добавления новых компьютеров Linux. Поддерживаемые макросы: `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: задает уровень детализации для операции копирования исходных файлов на удаленный компьютер. Может быть нормальным, подробным или диагностическим.
- `remoteCopySourcesConcurrentCopies`: задает количество одновременных операций копирования при синхронизации исходных файлов на удаленном компьютере.
- `remoteCopySourcesMethod`: задает метод для копирования файлов на удаленный компьютер. Может быть "rsync" или "sftp".
- `remoteCMakeListsRoot`: задает каталог на удаленном компьютере, в которой содержится проект CMake. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: задает каталог на удаленном компьютере, в котором CMake создает скрипты сборки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: задает каталог на удаленном компьютере, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` и `${env.VARIABLE}`, где `VARIABLE` является переменной среды, которая была определена на уровне системы, пользователя или сеанса.
- `remoteCopySources`: Объект `boolean`, указывающий, следует ли Visual Studio скопировать исходные файлы на удаленный компьютер. Значение по умолчанию — true. Установите значение false, если вы управляете синхронизацией файлов самостоятельно.
- `remoteCopyBuildOutput`: `boolean` указывает, следует ли копировать выходные данные сборки с удаленной системы.
- `rsyncCommandArgs`: задает набор дополнительных параметров командной строки, переданных в rsync.
- `remoteCopySourcesExclusionList`: `array` задает список путей, исключаемых при копировании исходных файлов: в качестве пути можно указать имя файла или каталога либо путь по отношению к корневому каталогу копии. Можно использовать подстановочные знаки \\\"*\\\" и \\\"?\\\" для сопоставления со стандартной маской.
- `cmakeExecutable`: задает полный путь к исполняемому файлу программы CMake, включая имя файла и расширение.
- `remotePreGenerateCommand`: задает команду, выполняемую перед запуском CMake для синтаксического анализа CMakeLists.txt.
- `remotePrebuildCommand`: задает команду, выполняемую на удаленном компьютере перед сборкой.
- `remotePostbuildCommand`: задает команду, выполняемую на удаленном компьютере после сборки.
- `variables`: содержит пары имя значение переменных CMake, будет передаваемых как **-D** *_имя_=_значение_* для CMake. Если инструкции сборки проекта CMake указывают добавление каких-либо переменных непосредственно в файл кэша CMake, рекомендуется вместо этого добавить их сюда. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

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

## <a name="environment-variables"></a>Переменные среды

`CMakeSettings.json` также поддерживает использование переменных среды, в каких-либо его свойств, упомянутых выше. Для расширения переменной среды %FOO% используется синтаксис `${env.FOO}`.

Вы также можете обращаться ко встроенным макросам внутри этого файла:

- `${workspaceRoot}` — предоставляет полный путь для папки рабочей области.
- `${workspaceHash}` — хэш расположения рабочей области; удобен для создания уникального идентификатора для текущей рабочей области (например, для использования в путях папок).
- `${projectFile}` — полный путь к корневому файлу CMakeLists.txt.
- `${projectDir}` — полный путь к папке корневого файла CMakeLists.txt.
- `${thisFile}` — полный путь к файлу `CMakeSettings.json`.
- `${name}` — имя конфигурации.
- `${generator}` — имя генератора CMake, используемого в этой конфигурации.


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

## <a name="ninja"></a> Аргументы командной строки ninja

Если целевые объекты не указаны, создает целевой объект «default».

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




