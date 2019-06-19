---
title: Настройка проекта Linux CMake в Visual Studio
description: Настройка, изменение и компиляция проекта Linux CMake в Visual Studio
ms.date: 06/07/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e0a4abb7fe62880af12277d5c5c474d6ec4e0202
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821671"
---
# <a name="configure-a-linux-cmake-project"></a>Настройка проекта Linux CMake

::: moniker range="vs-2015"

Поддержка Linux реализована в Visual Studio версии 2017 и выше.

::: moniker-end

При открытии папки, содержащей проект CMake, Visual Studio использует метаданные, создаваемые CMake, для автоматической настройки IntelliSense и сборок. Локальные параметры конфигурации и отладки хранятся в JSON-файлах, которыми при необходимости можно поделиться с другими пользователями, работающими с Visual Studio. 

Visual Studio не изменяет файлы CMakeLists.txt или исходный кэш CMake, чтобы другие сотрудники, работающие над тем же проектом, могли продолжить использование привычных средств.

Общие сведения о поддержке CMake в Visual Studio см. в статье о [средствах CMake для Visual Studio](../build/cmake-projects-in-visual-studio.md). Прочитайте статью, прежде чем продолжить чтение этого раздела.

## <a name="before-you-begin"></a>Подготовка к работе

Сначала убедитесь, что вы установили рабочую нагрузку **Разработка для Linux на C++**, включая компонент CMake. См. раздел [Установка рабочей нагрузки Linux для проектов C++ в Visual Studio](download-install-and-setup-the-linux-development-workload.md). 

Убедитесь, что в системе Linux установлены следующие компоненты: 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

Поддержка проектов CMake в Linux требует последнюю версию CMake на целевом компьютере. Часто версия, предлагаемая в дистрибутиве диспетчером пакетов распространения по умолчанию, не является актуальной и не поддерживает все функции, требуемые для работы с Visual Studio. Visual Studio 2019 определяет, установлена ли последняя версия CMake в системе Linux. Если такая версия не найдена, Visual Studio отображает информационную панель в верхней части области редактора с запросом на установку.

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
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Выбор целевого объекта Linux

Когда вы открываете папку, Visual Studio выполняет синтаксический анализ файла CMakeLists.txt и задает целевой объект Windows **x86-Debug**. Чтобы использовать удаленную систему Linux, измените параметры проекта на **Linux-Debug** или **Linux-Release**. 

::: moniker range="vs-2019"

Чтобы использовать подсистему Windows для Linux, выберите **WSL-Debug** или **WSL-Release**, если используется GCC,или варианты Clang, если используется набор инструментов Clang/LLVM. 

**Visual Studio 2019 версии 16.1** Если вы планируете использовать WSL, копировать или использовать источники либо заголовке не нужно, так как компилятор в Linux имеет прямой доступ к файловой системе Windows, где находятся исходные файлы, а Visual Studio Linux имеет прямой доступ к файлам заголовков.

::: moniker-end

Для целевых объектов Visual Studio по умолчанию выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Межплатформенные** > **Диспетчер подключений**. Если удаленные подключения не найдены, вам будет предложено создать нужное. В этом разделе предполагается, что вы прочитали статью [Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md).

После выбора целевого удаленного объекта Linux ваш источник будет скопирован в удаленную систему.

Когда вы выберете целевой объект, CMake автоматически выполнится в системе Linux, чтобы создать кэш CMake для проекта. 

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

Чтобы включить поддержку удаленных заголовков IntelliSense в удаленных системах Linux, Visual Studio автоматически копирует их с компьютера Linux в папку на локальном компьютере Windows. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Отладка проекта

Чтобы отладить код в указанной целевой системе отладки, задайте точку останова, выберите целевой объект CMake в качестве элемента автозагрузки на панели инструментов рядом с параметром проекта, а затем щелкните **&#x23f5; Запустить** на панели инструментов или нажмите клавишу F5.

Чтобы настроить аргументы командной строки для своей программы, щелкните правой кнопкой мыши исполняемый файл в **обозревателе решений** и выберите **Параметры отладки и запуска**. Будет открыт или создан файл конфигурации launch.vs.json, который содержит сведения о программе. Чтобы указать дополнительные аргументы, добавьте их в массив JSON `args`. Дополнительные сведения см. в статьях [Проекты "Открыть папку" для C++](../build/open-folder-projects-cpp.md) и [Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a>Настройка параметров CMake для Linux

Файл CMakeSettings.json в проекте Linux CMake может указывать все свойства, перечисленные в разделе [Настройка параметров CMake](../build/customize-cmake-settings.md), а также дополнительные свойства, определяющие параметры сборки на удаленном компьютере Linux. 

::: moniker range="vs-2019"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2019, на главной панели инструментов откройте раскрывающийся список **Конфигурация** и выберите **Управление конфигурациями**. 

![Управление конфигурациями CMake](../build/media/vs2019-cmake-manage-configurations.png "Раскрывающийся список конфигураций CMake")

Откроется **редактор параметров CMake**, в котором можно изменить файл `CMakeSettings.json` в корневой папке проекта. Вы также можете открыть файл напрямую, нажав кнопку **Изменить JSON** в редакторе. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Чтобы изменить параметры CMake по умолчанию в Visual Studio 2017, в основном меню выберите **CMake | Изменить параметры CMake | CMakeLists.txt** либо щелкните правой кнопкой мыши файл CMakeSettings.txt в **обозревателе решений** и выберите **Изменить параметры CMake**. Затем Visual Studio создает файл `CMakeSettings.json` в корневой папке проекта. Вы можете открыть этот файл с помощью редактора **параметров CMake** либо изменить файл напрямую. Дополнительные сведения см. в статье [Настраиваемые параметры CMake](../build/customize-cmake-settings.md).

::: moniker-end

Ниже приведен пример конфигурации по умолчанию для Linux-Debug на основании предыдущего примера кода.

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
Эти параметры собраны в следующей таблице:

|Параметр|Описание|
|-----------|-----------------|
|`name`|Это значение может быть любым.|
|`remoteMachineName`|Указывает, какая удаленная система будет целевым объектом, если систем несколько. Чтобы помочь вам выбрать нужную систему, для этого поля включена технология IntelliSense.|
|`remoteCMakeListsRoot`|Указывает, в какое место в удаленной системе будут скопированы источники проекта.|
|`remoteBuildRoot`|Указывает, в каком месте в удаленной системе будут формироваться выходные данные сборки. Эти выходные данные также копируются локально в место, указанное с помощью `buildRoot`.|
|`remoteInstallRoot` и `installRoot`| Похожи на `remoteBuildRoot` и `buildRoot`, но применяются во время установки CMake.|
|`remoteCopySources`|Указывает, копируются ли ваши локальные источники на удаленный компьютер. Можно установить false, если у вас много файлов и вы уже синхронизируете источники самостоятельно.|
|`remoteCopyOutputVerbosity`| Указывает уровень детализации операции копирования на случай, если вам нужно будет диагностировать ошибки.|
|`remoteCopySourcesConcurrentCopies`| Указывает, сколько процессов порождается для копирования.|
|`remoteCopySourcesMethod`| Может быть либо `rsync`, либо `sftp`.|
|`remoteCopySourcesExclusionList`| Указывает файлы, которые не нужно копировать на удаленный компьютер.|
|`rsyncCommandArgs`|Управляет методом rsync для копирования.|
|`remoteCopyBuildOutput`| Указывает, будут ли выходные данные удаленной сборки копироваться в папку локальной сборки.|

Эти дополнительные параметры можно использовать для дополнительного контроля:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Эти параметры позволяют выполнять команды в системе Linux до и после сборки, а также до создания CMake. Они могут быть любой командой, допустимой на удаленной системе. Выходные данные передаются обратно в Visual Studio.

::: moniker range="vs-2019"

В Visual Studio 2019 можно изменить эти параметры в **редакторе параметров CMake**.

::: moniker-end

## <a name="see-also"></a>См. также

[Работа со свойствами проектов](../build/working-with-project-properties.md)<br/>
[Проекты CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md)<br/>
[Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md)<br/>
[Настройка параметров CMake](../build/customize-cmake-settings.md)<br/>
[Настройка сеансов отладки CMake](../build/configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](../build/cmake-predefined-configuration-reference.md)<br/>
