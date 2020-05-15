---
title: Настройка параметров сборки CMake в Visual Studio
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: c6bd1404799ccc9ad6b689646cd066849d48fca8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328681"
---
# <a name="customize-cmake-build-settings"></a>Настройка параметров сборки CMake

::: moniker range="vs-2019"

В Visual Studio 2019 и более поздних версий можно добавлять конфигурации и настраивать их параметры с помощью **редактора параметров CMake**. Редактор является упрощенной альтернативой редактирования файла *CMakeSettings.json* вручную, но если вы предпочитаете редактировать файл напрямую, щелкните ссылку **Изменить JSON** в правом верхнем углу редактора.

Чтобы открыть редактор, перейдите в раскрывающееся меню **Конфигурация** на главной панели инструментов и выберите **Управление конфигурациями**.

![Раскрывающийся список конфигураций CMake](media/vs2019-cmake-manage-configurations.png)

Откроется **редактор параметров** с установленными конфигурациями слева.

![Редактор параметров CMake](media/cmake-settings-editor.png)

Visual Studio предоставляет одну конфигурацию `x64-Debug` по умолчанию. Вы можете добавить дополнительные конфигурации, щелкнув зеленый знак плюса. Параметры, отображаемые в редакторе, зависят от выбранной конфигурации.

Параметры, которые выбираются в редакторе, записываются в файл с именем *CMakeSettings.json*. Этот файл предоставляет аргументы командной строки и переменные среды, передаваемые CMake при сборке проектов. Visual Studio никогда не изменяет файл *CMakeLists.txt* автоматически. Посредством *CMakeSettings.json* вы можете настроить сборку в Visual Studio, не изменяя файлы проекта CMake, чтобы другие члены вашей команды использовали их с помощью любых инструментов.

## <a name="cmake-general-settings"></a>Общие параметры CMake

Следующие параметры доступны под заголовком **Общие**:

### <a name="configuration-name"></a>Имя конфигурации

Соответствует параметру **name**. Это имя отображается в раскрывающемся списке конфигураций C++. Вы можете использовать макрос `${name}` для создания других значений свойств, например путей.

### <a name="configuration-type"></a>Тип конфигурации

Соответствует параметру **configurationType**. Определяет тип конфигурации сборки для выбранного генератора. Сейчас поддерживаются значения Debug, MinSizeRel, Release и RelWithDebInfo. Сопоставляется с [CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html).

### <a name="toolset"></a>Набор инструментов

Соответствует параметру **inheritedEnvironments**. Определяет среду компилятора, которая используется для сборки выбранной конфигурации. Поддерживаемые значения зависят от типа конфигурации. Чтобы создать пользовательскую среду, щелкните ссылку **Изменить JSON** в правом верхнем углу редактора параметров и измените файл *CMakeSettings.json* напрямую.

### <a name="cmake-toolchain-file"></a>Файл цепочки инструментов CMake

Путь к [файлу цепочки инструментов CMake](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html). Этот путь передается в CMake как -DCMAKE_TOOLCHAIN_FILE = \<filepath>. В файлах цепочки инструментов указывается расположение компиляторов и служебных программ цепочки, а также прочая информация о компиляторах и целевых платформах. Если этот параметр не задан, по умолчанию Visual Studio использует [файл цепочки инструментов vcpkg](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake).

### <a name="build-root"></a>Корневой путь к сборке

Соответствует **buildRoot**. Сопоставляется с параметром [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html) и указывает, где будет создан кэш CMake. Если указанная папка не существует, она будет создана.

## <a name="command-arguments"></a>аргументы команды.

Следующие параметры доступны под заголовком **Аргументы команд**:

### <a name="cmake-command-arguments"></a>Аргументы команд CMake

Соответствует **cmakeCommandArgs**. Задает дополнительные [параметры командной строки](https://cmake.org/cmake/help/latest/manual/cmake.1.html), передаваемые в CMake.exe.

### <a name="build-command-arguments"></a>Аргументы команд сборки

Соответствует **buildCommandArgs**. Указывает дополнительные параметры, передаваемые базовой системе сборки. Например, передача `-v` при использовании генератора Ninja приводит к тому, что Ninja выдает командные строки.

### <a name="ctest-command-arguments"></a>Аргументы команд CTest

Соответствует **ctestCommandArgs**. Задает дополнительные [параметры командной строки](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html), передаваемые CTest при запуске тестов.

## <a name="general-settings-for-remote-builds"></a>Общие параметры для удаленных сборок

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="rsync-command-arguments"></a>Аргументы команды rsync

Дополнительные параметры командной строки, передаваемые в [rsync](https://download.samba.org/pub/rsync/rsync.html), быстрое и универсальное средство копирования файлов.

## <a name="cmake-variables-and-cache"></a>Переменные и кэш CMake

Эти параметры позволяют задать переменные CMake и сохранить их в *CMakeSettings.json*. Они передаются в CMake во время сборки и переопределяют любые значения в файле *CMakeLists.txt*. Этот раздел можно использовать так же, как вы используете CMakeGUI для просмотра списка всех доступных для изменения переменных CMake. Нажмите кнопку **Сохранить и создать кэш**, чтобы просмотреть список всех переменных CMake, доступных для редактирования, включая дополнительные переменные (для CMakeGUI). Вы можете отфильтровать список по имени переменной.

Соответствует **variables**. Содержит пару "имя-значение" для переменных CMake, которая передается в CMake в виде **-D** *_имя_=_значение_* . Если инструкции сборки проекта CMake указывают добавление каких-либо переменных непосредственно в файл кэша CMake, рекомендуется вместо этого добавить их сюда.

## <a name="advanced-settings"></a>Дополнительные параметры

### <a name="cmake-generator"></a>Генератор CMake

Соответствует **generator**. Сопоставляется с параметром **-G** в CMake и задает используемый [генератор CMake](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html). Это свойство можно также использовать как макрос `${generator}`, чтобы задать другие значения свойств. Сейчас Visual Studio поддерживает следующие генераторы CMake:

- Ninja
- "Unix Makefiles"
- "Visual Studio 16 2019"
- "Visual Studio 16 2019 Win64"
- "Visual Studio 16 2019 ARM"
- Visual Studio 15 2017
- Visual Studio 15 2017 Win64
- Visual Studio 15 2017 ARM
- Visual Studio 14 2015
- Visual Studio 14 2015 Win64
- Visual Studio 14 2015 ARM
  
Так как генератор Ninja предназначен для ускорения сборки в ущерб гибкости и функциональности, он используется по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно указать CMake, что необходимо создать проект Visual Studio.

### <a name="intellisense-mode"></a>Режим IntelliSense

Режим, используемый подсистемой IntelliSense. Если он не выбран, Visual Studio наследует режим от указанного набора инструментов.  

### <a name="install-directory"></a>Каталог установки

Каталог, в котором CMake устанавливает целевые объекты. Соответствует [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html).

### <a name="cmake-executable"></a>Исполняемый файл CMake

Полный путь к исполняемому файлу программы CMake, включая имя файла и расширение. Позволяет использовать настраиваемую версию CMake с Visual Studio. Для удаленных сборок укажите расположение CMake на удаленном компьютере.

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="remote-cmakeliststxt-root"></a>Удаленный корневой каталог CMakeLists.txt

Каталог на удаленном компьютере, который содержит корневой файл *CMakeLists.txt*.

### <a name="remote-install-root"></a>Удаленный корневой каталог установки

Каталог на удаленном компьютере, в который CMake устанавливает целевые объекты. Соответствует [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html).

### <a name="remote-copy-sources"></a>Удаленное копирование источников

Указывает, следует ли копировать исходные файлы на удаленный компьютер, и позволяет указать, следует ли использовать rsync или sftp.

## <a name="directly-edit-cmakesettingsjson"></a>Прямое изменение CMakeSettings.json

Вы также можете напрямую изменить *CMakeSettings.json* для создания настраиваемых конфигураций. В **редакторе параметров** есть кнопка **Изменить JSON** в правом верхнем углу, которая открывает файл для редактирования.

Ниже приведен пример конфигурации, который можно использовать в качестве отправной точки:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense помогает изменить файл *CMakeSettings.json*:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Редактор JSON также уведомляет о выборе несовместимых параметров.

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 предоставляет несколько конфигураций CMake, которые определяют, как вызывается CMake.exe для создания кэша CMake для данного проекта. Чтобы добавить новую конфигурацию, щелкните раскрывающийся список конфигурации на панели инструментов и выберите **Управление конфигурациями**.

   ![Управление конфигурациями CMake](media/cmake-manage-configurations.png)

Можно выбрать из списка стандартных конфигураций:

   ![Предопределенные конфигурации CMake](media/cmake-configurations.png)

При первом выборе конфигурации Visual Studio создает файл *CMakeSettings.json* в корневой папке проекта. Этот файл используется для повторного создания файла кэша CMake, например после операции **Очистить**.

Чтобы добавить дополнительную конфигурацию, щелкните правой кнопкой мыши файл *CMakeSettings.json* и выберите пункт **Добавить конфигурацию**.

   ![Добавление конфигурации CMake](media/cmake-add-configuration.png "Добавление конфигурации CMake")

Можно также изменить файл с помощью **редактора параметров CMake**. В **обозревателе решений** щелкните правой кнопкой мыши файл *CMakeSettings.json* и выберите пункт **Изменить параметры CMake**. Или выберите **Управление конфигурациями** из раскрывающегося списка конфигурации в верхней части окна редактора.

Вы также можете напрямую изменить *CMakeSettings.json* для создания настраиваемых конфигураций. Ниже приведен пример конфигурации, который можно использовать в качестве отправной точки:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense помогает изменить файл *CMakeSettings.json*:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)
