---
title: Создание и настройка проекта Linux CMake в Visual Studio
description: Создание, настройка, изменение и компиляция проекта Linux CMake в Visual Studio
ms.date: 10/04/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 128b8dac297398ffbfadfaade5b36c843d55e163
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625952"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Создание и настройка проекта Linux CMake

::: moniker range="vs-2015"

Поддержка Linux реализована в Visual Studio версии 2017 и выше.

::: moniker-end

::: moniker range="vs-2019"

Чтобы создать проект Linux CMake в Visual Studio 2019, сделайте следующее:

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Задайте для параметра **Язык** значение **C++** и выполните поиск по строке CMake. Теперь щелкните **Далее**. Укажите **имя** и **расположение**, а затем щелкните **Создать**.

Visual Studio создает минимально допустимый файл CMakeLists.txt, где содержится только имя исполняемого файла и минимальная требуемая версия CMake. При необходимости вы можете вручную изменить этот файл. Visual Studio никогда не переопределяет пользовательские изменения. Вы можете указать для CMake аргументы командной строки и переменные среды, щелкнув корневой файл CMakeLists.txt правой кнопкой мыши в **обозревателе решений** и выбрав **Параметры CMake для проекта**. Чтобы задать параметры для отладки, щелкните правой кнопкой мыши узел проекта и выберите **Параметры отладки и запуска**.

::: moniker-end

При открытии папки, содержащей существующий проект CMake, Visual Studio применяет переменные в кэше CMake для автоматических настройки IntelliSense и сборок. Локальные параметры конфигурации и отладки хранятся в JSON-файлах, которыми при необходимости можно поделиться с другими пользователями, работающими с Visual Studio.

Visual Studio не изменяет файлы CMakeLists.txt, чтобы другие разработчики, работающие над тем же проектом, могли и дальше использовать привычные средства. Но Visual Studio повторно создает кэш после сохранения изменений в файле CMakeLists.txt и (в некоторых случаях) в файле CMakeSettings.json. Но если вы используете конфигурацию **Существующий кэш**, Visual Studio не изменяет содержимое кэша.

Общие сведения о поддержке CMake в Visual Studio см. в статье о [проектах CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md). Прочитайте статью, прежде чем продолжить чтение этого раздела.

## <a name="before-you-begin"></a>Подготовка к работе

Сначала убедитесь, что вы установили рабочую нагрузку **Разработка для Linux на C++** , включая компонент CMake. См. раздел [Установка рабочей нагрузки Linux для проектов C++ в Visual Studio](download-install-and-setup-the-linux-development-workload.md). 

Убедитесь, что в системе Linux установлены следующие компоненты: 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

Поддержка проектов CMake в Linux требует последнюю версию CMake на целевом компьютере. Часто версия, предлагаемая в дистрибутиве диспетчером пакетов распространения по умолчанию, не является актуальной и не поддерживает все функции, требуемые для работы с Visual Studio. Visual Studio 2019 определяет, установлена ли последняя версия CMake в системе Linux. Если такая версия не найдена, Visual Studio отображает информационную панель в верхней части области редактора с запросом на установку из [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для Visual Studio 2019 рекомендуется версия 3.14 или более поздняя.

::: moniker-end

::: moniker range="vs-2017"

Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

Двоичные файлы установятся в папку `~/.vs/cmake`. После развертывания двоичных файлов проект будет повторно создан автоматически. Обратите внимание, что если файл CMake, указанный в поле `cmakeExecutable` в `CMakeSettings.json`, является недопустимым (файл не существует или версия файла не поддерживается), то при наличии предварительно созданных двоичных файлов Visual Studio проигнорирует `cmakeExecutable` и будет использовать эти предварительно созданные двоичные файлы.

:::moniker-end

## <a name="open-a-folder"></a>Открытие папки

Чтобы приступить к работе, в основном меню последовательно выберите **Файл** > **Открыть** > **Папка** или введите `devenv.exe <foldername>` в командной строке. В открываемой паке должен находиться файл CMakeLists.txt вместе с исходным кодом.
Ниже приведен пример простого файла CMakeLists.txt и CPP-файла.

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Выбор целевого объекта Linux

Когда вы открываете папку, Visual Studio выполняет синтаксический анализ файла CMakeLists.txt и задает целевой объект Windows **x86-Debug**. Чтобы использовать удаленную систему Linux, измените параметры проекта на **Linux-Debug** или **Linux-Release**. (См. ниже раздел [Настройка параметров CMake для Linux](#configure_cmake_linux).)

::: moniker range="vs-2019"

Чтобы выполнить настройку для использования подсистемы Windows для Linux, щелкните **Управление конфигурациями** в разделе раскрывающегося меню конфигураций на главной панели инструментов. Теперь щелкните **Добавить конфигурацию** и выберите **WSL-Debug** или **WSL-Release** для GCC либо один из вариантов Clang для набора инструментов Clang/LLVM. 

**Visual Studio 2019 версии 16.1** Если вы планируете использовать WSL, копировать или использовать источники либо заголовке не нужно, так как компилятор в Linux имеет прямой доступ к файловой системе Windows, где находятся исходные файлы. (В Windows версии 1903 и выше все приложения Windows также могут напрямую обращаться к файлам заголовков Linux, но Visual Studio пока не поддерживает эту возможность).

::: moniker-end

Для целевых объектов Visual Studio по умолчанию выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Межплатформенные** > **Диспетчер подключений**. Если удаленные подключения не найдены, вам будет предложено создать нужное. В этом разделе предполагается, что вы прочитали статью [Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md).

После выбора целевого удаленного объекта Linux ваш источник будет скопирован в удаленную систему.

Когда вы выберете целевой объект, CMake автоматически выполнится в системе Linux, чтобы создать кэш CMake для проекта. 

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

Чтобы включить поддержку удаленных заголовков IntelliSense в удаленных системах Linux, Visual Studio автоматически копирует их с компьютера Linux в папку на локальном компьютере Windows. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

## <a name="debug_cmake_project"></a> Отладка проекта CMake

Чтобы отладить код в указанной целевой системе отладки, задайте точку останова, выберите целевой объект CMake в качестве элемента автозагрузки на панели инструментов рядом с параметром проекта, а затем щелкните **&#x23f5; Запустить** на панели инструментов или нажмите клавишу F5.

Чтобы настроить аргументы командной строки для программы, нажмите кнопку **Переключить целевые объекты** в верхней части **обозревателя решений** и выберите **Представление целевых объектов**. Щелкните целевой объект правой кнопкой мыши и выберите **Параметры отладки и запуска**. Будет открыт или создан файл конфигурации launch.vs.json, который содержит сведения о программе. Чтобы указать расположение исходных файлов, добавьте в файл свойство **sourceFileMap**, как показано в следующем примере:

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

Чтобы указать дополнительные аргументы, добавьте их в массив JSON `args`. Дополнительные сведения см. в статьях [Проекты "Открыть папку" для C++](../build/open-folder-projects-cpp.md) и [Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md).

## <a name="configure_cmake_linux"></a> Настройка параметров CMake для Linux

Файл CMakeSettings.json в проекте Linux CMake может указывать все свойства, перечисленные в разделе [Настройка параметров CMake](../build/customize-cmake-settings.md), а также дополнительные свойства, определяющие параметры сборки на удаленном компьютере Linux. 

::: moniker range="vs-2019"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2019, на главной панели инструментов откройте раскрывающийся список **Конфигурация** и выберите **Управление конфигурациями**. 

![Управление конфигурациями CMake](../build/media/vs2019-cmake-manage-configurations.png "Раскрывающийся список конфигураций CMake")

Откроется **редактор параметров CMake**, в котором можно изменить файл `CMakeSettings.json` в корневой папке проекта. Вы также можете открыть файл напрямую, нажав кнопку **Изменить JSON** в редакторе. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2017, в основном меню выберите **CMake | Изменить параметры CMake | CMakeLists.txt** либо щелкните правой кнопкой мыши файл CMakeSettings.txt в **обозревателе решений** и выберите **Изменить параметры CMake**. Затем Visual Studio создает файл `CMakeSettings.json` в корневой папке проекта. Вы можете открыть этот файл с помощью редактора **параметров CMake** либо изменить файл напрямую. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

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

::: moniker range="vs-2019"

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
[Справочник по предопределенной конфигурации CMake](../build/cmake-predefined-configuration-reference.md)<br/>
