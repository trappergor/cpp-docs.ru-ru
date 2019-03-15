---
title: Справочник по схеме CMakeSettings.json
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: d80829b1475e8718e1c4188ff4fb7d42a1d4b3b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827706"
---
# <a name="cmakesettingsjson-schema-reference"></a>Справочник по схеме CMakeSettings.json

Файл `cmakesettings.json` содержит сведения о том, как Visual Studio должна взаимодействовать с CMake для сборки проекта для указанной платформы. Используйте этот файл для хранения сведений, таких как переменные среды или аргументы, для среды cmake.exe.

## <a name="environments"></a>Среды

Массив `environments` содержит список `items` типа `object`, которые определяют среду. Среду можно использовать для применения набора переменных к `configuration`. Каждый элемент в массиве `environments` состоит из следующих компонентов:

- `namespace`: называет среду, чтобы на ее переменные можно было ссылаться из конфигурации в виде `namespace.variable`. Объект среды по умолчанию называется `env` и заполняется определенными переменными среды, в том числе `%USERPROFILE%`.
- `environment`: уникальным образом идентифицирует данную группу переменных. Позволяет наследовать группу позже в записи `inheritEnvironments`.
- `groupPriority`: Целое число, указывающее приоритет этих переменных при их вычислении. Элементы с большим числом вычисляются первыми.
- `inheritEnvironments`: Массив значений, указывающих набор сред, наследуемых этой группой. Можно использовать любую пользовательскую среду или следующие предопределенные среды:
 
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

- `configurationType`; указывает конфигурацию типа сборки для выбранного генератора. Может быть одним из вариантов:
 
  - Отладка
  - Выпуск
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: указывает одну или несколько сред, от которых зависит эта конфигурация. Можно использовать любую пользовательскую среду или предопределенную среду.
- `buildRoot`: определяет каталог, в котором CMake создает скрипты сборки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: определяет каталог, в котором CMake создает целевые объекты установки для выбранного генератора. Поддерживаемые макросы: `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: указывает дополнительные параметры командной строки, передаваемые CMake при создании кэша.
- `cmakeToolchain`: задает файл цепочки инструментов. Передается в CMake с помощью -DCMAKE_TOOLCHAIN_FILE.
- `buildCommandArgs`: задает собственные параметры сборки, передаваемые CMake после --build --.
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
- `variables`: объект `array`, задающий переменные, которые передаются CMake в виде -Dname1=value1 -Dname2=value2 и т. д. 


