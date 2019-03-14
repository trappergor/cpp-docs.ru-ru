---
title: Настройка проекта Linux CMake в Visual Studio
description: Настройка проекта Linux CMake в Visual Studio
ms.date: 11/01/2018
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: f2186c14fbe2eb1273fceb4a378b359564eae327
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750602"
---
# <a name="configure-a-linux-cmake-project"></a>Настройка проекта Linux CMake

При открытии папки, содержащей проект CMake, Visual Studio использует метаданные, создаваемые CMake, для автоматической настройки IntelliSense и сборок. Локальные параметры конфигурации и отладки хранятся в JSON-файлах, которыми при необходимости можно поделиться с другими пользователями, работающими с Visual Studio. 

Visual Studio не изменяет файлы CMakeLists.txt или исходный кэш CMake, чтобы другие сотрудники, работающие над тем же проектом, могли продолжить использование привычных средств.  

## <a name="before-you-begin"></a>Подготовка к работе

Сначала убедитесь, что вы установили рабочую нагрузку **Разработка для Linux на C++**, включая компонент CMake. См. раздел [Установка рабочей нагрузки Linux для проектов C++ в Visual Studio](download-install-and-setup-the-linux-development-workload.md). 

Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

В этом разделе предполагается, что вы прочитали статью [Средства CMake для Visual Studio](../ide/cmake-tools-for-visual-cpp.md). 

> [!NOTE]
> Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases). В Visual Studio 2019 предварительно созданные двоичные файлы можно развернуть автоматически (см. раздел [Скачивание предварительно созданных двоичных файлов CMake](#download-prebuilt-cmake-binaries)).

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

По умолчанию Visual Studio выбирает первую удаленную систему в списке в разделе **Инструменты** > **Параметры** > **Межплатформенные** > **Диспетчер подключений**. Если удаленные подключения не найдены, вам будет предложено создать нужное. В этом разделе предполагается, что вы прочитали статью [Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md).

После указания целевого объекта Linux источник копируется на компьютер Linux. Затем CMake выполняется на компьютере Linux, чтобы создать кэш CMake для проекта.

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")

**Visual Studio 2017 версии 15.7 и выше**<br/>
Чтобы обеспечить поддержку IntelliSense для удаленных заголовков, Visual Studio автоматически копирует их с компьютера Linux в папку на локальном компьютере Windows. Подробнее см. в разделе [IntelliSense для удаленных заголовков](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Отладка проекта

Чтобы отладить код в удаленной системе, задайте точку останова, выберите целевой объект CMake в качестве элемента автозагрузки на панели инструментов рядом с параметром проекта, а затем щелкните **&#x23f5; Запустить** на панели инструментов или нажмите клавишу F5.

Чтобы настроить аргументы командной строки для своей программы, щелкните правой кнопкой мыши исполняемый файл в **обозревателе решений** и выберите **Параметры отладки и запуска**. Будет открыт или создан файл конфигурации launch.vs.json, который содержит сведения о программе. Чтобы указать дополнительные аргументы, добавьте их в массив JSON `args`. Дополнительные сведения см. в статьях [Проекты "Открыть папку" в Visual C++](../ide/non-msbuild-projects.md) и [Настройка сеансов отладки CMake](../ide/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a>Настройка параметров CMake для Linux

Файл CMakeSettings.json в проекте Linux CMake может указывать все свойства, перечисленные в разделе [Настройка параметров CMake](../ide/customize-cmake-settings.md), а также дополнительные свойства, определяющие параметры сборки на удаленном компьютере Linux. Чтобы изменить параметры CMake по умолчанию, в основном меню выберите **CMake | Изменить параметры CMake | CMakeLists.txt** либо щелкните правой кнопкой мыши файл CMakeSettings.txt в **обозревателе решений** и выберите **Изменить параметры CMake**. Затем Visual Studio создает файл `CMakeSettings.json` в корневой папке проекта. Вы можете открыть этот файл с помощью редактора **параметров CMake** либо изменить файл напрямую. 

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
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Эти параметры позволяют вам выполнять команды на удаленной системе до и после сборки и до создания CMake. Они могут быть любой командой, допустимой на удаленной системе. Выходные данные передаются обратно в Visual Studio.

## <a name="download-prebuilt-cmake-binaries"></a>Скачивание предварительно созданных двоичных файлов CMake

В дистрибутиве Linux может быть более ранняя версия CMake. Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

**Visual Studio 2019**<br/>
Если допустимый файл CMake не будет найден на удаленном компьютере, появится информационная панель и вам будет предоставлена возможность автоматически развернуть предварительно созданные двоичные файлы CMake. Двоичные файлы установятся в папку `~/.vs/cmake`. После развертывания двоичных файлов проект будет повторно создан автоматически. Обратите внимание, что если файл CMake, указанный в поле `cmakeExecutable` в `CMakeSettings.json`, является недопустимым (файл не существует или версия файла не поддерживается), то при наличии предварительно созданных двоичных файлов Visual Studio проигнорирует `cmakeExecutable` и будет использовать эти предварительно созданные двоичные файлы.

## <a name="see-also"></a>См. также

[Работа со свойствами проектов](../ide/working-with-project-properties.md)<br/>
[Инструменты CMake для Visual C++](../ide/cmake-tools-for-visual-cpp.md)<br/>
[Подключение к удаленному компьютеру Linux](connect-to-your-remote-linux-computer.md)<br/>
[Настройка параметров CMake](../ide/customize-cmake-settings.md)<br/>
[Настройка сеансов отладки CMake](../ide/configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](../ide/cmake-predefined-configuration-reference.md)<br/>
