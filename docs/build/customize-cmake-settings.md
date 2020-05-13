---
title: Настройка параметров сборки CMake в Visual Studio
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: c6bd1404799ccc9ad6b689646cd066849d48fca8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328681"
---
# <a name="customize-cmake-build-settings"></a>Настройка параметров сборки CMake

::: moniker range="vs-2019"

В Visual Studio 2019 и более поздних версий можно добавлять конфигурации и настраивать их параметры с помощью **редактора параметров CMake**. Редактор предназначен для более простой альтернативы вручную редактированию файла *CMakeSettings.json,* но если вы предпочитаете редактировать файл напрямую, вы можете нажать на ссылку **Edit JSON** в правом верхнем углу редактора.

Чтобы открыть редактор, перейдите в раскрывающееся меню **Конфигурация** на главной панели инструментов и выберите **Управление конфигурациями**.

![Раскрывающийся список конфигураций CMake](media/vs2019-cmake-manage-configurations.png)

Откроется **редактор параметров** с установленными конфигурациями слева.

![Редактор параметров CMake](media/cmake-settings-editor.png)

Visual Studio `x64-Debug` предоставляет одну конфигурацию по умолчанию. Вы можете добавить дополнительные конфигурации, нажав зеленый знак плюс. Настройки, которые можно увидеть в редакторе, могут варьироваться в зависимости от выбранной конфигурации.

Параметры, которые вы выбираете в редакторе, записываются в файл под названием *CMakeSettings.json.* Этот файл предоставляет аргументы командной строки и переменные среды, передаваемые CMake при сборке проектов. Visual Studio никогда не изменяет *CMakeLists.txt* автоматически; с помощью *CMakeSettings.json* вы можете настроить сборку через Visual Studio, оставляя файлы проекта CMake нетронутыми, чтобы другие члены вашей команды могли использовать их с любыми инструментами, которые они используют.

## <a name="cmake-general-settings"></a>Общие параметры CMake

Следующие параметры доступны под заголовком **Общие**:

### <a name="configuration-name"></a>Имя конфигурации

Соответствует параметру **name**. Это имя отображается в отпадении конфигурации СЗ. Вы можете использовать макрос `${name}` для создания других значений свойств, например путей.

### <a name="configuration-type"></a>Тип конфигурации

Соответствует параметру **configurationType**. Определяет тип конфигурации сборки для выбранного генератора. Сейчас поддерживаются значения Debug, MinSizeRel, Release и RelWithDebInfo. Он карты для [CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html).

### <a name="toolset"></a>Набор инструментов

Соответствует параметру **inheritedEnvironments**. Определяет среду компилятора, используемую для построения выбранной конфигурации. Поддерживаемые значения зависят от типа конфигурации. Чтобы создать пользовательскую среду, выберите ссылку **Edit JSON** в правом верхнем углу редактора «Настройки» и отредактируйте файл *CMakeSettings.json* напрямую.

### <a name="cmake-toolchain-file"></a>Файл цепочки инструментов CMake

Путь к [файлу инструментария CMake.](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html) Этот путь передается CMake как \<"-DCMAKE_TOOLCHAIN_FILE и filepath>". Файлы Toolchain определяют местоположение компиляторов и утилит, связанных с набором инструментов, а также другую целевую платформу и информацию, связанную с компилятором. По умолчанию Visual Studio использует [файл инструментария vcpkg,](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake) если эта настройка не определена.

### <a name="build-root"></a>Корневой путь к сборке

Соответствует **buildRoot**. Карты для [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)и определяет, где создать кэш CMake. Указанная папка создается, если она не существует.

## <a name="command-arguments"></a>аргументы команды.

Следующие параметры доступны под заголовком **Аргументы команд**:

### <a name="cmake-command-arguments"></a>Аргументы команд CMake

Соответствует **cmakeCommandArgs**. Определяет любые дополнительные [параметры командной строки,](https://cmake.org/cmake/help/latest/manual/cmake.1.html) передаваемые CMake.exe.

### <a name="build-command-arguments"></a>Аргументы команд сборки

Соответствует **построитьКомендантСарги**. Определяет дополнительные коммутаторы для перехода в базовую систему сборки. Например, `-v` прохождение при использовании генератора Ninja заставляет Ninja вывести командные линии.

### <a name="ctest-command-arguments"></a>Аргументы команд CTest

Соответствует **ctestCommandArgs**. Определяет дополнительные [параметры командной строки](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html) для передачи cTest при проведении тестов.

## <a name="general-settings-for-remote-builds"></a>Общие параметры для удаленных сборок

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="rsync-command-arguments"></a>Аргументы команды rsync

Дополнительные параметры командной строки перешли в [rsync](https://download.samba.org/pub/rsync/rsync.html), быстрый и универсальный инструмент копирования файлов.

## <a name="cmake-variables-and-cache"></a>Переменные и кэш CMake

Эти параметры позволяют установить переменные CMake и сохранить их в *CMakeSettings.json.* Они передаются CMake во время сборки и переопределяют все значения, которые есть в файле *CMakeLists.txt.* Этот раздел можно использовать так же, как вы используете CMakeGUI для просмотра списка всех доступных для изменения переменных CMake. Нажмите кнопку **Сохранить и создать кэш**, чтобы просмотреть список всех переменных CMake, доступных для редактирования, включая дополнительные переменные (для CMakeGUI). Можно отфильтровать список по имени переменной.

Соответствует **переменным.** Содержит пару значений имен переменных CMake, передаваемую как значение * _имени_=* **- D** для CMake. Если инструкции по сборке проекта CMake указывают добавление любых переменных непосредственно в файл кэша CMake, мы рекомендуем добавить их здесь.

## <a name="advanced-settings"></a>Дополнительные параметры

### <a name="cmake-generator"></a>Генератор CMake

Соответствует **генератору.** Карты для **cMake-G** переключатель, и определяет [генератор CMake](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) для использования. Это свойство можно также использовать как макрос `${generator}`, чтобы задать другие значения свойств. Сейчас Visual Studio поддерживает следующие генераторы CMake:

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
  
Поскольку Ninja предназначен для быстрых скоростей сборки, а не для гибкости и функции, он установлен по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. Если это происходит, вы можете поручить CMake создать проект Visual Studio.

### <a name="intellisense-mode"></a>Режим IntelliSense

Режим IntelliSense, используемый движком IntelliSense. Если режим не выбран, Visual Studio унаследует из указанного набора инструментов.  

### <a name="install-directory"></a>Каталог установки

Каталог, в котором CMake устанавливает цели. Карты для [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html).

### <a name="cmake-executable"></a>Исполняемый файл CMake

Полный путь к исполняемой программе CMake, включая имя файла и расширение. Это позволяет использовать пользовательскую версию CMake с Visual Studio. Для удаленных сборок укажите расположение CMake на удаленном компьютере.

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="remote-cmakeliststxt-root"></a>Удаленный корневой каталог CMakeLists.txt

Каталог на удаленной машине, содержащей корневой файл *CMakeLists.txt.*

### <a name="remote-install-root"></a>Удаленный корневой каталог установки

Каталог на удаленном компьютере, в который CMake устанавливает целевые объекты. Карты для [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html).

### <a name="remote-copy-sources"></a>Удаленное копирование источников

Определяет, следует ли копировать исходные файлы на удаленной машине, и позволяет указать, следует ли использовать rsync или sftp.

## <a name="directly-edit-cmakesettingsjson"></a>Прямое изменение CMakeSettings.json

Вы также можете непосредственно отойти от *CMakeSettings.json* для создания пользовательских конфигураций. В **редакторе параметров** есть кнопка **Изменить JSON** в правом верхнем углу, которая открывает файл для редактирования.

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

JSON IntelliSense поможет вам отсеить файл *CMakeSettings.json:*

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Редактор JSON также информирует вас о выборе несовместимых настроек.

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 предоставляет несколько конфигураций CMake, которые определяют, как вызывается CMake.exe для создания кэша CMake для данного проекта. Чтобы добавить новую конфигурацию, щелкните раскрывающийся список конфигурации на панели инструментов и выберите **Управление конфигурациями**.

   ![Управление конфигурациями CMake](media/cmake-manage-configurations.png)

Можно выбрать из списка стандартных конфигураций:

   ![Предопределенные конфигурации CMake](media/cmake-configurations.png)

При первом выборе конфигурации Visual Studio создает файл *CMakeSettings.json* в корневой папке проекта. Этот файл используется для повторного создания файла кэша CMake, например после операции **Очистить**.

Чтобы добавить дополнительную конфигурацию, нажмите *cMakeSettings.json* и выберите **Добавить конфигурацию.**

   ![Конфигурация CMake Add](media/cmake-add-configuration.png "Конфигурация CMake Добавить")

Можно также изменить файл с помощью **редактора параметров CMake**. Нажмите на *CMakeSettings.json* в **Solution Explorer** и выберите **настройки Edit CMake.** Или выберите **Управление конфигурациями** из раскрывающегося списка конфигурации в верхней части окна редактора.

Вы также можете непосредственно отойти от *CMakeSettings.json* для создания пользовательских конфигураций. Ниже приведен пример конфигурации, который можно использовать в качестве отправной точки:

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

JSON IntelliSense поможет вам отсеить файл *CMakeSettings.json:*

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>См. также раздел

[Проекты CMake в визуальной студии](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)
