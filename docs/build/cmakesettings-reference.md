---
title: Справочник по схеме CMakeSettings.json
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: f9c864b66df86165090b7d6d6fc9c4fc51d65a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328896"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

::: moniker range="vs-2015"

Проекты CMake поддерживаются в Visual Studio 2017 и позже.

::: moniker-end

::: moniker range=">=vs-2017"

Файл **CMakeSettings.json** содержит информацию, которую Visual Studio использует для IntelliSense и для построения аргументов командной строки, которые она передает cmake.exe для заданной *среды* *конфигурации* и компилятора. Конфигурация определяет свойства, которые применяются к определенной платформе и `x86-Debug` `Linux-Release`типу сборки, например, или. Каждая конфигурация определяет среду, которая инкапсулирует информацию о наборе инструментов компилятора, например MSVC, GCC или Clang. CMake использует аргументы командной строки для регенерации корневого файла *CMakeCache.txt* и других файлов проекта. Значения могут быть переопределены в файлах *CMakeLists.txt.*

Вы можете добавить или удалить конфигурации в IDE, а затем отредконить их непосредственно в файле JSON или использовать **редактор CMake Настройки** (Visual Studio 2019 и более поздний срок). Вы можете легко переключаться между конфигурациями в IDE для генерации различных файлов проектов. Для получения дополнительной информации смотрите [настройки сборки CMake в Visual Studio.](customize-cmake-settings.md)

## <a name="configurations"></a>Конфигурации

Массив `configurations` содержит все конфигурации для проекта CMake. Для получения дополнительной информации о заранее определенных конфигурациях смотрите [предопределенные настройки CMake.](cmake-predefined-configuration-reference.md) Вы можете добавить любое количество заранее определенных или пользовательских конфигураций в файл.

`configuration` имеет следующие свойства:

- `addressSanitizerEnabled`: `true` если компилирует программу с адресом sanitizer (Экспериментальный на Windows). На Linux, компилировать с -fno-omit-кадр-указатель и компилятор оптимизации уровня-Os или -Oo для достижения наилучших результатов.
- `addressSanitizerRuntimeFlags`: флаги времени выполнения передаются AddressSanitizer через переменную ASAN_OPTIONS среды. Формат: flag1'value:flag2'value2.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. Дополнительные сведения о командах Ninja см. в статье [Аргументы командной строки Ninja](#ninja).
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Карты **для -DCMAKE_BINARY_DIR** переключения и указывает, где *CMakeCache.txt* будет создан. Если папка не существует, она будет создана. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cacheGenerationCommand`: определяет инструмент командной строки и аргументы, например *gencache.bat отладка* для создания кэша. Команда запускается из оболочки в заданной среде для конфигурации, когда пользователь явно запрашивает регенерацию, или файл CMakeLists.txt или CMakeSettings.json модифицируется.
- `cacheRoot`: задает путь к кэшу CMake. Этот каталог должен содержать существующий файл *CMakeCache.txt.*
- `clangTidyChecks`: запятая-отделенный список предупреждений, которые будут переданы в clang-tidy; подстановочные знаки разрешены и "-" префикс будет удалить чеки.
- `cmakeCommandArgs`: определяет дополнительные параметры командной строки, передаваемые CMake при вызове для создания файлов проекта.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Можно указать полный путь к файлу или имя файла набора правил, установленного Visual Studio.
- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:

  - Отладка
  - Release
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `description`: описание конфигурации, которое отображается в меню.
- `enableClangTidyCodeAnalysis`: используйте Clang-Tidy для анализа кода.
- `enableMicrosoftCodeAnalysis`: используйте инструменты анализа кода Майкрософт для анализа кода.
- `generator`: указывает генератор CMake для этой конфигурации. Может быть одним из вариантов:
  
  **Только visual Studio 2019:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 и более поздних версий:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefile
  - Ninja

Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. Если это происходит, вы можете поручить CMake создавать проекты Visual Studio.

Чтобы указать генератор Visual Studio в Visual Studio 2017, откройте из основного меню, выбрав **CMake Изменение настроек CMake**. Удалить "Ниндзя" и тип "V". Это активирует IntelliSense, позволяя выбрать нужный генератор.

Чтобы указать генератор Visual Studio в Visual Studio 2019, нажмите правой кнопкой мыши на файл *CMakeLists.txt* в **Solution Explorer** и выберите **настройки CMake для проекта** > **Show Advanced Settings** > **CMake Generator.**

Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку внутри файла *CMakeSettings.json,* можно указать дополнительные [аргументы командной строки MSBuild,](../build/reference/msbuild-visual-cpp-overview.md) которые будут переданы системе сборки через свойство: `buildCommandArgs`

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `inheritEnvironments`: указывает одну или несколько сред компилятора, от которых зависит эта конфигурация. Можно использовать любую пользовательскую или предопределенную среду. Дополнительные сведения: [Среды](#environments).
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

- `name`: имя конфигурации.  Для получения дополнительной информации о заранее определенных конфигурациях смотрите [предопределенные настройки CMake.](cmake-predefined-configuration-reference.md)
- `wslPath`: путь к пусковой установке экземпляра подсистемы Windows для Linux.

### <a name="additional-settings-for-cmake-linux-projects"></a>Дополнительные настройки для проектов CMake Linux

- `remoteMachineName`: задает имя удаленного компьютера Linux, на котором размещается CMake, сборки и отладчик. Используйте диспетчер подключений для добавления новых компьютеров Linux. Поддерживаемые макросы: `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: задает уровень детализации для операции копирования исходных файлов на удаленный компьютер. Может быть нормальным, подробным или диагностическим.
- `remoteCopySourcesConcurrentCopies`: определяет количество одновременных копий, используемых при синхронизации источников с удаленной машиной (только sftp).
- `remoteCopySourcesMethod`: задает метод для копирования файлов на удаленный компьютер. Может быть "rsync" или "sftp".
- `remoteCMakeListsRoot`: задает каталог на удаленном компьютере, в которой содержится проект CMake. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: задает каталог на удаленном компьютере, в котором CMake создает скрипты сборки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: задает каталог на удаленном компьютере, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` и `${env.VARIABLE}`, где `VARIABLE` является переменной среды, которая была определена на уровне системы, пользователя или сеанса.
- `remoteCopySources`: `boolean` A определяет, должна ли Visual Studio копировать исходные файлы на удаленной машине. Значение по умолчанию — true. Установите значение false, если вы управляете синхронизацией файлов самостоятельно.
- `remoteCopyBuildOutput`: `boolean` A определяет, следует ли копировать выходы сборки из удаленной системы.
- `remoteCopyAdditionalIncludeDirectories`: Дополнительные функции включают каталоги, которые будут скопированы с удаленной машины для поддержки IntelliSense. Формат как "/path1;/path2...".
- `remoteCopyExcludeDirectories`: Включите каталоги, которые НЕ копировать с удаленной машины. Формат как "/path1;/path2...".
- `remoteCopyUseCompilerDefaults`: Определяет, следует ли использовать значение компилятора по умолчанию и включать пути для IntelliSense. Должно быть только ложным, если компиляторы в использовании, чтобы не поддерживать gcc стиле аргументы.
- `rsyncCommandArgs`: задает набор дополнительных параметров командной строки, переданных в rsync.
- `remoteCopySourcesExclusionList`: `array` A, который определяет список путей, которые должны быть исключены при копировании исходных файлов: путь может быть имя файла / каталога, или путь по отношению к корню копии. Можно использовать подстановочные знаки \\\"*\\\" и \\\"?\\\" для сопоставления со стандартной маской.
- `cmakeExecutable`: задает полный путь к исполняемому файлу программы CMake, включая имя файла и расширение.
- `remotePreGenerateCommand`: определяет команду для запуска перед запуском CMake для разбора файла *CMakeLists.txt.*
- `remotePrebuildCommand`: задает команду, выполняемую на удаленном компьютере перед сборкой.
- `remotePostbuildCommand`: задает команду, выполняемую на удаленном компьютере после сборки.
- `variables`: содержит пару имя-значение для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_*. Если инструкции по сборке проекта CMake указывают добавление любых переменных непосредственно в файл *CMakeCache.txt,* рекомендуется добавить их здесь. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

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

Обратите внимание, что если `"type"`вы `"STRING"` не определяете, тип будет предполагается по умолчанию.

- `remoteCopyOptimizations`: **Visual Studio 2019 версия 16.5 или более поздние** свойства для управления копией источника к удаленной цели. Оптимизация включена по умолчанию. Включает `remoteCopyUseOptimizations`, `rsyncSingleDirectoryCommandArgs` и `remoteCopySourcesMaxSmallChange`.

## <a name="environments"></a><a name="environments"></a>Средах

*Среда* инкапсулирует переменные среды, которые устанавливаются в процессе, который Visual Studio использует для вызывать cmake.exe. Для проектов MSVC переменные — это те, которые установлены в [запросе команды разработчика](building-on-the-command-line.md) для определенной платформы. Например, `msvc_x64_x64` среда такая же, как и запуск **команды разработчиков Prompt для VS 2017** или **Команды разработчиков Для VS 2019** с **аргументами -arch-amd64-host_arch'amd64.** Синтаксис `env.{<variable_name>}` можно использовать в *CMakeSettings.json* для ссылки на отдельные переменные среды, например, для построения путей к папкам.  Предоставляются следующие предопределенные среды:

- linux_arm: Target ARM Linux удаленно.
- linux_x64: Target x64 Linux удаленно.
- linux_x86: Target x86 Linux удаленно.
- msvc_arm: Целевая система ARM Windows с компилятором MSVC.
- msvc_arm_x64: Target ARM Windows с 64-разрядным компилятором MSVC.
- msvc_arm64: Целевая компания ARM64 Windows с компилятором MSVC.
- msvc_arm64_x64: Target ARM64 Windows с 64-разрядным компилятором MSVC.
- msvc_x64: Target x64 Windows с компилятором MSVC.
- msvc_x64_x64: Target x64 Windows с 64-разрядным компилятором MSVC.
- msvc_x86: Target x86 Windows с компилятором MSVC.
- msvc_x86_x64: Target x86 Windows с 64-разрядным компилятором MSVC.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>Доступ к переменным среды от CMakeLists.txt

Из файла CMakeLists.txt все переменные среды ссылаются на синтаксис. `$ENV{variable_name}` Чтобы увидеть доступные переменные для среды, откройте соответствующий запрос команды и введите. `SET` Часть информации в переменных среды также доступна через переменные системы самоанализа Системы CMake, но вы можете найти более удобным использование переменной среды. Например, компиляторная версия MSVC или версия Windows SDK легко извлекаются через переменные среды.

### <a name="custom-environment-variables"></a>Пользовательские переменные среды

В, `CMakeSettings.json`вы можете определить пользовательские переменные среды `environments` глобально или в конфигурации в массиве. Пользовательская среда — это удобный способ сгруппировать набор свойств, которые можно использовать вместо заданной среды, или расширить или изменить предопределенную среду. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по `env` умолчанию вызывается и заполняется `%USERPROFILE%`определенными переменными системной среды, включая.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`: Несколько, которое определяет приоритет этих переменных при их оценке. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`: Массив значений, определяющих набор сред, унаследованных этой группой. Эта функция позволяет наследовать среды по умолчанию и создавать пользовательские переменные среды, которые передаются в CMake.exe при запуске.

**Visual Studio 2019 версия 16.4 и позже:** Цели debug автоматически запускаются с помощью указанной вами среды в *CMakeSettings.json.* Вы можете переопределить или добавить переменные среды на основе в-цель или по задачам в [launch.vs.json](launch-vs-schema-reference-cpp.md) и [tasks.vs.json.](tasks-vs-json-schema-reference-cpp.md)

Следующий пример определяет одну глобальную переменную **BuildDir**, которая наследуется в конфигурациях x86-Debug и x64-Debug. Каждая конфигурация использует эту переменную, чтобы задать значение свойства **buildRoot** для этой конфигурации. Обратите внимание, как каждая конфигурация использует свойство **inheritEnvironments**, чтобы указать переменную, применяемую только к этой конфигурации.

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
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>Макросы

Следующие макросы могут быть использованы в *CMakeSettings.json*:

- `${workspaceRoot}`- полный путь папки рабочей области
- `${workspaceHash}` — хэш расположения рабочей области; удобен для создания уникального идентификатора для текущей рабочей области (например, для использования в путях папок).
- `${projectFile}` — полный путь к корневому файлу CMakeLists.txt.
- `${projectDir}` — полный путь к папке корневого файла CMakeLists.txt.
- `${thisFile}` — полный путь к файлу `CMakeSettings.json`.
- `${name}` — имя конфигурации.
- `${generator}` — имя генератора CMake, используемого в этой конфигурации.

Все ссылки на макросы и переменные среды в *CMakeSettings.json* расширяются перед тем, как перейти к командной строке cmake.exe.

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a> Аргументы командной строки Ninja

Если целевые объекты не заданы, создается целевой объект default.

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
|   -t TOOL  | Запуск подчиненного инструмента (используйте список -t для указания подчиненных инструментов); завершает действие параметров верхнего уровня; в средство передаются дополнительные флаги|
|   -w FLAG  | Настройка предупреждений (используйте список -w для указания предупреждений)|

::: moniker-end
