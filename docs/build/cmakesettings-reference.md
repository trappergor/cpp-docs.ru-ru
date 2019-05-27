---
title: Справочник по схеме CMakeSettings.json
ms.date: 05/16/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 018a755aa4f3acde44fe1dbb33b07b49c8d1c223
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837257"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

Файл **cmakesettings.json** содержит сведения о том, как среда Visual Studio должна взаимодействовать с CMake для сборки проекта для указанной платформы. В нем хранятся такие сведения, как переменные среды или аргументы, для среды cmake.exe. Этот файл можно изменить напрямую или с помощью **редактора параметров CMake** (в Visual Studio 2019 и более поздних версий). Дополнительные сведения о редакторе см. в статье [Настройка параметров сборки CMake в Visual Studio](customize-cmake-settings.md).

## <a name="environments"></a>Среды

Массив `environments` содержит список элементов `items` типа `object`, которые определяют среду набора средств компилятора. Среду можно использовать для применения набора переменных к `configuration`. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по умолчанию называется `env` и заполняется определенными переменными среды, в том числе `%USERPROFILE%`.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`: Целое число, указывающее приоритет этих переменных при их вычислении. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`: Массив значений, указывающих набор сред, наследуемых этой группой. Эта функция позволяет наследовать среды по умолчанию и создавать пользовательские переменные среды, которые передаются в CMake.exe при запуске.

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   Приведенный выше пример аналогичен запуску **Командной строки разработчика для VS 2017** или **Командной строки разработчика для VS 2019** с аргументами **-arch=amd64 -host_arch=amd64**. Можно использовать любую пользовательскую среду или следующие предопределенные среды:
 
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

Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно велеть CMake создать проект Visual Studio.

Чтобы указать генератор Visual Studio в Visual Studio 2017, откройте `CMakeSettings.json` в главном меню, выбрав **CMake | Изменить параметры CMake**. Удалите слово Ninja и введите букву V. Это активирует IntelliSense, позволяя выбрать нужный генератор.

Чтобы указать генератор Visual Studio в Visual Studio 2019, щелкните правой кнопкой мыши файл CMakeLists.txt в **обозревателе решений** и выберите **Параметры CMake для проекта** > **Показать дополнительные настройки** > **Генератор CMake**.

Когда для активной конфигурации выбран генератор Visual Studio, по умолчанию вызывается MSBuild.exe с аргументами `-m -v:minimal`. Чтобы настроить сборку в файле `CMakeSettings.json`, можно указать дополнительные [аргументы командной строки MSBuild](../build/reference/msbuild-visual-cpp-overview.md) для передачи в систему сборки через свойство `buildCommandArgs`:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:
 
  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: указывает одну или несколько сред компилятора, от которых зависит эта конфигурация. Можно использовать любую пользовательскую или предопределенную среду.
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора.  Сопоставляется с параметром **-DCMAKE_BINARY_DIR** и указывает, где будет создан кэш CMake. Если папка не существует, она будет создана. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: указывает дополнительные параметры командной строки, передаваемые CMake при создании кэша.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --. Например, передача -v при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки. Дополнительные сведения о командах Ninja см. в статье [Аргументы командной строки Ninja](#ninja).
- `ctestCommandArgs`: задает дополнительные параметры командной строки, передаваемые CTest при запуске тестов.
- `codeAnalysisRuleset`: указывает набор правил для использования при выполнении анализа кода. Можно указать полный путь к файлу или имя файла набора правил, установленного Visual Studio.
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
- `variables`: содержит пару имя-значение для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_*. Если инструкции сборки проекта CMake указывают добавление каких-либо переменных непосредственно в файл кэша CMake, рекомендуется вместо этого добавить их сюда. В следующем примере показано, как задать пары имя-значение для набора инструментов 14.14.26428 MSVC:

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

Обратите внимание, что если `"type"` не определен, по умолчанию используется строковый тип.

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




