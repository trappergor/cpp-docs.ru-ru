---
title: Настройка проекта Linux CMake в Visual Studio
description: Настройка проекта Linux CMake в Visual Studio
ms.date: 07/20/2018
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 32d69e28c0991adc6117b7f9496eeb1022943ef2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585046"
---
# <a name="configure-a-linux-cmake-project"></a>Настройка проекта Linux CMake

**Visual Studio 2017 версии 15.4 и выше**<br/>
При установке рабочей нагрузки Linux для проектов C++ в Visual Studio по умолчанию выбирается поддержка CMake для Linux. Теперь вы можете работать с существующей базой кода, где CMake не требуется преобразовывать в проект VS. Если база кода является кроссплатформенной, в Visual Studio можно создавать решения как для Windows, так и для Linux.

В этом разделе предполагается, что вы уже знакомы с поддержкой CMake в Visual Studio. Дополнительные сведения см. в разделе [Инструменты CMake для Visual C++](../ide/cmake-tools-for-visual-cpp.md). Дополнительные сведения о CMake см. на странице [Сборка, тестирование и упаковка программного обеспечения с помощью CMake](https://cmake.org/).

> [!NOTE]
> Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

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

Когда вы открываете папку, Visual Studio выполняет синтаксический анализ файла CMakeLists.txt и задает целевой объект Windows **x86-Debug**. Чтобы использовать Linux, измените параметры проекта на **Linux-Debug** или **Linux-Release**.

По умолчанию Visual Studio выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Межплатформенные** > **Диспетчер подключений**. Если удаленные подключения не найдены, вам будет предложено создать нужное.

После указания целевого объекта Linux источник копируется на компьютер Linux. Затем CMake выполняется на компьютере Linux, чтобы создать кэш CMake для проекта.

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

**Visual Studio 2017 версии 15.7 и выше**<br/>
Чтобы обеспечить поддержку IntelliSense для удаленных заголовков, Visual Studio автоматически копирует их в папку на локальном компьютере Windows. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Отладка проекта

Чтобы отладить код в удаленной системе, задайте точку останова, выберите целевой объект CMake в качестве элемента автозагрузки на панели инструментов рядом с параметром проекта, а затем щелкните **&#x23f5; Запустить** на панели инструментов или нажмите клавишу F5.

Чтобы настроить аргументы командной строки для своей программы, щелкните правой кнопкой мыши исполняемый файл в **обозревателе решений** и выберите **Параметры отладки и запуска**. Будет открыт или создан файл конфигурации launch.vs.json, который содержит сведения о программе. Чтобы указать дополнительные аргументы, добавьте их в массив JSON `args`. Дополнительные сведения см. в статье [Open Folder projects in Visual C++](../ide/non-msbuild-projects.md) (Открытие папки проектов в Visual C++).

## <a name="configure-cmake-settings-for-linux"></a>Настройка параметров CMake для Linux

Чтобы изменить параметры CMake по умолчанию, в основном меню выберите **CMake | Изменить параметры CMake | CMakeLists.txt** либо щелкните правой кнопкой мыши файл CMakeSettings.txt в **обозревателе решений** и выберите **Изменить параметры CMake**. Visual Studio создаст новый файл в папке с именем `CMakeSettings.json`, который заполняется конфигурациями по умолчанию, перечисленными в пункте меню параметров проекта. Ниже приведен пример конфигурации по умолчанию для Linux-Debug на основании предыдущего примера кода.

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

Значение `name` может быть любым. Значение `remoteMachineName` указывает, какая удаленная система будет целевым объектом, если систем несколько. Чтобы помочь вам выбрать нужную систему, для этого поля включена технология IntelliSense. Поле `remoteCMakeListsRoot` указывает, в какое место в удаленной системе будут скопированы источники проекта Поле `remoteBuildRoot` указывает, в каком месте в удаленной системе будут формироваться выходные данные сборки. Эти выходные данные также копируются локально в место, указанное с помощью `buildRoot`. Поля `remoteInstallRoot` и `installRoot` похожи на `remoteBuildRoot` и `buildRoot`, но применяются во время установки cmake. Запись `remoteCopySources` определяет, копируются ли ваши локальные источники на удаленный компьютер. Можно установить false, если у вас много файлов и вы уже синхронизируете источники самостоятельно. Значение `remoteCopyOutputVerbosity` определяет уровень детализации операции копирования на случай, если вам необходимо будет диагностировать ошибки. Запись `remoteCopySourcesConcurrentCopies` определяет, сколько процессов создается для копирования. Значение `remoteCopySourcesMethod` может быть rsync или sftp. Поле `remoteCopySourcesExclusionList` позволяет указать, что будет скопировано на удаленный компьютер. Значение `rsyncCommandArgs` позволяет управлять методом копирования rsync. Поле `remoteCopyBuildOutput` указывает, будут ли выходные данные удаленной сборки копироваться в папку локальной сборки.

Кроме того, существуют некоторые необязательные параметры, которые можно использовать для дополнительного контроля:

```json
{
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Эти параметры позволяют вам выполнять команды в окне удаленного ввода до и после сборки и до создания CMake. Они могут быть любой допустимой командой в окне удаленного ввода. Выходные данные передаются обратно в Visual Studio.

## <a name="download-prebuilt-cmake-binaries"></a>Скачивание предварительно созданных двоичных файлов CMake

В дистрибутиве Linux может быть более ранняя версия CMake. Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

## <a name="see-also"></a>См. также

[Работа со свойствами проектов](../ide/working-with-project-properties.md)<br/>
[Инструменты CMake для Visual C++](../ide/cmake-tools-for-visual-cpp.md)
