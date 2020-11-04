---
title: Настройка проекта Linux CMake в Visual Studio
description: Настройка параметров Linux CMake в Visual Studio
ms.date: 08/08/2020
ms.openlocfilehash: c4c2d4682b6d18f9175a92a810b3f86d8132fc0c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921923"
---
# <a name="configure-a-linux-cmake-project-in-visual-studio"></a>Настройка проекта Linux CMake в Visual Studio

::: moniker range="msvc-140"
Поддержка Linux реализована в Visual Studio версии 2017 и выше. Чтобы увидеть документацию для этих версий, установите в расположенном над содержанием раскрывающемся списке **Версия** пункт **Visual Studio 2017** или **Visual Studio 2019**.
::: moniker-end

::: moniker range=">=msvc-150"
В этой статье описывается добавление конфигурации Linux в проекте CMake, предназначенном как для удаленной системы Linux, так и для подсистемы Windows для Linux (WSL). Это продолжение серии, которая началась со статьи [Создание и настройка проекта Linux CMake](cmake-linux-project.md). Если используется MSBuild, ознакомьтесь со статьей [Настройка проекта Linux](configure-a-linux-project.md).

## <a name="add-a-linux-configuration"></a>Добавление конфигурации Linux

Конфигурацию можно использовать для различных платформ (Windows, WSL, удаленных систем) с одним и тем же исходным кодом. Конфигурация также используется для установки компиляторов, передачи переменных среды и настройки способа вызова CMake. В файле *CMakeSettings.json* задаются некоторые или все свойства, перечисленные в статье [Настройка параметров сборки CMake](../build/customize-cmake-settings.md), а также дополнительные свойства, определяющие параметры сборки на удаленном компьютере Linux.
::: moniker-end

::: moniker range="msvc-150"
Чтобы изменить параметры CMake по умолчанию в Visual Studio 2017, в главном меню последовательно выберите **CMake** > **Изменить параметры CMake** > **CMakeLists.txt**. Или же щелкните правой кнопкой мыши файл *CMakeLists.txt* в **Обозревателе решений** и выберите пункт **Изменить параметры CMake**. Затем Visual Studio создает новый файл *CMakeSettings.json* в корневой папке проекта. Чтобы внести изменения, откройте файл и измените его напрямую. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

Конфигурация по умолчанию для Linux-Debug в Visual Studio 2017 (а также для Visual Studio 2019 версии 16.0) выглядит следующим образом:

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

::: moniker range="msvc-160"
Чтобы изменить параметры CMake по умолчанию в Visual Studio 2019, в главной панели инструментов откройте раскрывающийся список **Конфигурация** и выберите **Управление конфигурациями**.

![Управление конфигурациями CMake](../build/media/vs2019-cmake-manage-configurations.png "Раскрывающийся список конфигураций CMake")

Откроется **Редактор параметров CMake** , в котором можно изменить файл *CMakeSettings.json* в корневой папке проекта. Вы также можете открыть файл в помощью редактора JSON, нажав кнопку **Изменить JSON** в редакторе. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

Конфигурация Linux-Debug по умолчанию в Visual Studio 2019 версии 16.1 и более поздних версиях представлена ниже:

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

Ninja является генератором по умолчанию для конфигураций, предназначенных для удаленных систем или WSL в Visual Studio 2019 версии 16.6 или более поздней. Дополнительные сведения см. в публикации [блога команды разработчиков C++](https://devblogs.microsoft.com/cppblog/linux-development-with-visual-studio-first-class-support-for-gdbserver-improved-build-times-with-ninja-and-updates-to-the-connection-manager/).

::: moniker-end
::: moniker range=">=msvc-150"
Дополнительные сведения об этих параметрах см. в разделе [документации по CMakeSettings.json](../build/cmakesettings-reference.md).

При выполнении сборки:

- Если целевая система предназначена для удаленной системы, Visual Studio по умолчанию выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Кроссплатформенные** > **Диспетчер подключений** для целевых объектов.
- Если ни одно удаленное подключение не будет найдено, вам будет предложено создать его. В этом разделе предполагается, что вы прочитали статью [Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md).

## <a name="choose-a-linux-target"></a>Выбор целевого объекта Linux

Когда вы открываете папку проекта CMake, Visual Studio выполняет синтаксический анализ файла *CMakeLists.txt* и задает целевой объект Windows **x86-Debug**. Чтобы использовать удаленную систему Linux, измените параметры проекта в соответствии с используемым компилятором Linux. Например, если вы используете GCC в Linux и выполняете компиляцию с отладочной информацией, выберите следующее:  **Linux-GCC-Debug** или **Linux-GCC-Release**.

После выбора целевого удаленного объекта Linux ваш источник будет скопирован в удаленную систему.

Когда вы выберете целевой объект, CMake автоматически выполнится в системе Linux, чтобы создать кэш CMake для проекта:

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

::: moniker-end
::: moniker range="msvc-160"

### <a name="target-windows-subsystem-for-linux"></a>Использование подсистемы Windows для Linux

Если вы намерены использовать подсистему Windows для Linux (WSL), вам не нужно добавлять удаленное подключение.

Чтобы настроить использование подсистемы WSL, выберите **Управление конфигурациями** в раскрывающемся меню конфигураций на главной панели инструментов:

![Управление конфигурациями CMake](../build/media/vs2019-cmake-manage-configurations.png "Раскрывающийся список конфигураций CMake")

Откроется окно **CMakeSettings.json**.

![Добавление конфигурации](media/cmake-linux-configurations.png "Добавление конфигурации в параметры CMake")

Щелкните **Добавить конфигурацию** (зеленая кнопка "+") и выберите **Linux-GCC-Debug** или **Linux-GCC-Release** , если вы используете GCC. Если используется набор инструментов Clang/LLVM, выберите один из вариантов Clang.  Нажмите **Выбрать** и нажмите клавиши **CTRL+S** , чтобы сохранить конфигурацию.

**Visual Studio 2019 версии 16.1**. Если вы планируете использовать WSL, Visual Studio не требуется копировать исходные файлы и поддерживать две синхронные копии вашего дерева сборки, так как компилятор в Linux имеет прямой доступ к исходным файлам в подключенной файловой системе Windows.
::: moniker-end
::: moniker range=">=msvc-150"

### <a name="intellisense"></a>IntelliSense

Для правильной работы C++ IntelliSense требуется доступ к заголовкам C++, на которые ссылаются исходные файлы C++. Visual Studio автоматически использует заголовки, на которые ссылается проект CMake из Linux в Windows, чтобы обеспечить полную функциональность технологии IntelliSense. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

### <a name="locale-setting"></a>Настройка языкового стандарта

Языковые параметры Visual Studio не распространяются на целевые объекты Linux, так как Visual Studio не управляет установленными пакетами и не настраивает их. Сообщения, отображаемые в окне Вывод, например ошибки сборки, отображаются с использованием языка и языкового стандарта целевого объекта Linux. Вам потребуется настроить целевые объекты Linux для требуемого языкового стандарта.

## <a name="additional-settings"></a>Дополнительные параметры

Используйте следующие параметры, чтобы выполнять команды в системе Linux до и после сборки, а также до создания CMake. Они могут быть любой командой, допустимой на удаленной системе. Выходные данные передаются обратно в Visual Studio.

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

## <a name="next-steps"></a>Дальнейшие действия

[Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md?toc=/cpp/linux/toc.json&bc=/cpp/_breadcrumb/toc.json)

## <a name="see-also"></a>Дополнительно

[Настройка компилятора и свойств сборки](../build/working-with-project-properties.md)<br/>
[Настройка параметров CMake](../build/customize-cmake-settings.md)<br/>
[Справочник по предопределенной конфигурации CMake](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
