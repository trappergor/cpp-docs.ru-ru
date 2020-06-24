---
title: Создание и настройка проекта Linux CMake в Visual Studio
description: Создание, настройка, изменение и компиляция проекта Linux CMake в Visual Studio
ms.date: 06/22/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 2149b102c452149070d59c9645ce34a5977a6057
ms.sourcegitcommit: f9344b09a734e8b05a7494415991a22b7aec5ae8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269732"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Создание и настройка проекта Linux CMake

::: moniker range="vs-2015"

Поддержка Linux реализована в Visual Studio версии 2017 и выше. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="before-you-begin"></a>Подготовка к работе

Сначала убедитесь, что вы установили рабочую нагрузку **Разработка для Linux на C++** , включая компонент CMake. См. раздел [Установка рабочей нагрузки Linux для проектов C++ в Visual Studio](download-install-and-setup-the-linux-development-workload.md).

Убедитесь, что в системе Linux установлены следующие компоненты:

- gcc
- gdb
- rsync
- zip
- ninja-build

::: moniker-end

::: moniker range="vs-2019"

Для поддержки проектов CMake в Linux на целевом компьютере должна быть установлена последняя версия CMake. Часто в дистрибутиве версия, которую предлагает диспетчер пакетов по умолчанию, не является актуальной и не поддерживает все функции, необходимые для работы с Visual Studio. Visual Studio 2019 определяет, установлена ли последняя версия CMake в системе Linux. Если такая версия не найдена, Visual Studio отображает информационную панель в верхней части области редактора. В ней предлагается установить CMake из [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для Visual Studio 2019 рекомендуется версия 3.14 или более поздняя.

::: moniker-end

::: moniker range="vs-2017"

Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

Двоичные файлы устанавливаются в каталог `~/.vs/cmake`. После развертывания двоичных файлов автоматически выполняется повторное создание проекта. Если файл CMake, указанный в поле `cmakeExecutable` в *CMakeSettings.json*, является недопустимым (файл не существует или версия файла не поддерживается), то при наличии предварительно созданных двоичных файлов Visual Studio игнорирует поле `cmakeExecutable` и использует эти предварительно созданные двоичные файлы.

:::moniker-end

::: moniker range="vs-2019"

## <a name="create-a-new-linux-cmake-project"></a>Создание нового проекта CMake в Linux

Чтобы создать проект Linux CMake в Visual Studio 2019, сделайте следующее:

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Задайте для параметра **Язык** значение **C++** и выполните поиск по строке CMake. Теперь щелкните **Далее**. Укажите **имя** и **расположение**, а затем щелкните **Создать**.

Visual Studio создает минимальный файл *CMakeLists.txt*, в котором содержится только имя исполняемого файла и минимальная требуемая версия CMake. При необходимости вы можете вручную изменить этот файл. Visual Studio никогда не переопределяет пользовательские изменения. В этом файле можно задать переменные среды и аргументы командной строки CMake. Щелкните правой кнопкой мыши корневой файл *CMakeLists.txt* в **Обозревателе решений** и выберите пункт **Параметры CMake для проекта**. Чтобы задать параметры для отладки, щелкните правой кнопкой мыши узел проекта и выберите **Параметры отладки и запуска**.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="open-a-cmake-project-folder"></a>Открытие папки проекта CMake

Когда вы открываете папку, содержащую существующий проект CMake, Visual Studio автоматически настраивает IntelliSense и сборки, используя переменные в кэше CMake. Локальные параметры конфигурации и отладки хранятся в файлах JSON. При желании вы можете предоставить доступ к этим файлам другим пользователям Visual Studio.

Visual Studio не изменяет файлы *CMakeLists.txt*. Они остаются неизменными, чтобы ваши коллеги, работающие над тем же проектом, могли продолжать использовать свои существующие инструменты. После того как вы сохраните изменения в файле *CMakeLists.txt* и (в некоторых случаях) в файле *CMakeSettings.json*, Visual Studio повторно создает кэш. Но если вы используете конфигурацию **Существующий кэш**, то Visual Studio не изменяет содержимое кэша.

Общие сведения о поддержке CMake в Visual Studio см. в статье о [проектах CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md). Прочитайте статью, прежде чем продолжить чтение этого раздела.

Чтобы приступить к работе, в главном меню последовательно выберите пункты **Файл** > **Открыть** > **Папка** или введите `devenv.exe <foldername>` в окне [командной строки разработчика](../build/building-on-the-command-line.md). В открываемой паке должен находиться файл *CMakeLists.txt* вместе с исходным кодом.

Ниже приведен пример простого файла *CMakeLists.txt* и CPP-файла.

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*CMakeLists.txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Выбор целевого объекта Linux

Когда вы открываете папку, Visual Studio выполняет синтаксический анализ файла *CMakeLists.txt* и задает целевой объект Windows **x86-Debug**. Чтобы использовать удаленную систему Linux, измените параметры проекта на **Linux-Debug** или **Linux-Release**. (См. ниже раздел [Настройка параметров CMake для Linux](#configure_cmake_linux).)

::: moniker-end

::: moniker range="vs-2019"

Чтобы настроить использование подсистемы Windows для Linux, щелкните **Управление конфигурациями** в раскрывающемся меню конфигураций на главной панели инструментов. Затем нажмите **Добавить конфигурацию** и выберите **WSL-Debug** или **WSL-Release**, если используется GCC. Если используется набор инструментов Clang/LLVM, выберите один из вариантов Clang.

**Visual Studio 2019 версии 16.1**. При указании WSL не требуется копировать никакие исходные файлы или заголовки, так как компилятор в Linux имеет прямой доступ к вашим исходным файлам в файловой системе Windows. (В Windows 10, начиная с версии 1903, приложения Windows также имеют прямой доступ к файлам заголовка Linux. В Visual Studio такая возможность пока отсутствует.)

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio по умолчанию выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Межплатформенные** > **Диспетчер подключений** для целевых объектов. Если ни одно удаленное подключение не будет найдено, вам будет предложено создать его. В этом разделе предполагается, что вы прочитали статью [Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md).

После выбора целевого удаленного объекта Linux ваш источник будет скопирован в удаленную систему.

Когда вы выберете целевой объект, CMake автоматически выполнится в системе Linux, чтобы создать кэш CMake для проекта.

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

### <a name="intellisense"></a>IntelliSense

Чтобы включить поддержку удаленных заголовков IntelliSense в удаленных системах Linux, Visual Studio автоматически копирует их с компьютера Linux в папку на локальном компьютере Windows. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

### <a name="locale"></a>Языковой стандарт

См. дополнительные сведения о [языковом стандарте целевого объекта Linux](configure-a-linux-project.md#locale).

## <a name="debug-the-cmake-project"></a><a name="debug_cmake_project"></a> Отладка проекта CMake

Для отладки кода в указанной целевой системе установите точку останова. Выберите целевой объект CMake в качестве элемента для запуска в меню панели инструментов рядом с параметром проекта. Затем выберите **&#x23f5; Запуск** в панели инструментов или нажмите клавишу **F5**.

Чтобы настроить аргументы командной строки для программы, нажмите кнопку **Переключить целевые объекты** в верхней части **Обозревателя решений** и выберите **Представление целевых объектов**. Щелкните целевой объект правой кнопкой мыши и выберите **Параметры отладки и запуска**. Будет открыт или создан файл конфигурации *launch.vs.json*, содержащий сведения о вашей программе. Чтобы указать расположение исходных файлов, добавьте в файл свойство **sourceFileMap**, как показано в следующем примере:

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

Чтобы указать дополнительные аргументы, добавьте их в массив JSON `args`. Дополнительные сведения см. в статьях [Проекты "Открыть папку" для C++](../build/open-folder-projects-cpp.md) и [Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a><a name="configure_cmake_linux"></a> Настройка параметров CMake для Linux

В файле *CMakeSettings.json* в проекте Linux CMake могут быть заданы все свойства, перечисленные в разделе [Настройка параметров CMake](../build/customize-cmake-settings.md), а также дополнительные свойства, определяющие параметры сборки на удаленном компьютере Linux.

::: moniker-end

::: moniker range="vs-2019"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2019, в главной панели инструментов откройте раскрывающийся список **Конфигурация** и выберите **Управление конфигурациями**.

![Управление конфигурациями CMake](../build/media/vs2019-cmake-manage-configurations.png "Раскрывающийся список конфигураций CMake")

Откроется **редактор параметров CMake**, в котором можно изменить файл *CMakeSettings.json* в корневой папке проекта. Вы также можете открыть файл напрямую, нажав кнопку **Изменить JSON** в редакторе. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

Конфигурация Linux-Debug по умолчанию в Visual Studio 2019 версии 16.1 и более поздних версиях представлена ниже:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "configurationType": "Debug",
      "cmakeExecutable": "/usr/bin/cmake",
      "remoteCopySourcesExclusionList": [ ".vs", ".git", "out" ],
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux_x64" ],
      "remoteMachineName": "${defaultRemoteMachineName}",
      "remoteCMakeListsRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/src",
      "remoteBuildRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/build/${name}",
      "remoteInstallRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/install/${name}",
      "remoteCopySources": true,
      "rsyncCommandArgs": "-t --delete --delete-excluded",
      "remoteCopyBuildOutput": false,
      "remoteCopySourcesMethod": "rsync",
      "addressSanitizerRuntimeFlags": "detect_leaks=0",
      "variables": []
    }
  ]
}
```

::: moniker-end

::: moniker range="vs-2017"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2017, в главном меню последовательно выберите **CMake** > **Изменить параметры CMake** > **CMakeLists.txt**. Или же щелкните правой кнопкой мыши файл *CMakeSettings.txt* в **Обозревателе решений** и выберите пункт **Изменить параметры CMake**. Затем Visual Studio создает новый файл *CMakeSettings.json* в корневой папке проекта. Вы можете открыть этот файл с помощью редактора **параметров CMake** либо изменить файл напрямую. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

Ниже приведен пример конфигурации по умолчанию для Linux-Debug в Visual Studio 2017 (а также для Visual Studio 2019 версии 16.0) на основе предыдущего примера кода.

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

::: moniker-end

::: moniker range=">=vs-2017"

Дополнительные сведения об этих параметрах см. в разделе [документации по CMakeSettings.json](../build/cmakesettings-reference.md).

## <a name="optional-settings"></a>Необязательные параметры

Следующие необязательные параметры можно использовать для дополнительного контроля:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Эти параметры позволяют выполнять команды в системе Linux до и после сборки, а также до создания CMake. Они могут быть любой командой, допустимой на удаленной системе. Выходные данные передаются обратно в Visual Studio.

## <a name="see-also"></a>См. также

[Работа со свойствами проектов](../build/working-with-project-properties.md)<br/>
[Проекты CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md)<br/>
[Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md)<br/>
[Настройка параметров CMake](../build/customize-cmake-settings.md)<br/>
[Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
