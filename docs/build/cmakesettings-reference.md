---
title: Справочник по схеме CMakeSettings.json
ms.date: 10/31/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 6f8301c07f87feee80191f5db14fea5b16f02863
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624415"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

::: moniker range="vs-2015"

Проекты CMak поддерживаются в Visual Studio 2017 и более поздних версиях.

::: moniker-end

::: moniker range=">=vs-2017"

Файл **CMakeSettings. JSON** содержит сведения, которые Visual Studio использует для IntelliSense, и для создания аргументов командной строки, которые она передает в CMAK. exe для указанной *среды* *конфигурации* и компилятора. Конфигурация определяет свойства, которые применяются к конкретной платформе и типу сборки, например `x86-Debug` или `Linux-Release`. Каждая конфигурация задает среду, которая инкапсулирует сведения о наборе инструментов компилятора, например КОМПИЛЯТОРОМ MSVC, GCC или Clang. CMak использует аргументы командной строки для повторного создания корневого файла *CMakeCache. txt* и других файлов проекта для проекта. Значения можно переопределить в файлах *CMakeLists. txt* . 

Можно добавить или удалить конфигурации в интегрированной среде разработки, а затем изменить их непосредственно в JSON-файле или воспользоваться **редактором параметров CMAK** (Visual Studio 2019 и более поздние версии). Можно легко переключаться между конфигурациями в интегрированной среде разработки для создания различных файлов проекта. Дополнительные сведения см. [в разделе Настройка параметров сборки CMAK в Visual Studio](customize-cmake-settings.md) .

## <a name="configurations"></a>Конфигурации

Массив `configurations` содержит все конфигурации для проекта CMak. Дополнительные сведения о предварительно определенных конфигурациях см. в разделе [руководство по предварительно заданной конфигурации CMAK](cmake-predefined-configuration-reference.md) . В файл можно добавить любое количество предварительно определенных или пользовательских конфигураций. 

`configuration` имеет следующие свойства:

- `addressSDanitizerEnabled`: Если `true` компилирует программу с помощью программы очистки адреса (экспериментально в Windows). В Linux Скомпилируйте с параметром-ФНО-опускать-Frame-указатель и уровень оптимизации компилятора — OS или-ОО для получения наилучших результатов.
- `addressSanitizerRuntimeFlags`: флаги среды выполнения передаются в Аддресссанитизер через переменную среды ASAN_OPTIONS. Формат: flag1 = значение: flag2 = значение2.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. Дополнительные сведения о командах Ninja см. в статье [Аргументы командной строки Ninja](#ninja).
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Сопоставляется с параметром **-DCMAKE_BINARY_DIR** и указывает, где будет создан кэш CMake. Если папка не существует, она будет создана. Поддерживаются следующие макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`и `${env.VARIABLE}`.
- `cacheGenerationCommand`: определяет средство командной строки и аргументы, например *женкаче. bat Debug* для создания кэша. Команда выполняется из оболочки в заданной среде для конфигурации при повторном создании пользовательских запросов или при изменении файла CMakeLists. txt или CMakeSettings. JSON.
- `cacheRoot`: задает путь к кэшу CMake. Этот каталог должен содержать существующий файл CMakeCache.txt.
- `clangTidyChecks`: разделенный запятыми список варнигнс, которые будут переданы в Clang; Допускается использование подстановочных знаков, а префикс "-" приведет к удалению проверок.
- `cmakeCommandArgs`: указывает дополнительные параметры командной строки, передаваемые CMake при создании кэша.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Можно указать полный путь к файлу или имя файла набора правил, установленного Visual Studio.
- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:

  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `description`: описание конфигурации, которое отображается в меню.
- `enableClangTidyCodeAnalysis`. используйте Clang для анализа кода.
- `enableMicrosoftCodeAnalysis`. Используйте средства анализа кода Майкрософт для анализа кода.
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

Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно указать, что CMak должен создавать проекты Visual Studio.

Чтобы указать генератор Visual Studio в Visual Studio 2017, откройте из главного меню пункт **CMAK | Измените параметры CMak**. Удалите слово Ninja и введите букву V. Это активирует IntelliSense, позволяя выбрать нужный генератор.

Чтобы указать генератор Visual Studio в Visual Studio 2019, щелкните правой кнопкой мыши файл *CMakeLists. txt* в **Обозреватель решений** и выберите **Параметры CMAK для проекта** > **Показывать дополнительные параметры** > **CMAK. Генератор**.

Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку в файле *CMakeSettings. JSON* , можно указать дополнительные [аргументы командной строки MSBuild](../build/reference/msbuild-visual-cpp-overview.md) для передачи в систему сборки с помощью свойства `buildCommandArgs`:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:

  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
 
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Сопоставляется с параметром **-DCMAKE_BINARY_DIR** и указывает, где будет создан *CMakeCache. txt* . Если папка не существует, она будет создана. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: указывает дополнительные параметры командной строки, передаваемые в CMak при вызове для создания файлов проекта.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. Дополнительные сведения о командах Ninja см. в статье [Аргументы командной строки Ninja](#ninja).
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Можно указать полный путь к файлу или имя файла набора правил, установленного Visual Studio.
- `inheritEnvironments`: указывает одну или несколько сред компилятора, от которых зависит эта конфигурация. Можно использовать любую пользовательскую или предопределенную среду. Дополнительные сведения: [Среды](#environments).
- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
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

- `cacheRoot`: задает путь к кэшу CMake. Этот каталог должен содержать существующий файл *CMakeCache. txt* .
- `name`: имя конфигурации.  Дополнительные сведения о предварительно определенных конфигурациях см. в разделе [руководство по предварительно заданной конфигурации CMAK](cmake-predefined-configuration-reference.md) .
- `wslPath`: путь к средству запуска экземпляра подсистемы Windows для Linux.

### <a name="additional-settings-for-cmake-linux-projects"></a>Дополнительные параметры для проектов CMake Linux. 

- `remoteMachineName`: задает имя удаленного компьютера Linux, на котором размещается CMake, сборки и отладчик. Используйте диспетчер подключений для добавления новых компьютеров Linux. Поддерживаемые макросы: `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: задает уровень детализации для операции копирования исходных файлов на удаленный компьютер. Может быть нормальным, подробным или диагностическим.
- `remoteCopySourcesConcurrentCopies`: указывает количество одновременных копий, используемых во время синхронизации источников на удаленном компьютере (только SFTP).
- `remoteCopySourcesMethod`: задает метод для копирования файлов на удаленный компьютер. Может быть "rsync" или "sftp".
- `remoteCMakeListsRoot`: задает каталог на удаленном компьютере, в которой содержится проект CMake. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: задает каталог на удаленном компьютере, в котором CMake создает скрипты сборки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: задает каталог на удаленном компьютере, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` и `${env.VARIABLE}`, где `VARIABLE` является переменной среды, которая была определена на уровне системы, пользователя или сеанса.
- `remoteCopySources`: `boolean`, указывающий, должна ли Visual Studio копировать исходные файлы на удаленный компьютер. Значение по умолчанию — true. Установите значение false, если вы управляете синхронизацией файлов самостоятельно.
- `remoteCopyBuildOutput`: `boolean`, указывающий, следует ли копировать выходные данные сборки из удаленной системы.
- `rsyncCommandArgs`: задает набор дополнительных параметров командной строки, переданных в rsync.
- `remoteCopySourcesExclusionList`: `array`, указывающий список путей, исключаемых при копировании исходных файлов: путь может представлять собой имя файла или каталога или путь относительно корня копии. Можно использовать подстановочные знаки \\\"*\\\" и \\\"?\\\" для сопоставления со стандартной маской.
- `cmakeExecutable`: задает полный путь к исполняемому файлу программы CMake, включая имя файла и расширение.
- `remotePreGenerateCommand`: Указывает команду, выполняемую перед запуском CMak для синтаксического анализа файла *CMakeLists. txt* .
- `remotePrebuildCommand`: задает команду, выполняемую на удаленном компьютере перед сборкой.
- `remotePostbuildCommand`: задает команду, выполняемую на удаленном компьютере после сборки.
- `variables`: содержит пару имя-значение для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_* . Если в инструкциях по сборке проекта CMak указано Добавление переменных непосредственно в файл *CMakeCache. txt* , рекомендуется добавить их здесь. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

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

Обратите внимание, что если не определить `"type"`, по умолчанию будет использоваться тип `"STRING"`.

## <a name="environments"></a>Возможным

*Среда* инкапсулирует переменные среды, заданные в процессе, который Visual Studio использует для вызова CMAK. exe. Для проектов КОМПИЛЯТОРОМ MSVC используются переменные, заданные в [командной строке разработчика](building-on-the-command-line.md) для конкретной платформы. Например, `msvc_x64_x64` среда аналогична запуску **Командная строка разработчика для vs 2017** или **Командная строка разработчика для VS 2019** с аргументами **-Arch = AMD64-host_arch = AMD64** . Можно использовать синтаксис `env.{<variable_name>}` в *CMakeSettings. JSON* для ссылки на отдельные переменные среды, например для создания путей к папкам.  Предоставляются следующие предопределенные среды:

- linux_arm: удаленная версия ARM Linux.
- linux_x64: Целевая версия x64 Linux удаленно.
- linux_x86: target x86 Linux удаленно.
- msvc_arm: целевые окна ARM с компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_arm_x64: целевые окна ARM с 64-разрядным компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_arm64: target ARM64 Windows с компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_arm64_x64: target ARM64 Windows с 64-разрядным компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_x64: целевые окна x64 с компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_x64_x64: целевые окна x64 с 64-разрядным компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_x86: целевые окна x86 с компилятором КОМПИЛЯТОРОМ MSVC.
- msvc_x86_x64: целевые окна x86 с 64-разрядным компилятором КОМПИЛЯТОРОМ MSVC.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>Доступ к переменным среды из CMakeLists. txt

Из файла CMakeLists. txt на все переменные среды ссылается синтаксис `$ENV{variable_name}`. Чтобы просмотреть доступные переменные среды, откройте соответствующую командную строку и введите `SET`. Некоторые сведения в переменных среды также доступны через переменные System самоанализ системы CMak, но, возможно, удобнее использовать переменную среды. Например, версия компилятора КОМПИЛЯТОРОМ MSVC или версия Windows SDK легко извлекаются с помощью переменных среды.

### <a name="custom-environment-variables"></a>Пользовательские переменные среды

В `CMakeSettings.json`можно задавать пользовательские переменные среды глобально или для каждой конфигурации в массиве `environments`. Пользовательская среда — это удобный способ группировки набора свойств, которые можно использовать вместо предопределенной среды или для расширения или изменения предопределенной среды. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по умолчанию называется `env` и заполняется определенными системными переменными среды, включая `%USERPROFILE%`.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`: целое число, указывающее приоритет этих переменных при их вычислении. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`: массив значений, определяющих набор сред, наследуемых этой группой. Эта функция позволяет наследовать среды по умолчанию и создавать пользовательские переменные среды, которые передаются в CMake.exe при запуске.

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
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>Макросы

В *CMakeSettings. JSON*можно использовать следующие макросы:

- `${workspaceRoot}` — полный путь к папке рабочей области
- `${workspaceHash}` — хэш расположения рабочей области; удобен для создания уникального идентификатора для текущей рабочей области (например, для использования в путях папок).
- `${projectFile}` — полный путь к корневому файлу CMakeLists.txt.
- `${projectDir}` — полный путь к папке корневого файла CMakeLists.txt.
- `${thisFile}` — полный путь к файлу `CMakeSettings.json`.
- `${name}` — имя конфигурации.
- `${generator}` — имя генератора CMake, используемого в этой конфигурации.

Все ссылки на макросы и переменные среды в *CMakeSettings. JSON* развертываются перед передачей в командную строку CMAK. exe.

## <a name="ninja"></a> Аргументы командной строки Ninja

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
