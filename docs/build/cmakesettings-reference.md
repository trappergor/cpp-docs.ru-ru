---
title: Справочник по схеме CMakeSettings.json
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: c80bb27761b8de91f7caee5932f28f1ec2ac0e29
ms.sourcegitcommit: 166039ceea3256c26fb23920b96de4257b8cf149
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84946652"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

::: moniker range="vs-2015"

Проекты CMake поддерживаются в Visual Studio версии 2017 и более поздних.

::: moniker-end

::: moniker range=">=vs-2017"

Файл **CMakeSettings.json** содержит сведения, которые Visual Studio использует для IntelliSense и для формирования аргументов командной строки, передаваемых в программу cmake.exe для указанной *конфигурации* и *среды* компилятора. Конфигурация определяет свойства, которые применяются к конкретной платформе и типу сборки, например `x86-Debug` или `Linux-Release`. Каждая конфигурация задает среду, которая инкапсулирует сведения о наборе инструментов компилятора, например MSVC, GCC или Clang. CMake использует аргументы командной строки для повторного создания корневого файла *CMakeCache.txt* и других файлов проекта. Значения в файлах *CMakeLists.txt* можно переопределять.

Конфигурации можно добавлять или удалять в интегрированной среде разработки, а затем изменять их непосредственно в JSON-файле или с помощью **редактора параметров CMake** (в Visual Studio 2019 и более поздних версиях). В интегрированной среде разработки можно легко переключаться между конфигурациями для создания различных файлов проекта. Дополнительные сведения см. в статье [Настройка параметров сборки CMake в Visual Studio](customize-cmake-settings.md).

## <a name="configurations"></a>Конфигурации

Массив `configurations` содержит все конфигурации для проекта CMake. Дополнительные сведения о предварительно определенных конфигурациях см. в статье [Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md). В файл можно добавить любое количество предварительно определенных или пользовательских конфигураций.

`configuration` имеет следующие свойства:

- `addressSanitizerEnabled`: если указано значение `true`, программа компилируется с использованием санитайзера адресов (экспериментальная функция в Windows). Для получения наилучших результатов в Linux выполните компиляцию с параметром -fno-omit-frame-pointer и уровнем оптимизации компилятора -Os или -Oo.
- `addressSanitizerRuntimeFlags`: флаги среды выполнения, передаваемые в AddressSanitizer через переменную среды ASAN_OPTIONS. Формат: флаг1=значение:флаг2=значение2.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. Дополнительные сведения о командах Ninja см. в статье [Аргументы командной строки Ninja](#ninja).
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Сопоставляется с параметром **-DCMAKE_BINARY_DIR** и указывает, где будет создан файл *CMakeCache.txt*. Если папка не существует, она будет создана. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cacheGenerationCommand`: определяет программу командной строки и аргументы для создания кэша, например *gencache.bat debug*. Эта команда выполняется из оболочки в указанной для конфигурации среде, когда пользователь явно запрашивает повторное создание или когда изменяется файл CMakeLists.txt либо CMakeSettings.json.
- `cacheRoot`: задает путь к кэшу CMake. Этот каталог должен содержать существующий файл *CMakeCache.txt*.
- `clangTidyChecks`: разделенный запятыми список предупреждений, которые будут переданы в clang-tidy; могут использоваться подстановочные знаки; для исключения проверок укажите префикс "-".
- `cmakeCommandArgs`: указывает дополнительные параметры командной строки, передаваемые в CMake при создании файлов проекта.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Можно указать полный путь к файлу или имя файла набора правил, установленного Visual Studio.
- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:

  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `description`: описание конфигурации, которое отображается в меню.
- `enableClangTidyCodeAnalysis`: использовать Clang-Tidy для анализа кода.
- `enableMicrosoftCodeAnalysis`: использовать средства анализа кода Майкрософт для анализа кода.
- `generator`: указывает генератор CMake для этой конфигурации. Может быть одним из вариантов:
  
  **Только для Visual Studio 2019:**
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

Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно указать, что средство CMake должно создавать проекты Visual Studio.

Чтобы указать генератор Visual Studio в Visual Studio 2017, в главном меню откройте редактор параметров, выбрав **CMake | Изменить параметры CMake**. Удалите слово "Ninja" и введите букву "V". Это активирует IntelliSense, позволяя выбрать нужный генератор.

Чтобы указать генератор Visual Studio в Visual Studio 2019, в **обозревателе решений** щелкните правой кнопкой мыши файл *CMakeLists.txt* и выберите **Параметры CMake для проекта** > **Показать дополнительные настройки** > **Генератор CMake**.

Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку, в файле *CMakeSettings.json* можно указать дополнительные [аргументы командной строки MSBuild](../build/reference/msbuild-visual-cpp-overview.md) для передачи в систему сборки через свойство `buildCommandArgs`:

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

- `name`: имя конфигурации.  Дополнительные сведения о предварительно определенных конфигурациях см. в статье [Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md).
- `wslPath`: путь к средству запуска экземпляра подсистемы Windows для Linux.

### <a name="additional-settings-for-cmake-linux-projects"></a>Дополнительные параметры для проектов CMake Linux

- `remoteMachineName`: задает имя удаленного компьютера Linux, на котором размещается CMake, сборки и отладчик. Используйте диспетчер подключений для добавления новых компьютеров Linux. Поддерживаемые макросы: `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: задает уровень детализации для операции копирования исходных файлов на удаленный компьютер. Может быть нормальным, подробным или диагностическим.
- `remoteCopySourcesConcurrentCopies`: задает количество одновременных операций копирования при синхронизации исходных файлов с удаленным компьютером (только sftp).
- `remoteCopySourcesMethod`: задает метод для копирования файлов на удаленный компьютер. Может быть "rsync" или "sftp".
- `remoteCMakeListsRoot`: задает каталог на удаленном компьютере, в которой содержится проект CMake. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: задает каталог на удаленном компьютере, в котором CMake создает скрипты сборки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: задает каталог на удаленном компьютере, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` и `${env.VARIABLE}`, где `VARIABLE` является переменной среды, которая была определена на уровне системы, пользователя или сеанса.
- `remoteCopySources`. Объект `boolean`, указывающий, следует ли Visual Studio скопировать исходные файлы на удаленный компьютер. Значение по умолчанию — true. Установите значение false, если вы управляете синхронизацией файлов самостоятельно.
- `remoteCopyBuildOutput`. `boolean` указывает, следует ли копировать выходные данные сборки с удаленной системы.
- `remoteCopyAdditionalIncludeDirectories`. Дополнительные каталоги включения, которые будут скопированы с удаленного компьютера для поддержки IntelliSense. Формат: "/путь1;/путь2…".
- `remoteCopyExcludeDirectories`. Каталоги включаемых файлов, которые НЕ будут скопированы с удаленного компьютера. Формат: "/путь1;/путь2…".
- `remoteCopyUseCompilerDefaults`. Указывает, следует ли использовать определения компилятора по умолчанию и пути поиска включаемых файлов для IntelliSense. Значение false следует задавать только в том случае, если используемые компиляторы не поддерживают аргументы в стиле gcc.
- `rsyncCommandArgs`: задает набор дополнительных параметров командной строки, переданных в rsync.
- `remoteCopySourcesExclusionList`. `array` задает список путей, исключаемых при копировании исходных файлов: в качестве пути можно указать имя файла или каталога либо путь по отношению к корневому каталогу копии. Можно использовать подстановочные знаки \\\"*\\\" и \\\"?\\\" для сопоставления со стандартной маской.
- `cmakeExecutable`: задает полный путь к исполняемому файлу программы CMake, включая имя файла и расширение.
- `remotePreGenerateCommand`: задает команду, выполняемую перед запуском CMake для синтаксического анализа файла *CMakeLists.txt*.
- `remotePrebuildCommand`: задает команду, выполняемую на удаленном компьютере перед сборкой.
- `remotePostbuildCommand`: задает команду, выполняемую на удаленном компьютере после сборки.
- `variables`: содержит пару "имя-значение" для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_*. Если инструкции сборки проекта CMake указывают добавление каких-либо переменных непосредственно в файл *CMakeCache.txt*, рекомендуется вместо этого добавить их сюда. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

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

Обратите внимание, что если `"type"` не определен, по умолчанию используется тип `"STRING"`.

- `remoteCopyOptimizations`. свойства **Visual Studio 2019 версии 16.5 или более поздней** для управления копированием исходного кода в удаленный целевой объект. Оптимизации по умолчанию включены. Включает `remoteCopyUseOptimizations`, `rsyncSingleDirectoryCommandArgs` и `remoteCopySourcesMaxSmallChange`.

## <a name="environments"></a><a name="environments"></a> Среды

*Среда* инкапсулирует переменные среды, заданные в процессе, который Visual Studio использует для вызова cmake.exe. Для проектов MSVC это переменные, которые задаются в [командной строке разработчика](building-on-the-command-line.md) для конкретной платформы. Например, среда `msvc_x64_x64` аналогична запуску **командной строки разработчика для VS 2017** или **командной строки разработчика для VS 2019** с аргументами **-arch=amd64 -host_arch=amd64**. Вы можете использовать синтаксис `env.{<variable_name>}` в файле *CMakeSettings.json* для ссылки на отдельные переменные среды, например с целью формирования путей к папкам.  Предоставляются следующие предопределенные среды:

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

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>Доступ к переменным среды из файла CMakeLists.txt

Обращение к переменным среды из файла CMakeLists.txt производится с использованием синтаксиса `$ENV{variable_name}`. Чтобы просмотреть доступные переменные среды, откройте соответствующую командную строку и введите `SET`. Некоторые сведения в переменных среды также доступны посредством переменных самоанализа системы CMake, но переменные среды, скорее всего, будут удобнее в использовании. Например, с помощью переменных среды можно легко получить версию компилятора MSVC или пакета SDK для Windows.

### <a name="custom-environment-variables"></a>Пользовательские переменные среды

В `CMakeSettings.json` можно определить пользовательские переменные среды на глобальном уровне или для отдельных конфигураций в массиве `environments`. Пользовательская среда — это удобный способ составления набора свойств, которые можно использовать вместо предопределенной среды либо для ее расширения или изменения. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по умолчанию называется `env` и заполняется определенными переменными среды, в том числе `%USERPROFILE%`.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`. Целое число, указывающее приоритет этих переменных при их вычислении. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`. Массив значений, указывающих набор сред, наследуемых этой группой. Эта функция позволяет наследовать среды по умолчанию и создавать пользовательские переменные среды, которые передаются в CMake.exe при запуске.

**Visual Studio 2019 версии 16.4 и более поздней:** Целевые объекты отладки автоматически запускаются в среде, указанной в *CMakeSettings.json*. Вы можете переопределить или добавить переменные среды для конкретного целевого объекта или задачи в файлах [launch.vs.json](launch-vs-schema-reference-cpp.md) и [tasks.vs.json](tasks-vs-json-schema-reference-cpp.md).

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

В файле *CMakeSettings.json* можно использовать следующие макросы:

- `${workspaceRoot}` — полный путь к папке рабочей области;
- `${workspaceHash}` — хэш расположения рабочей области; удобен для создания уникального идентификатора для текущей рабочей области (например, для использования в путях папок).
- `${projectFile}` — полный путь к корневому файлу CMakeLists.txt.
- `${projectDir}` — полный путь к папке корневого файла CMakeLists.txt.
- `${thisFile}` — полный путь к файлу `CMakeSettings.json`.
- `${name}` — имя конфигурации.
- `${generator}` — имя генератора CMake, используемого в этой конфигурации.

Все ссылки на макросы и переменные среды в файле *CMakeSettings.json* развертываются перед передачей в командную строку cmake.exe.

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
