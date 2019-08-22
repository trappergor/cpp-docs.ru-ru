---
title: Настройка параметров сборки CMake в Visual Studio
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: ecd2964e035cbf3d48a737164b0067720e9b6b9a
ms.sourcegitcommit: 0df462d79ad617296095c3012badc2fe669bab2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69887059"
---
# <a name="customize-cmake-build-settings"></a>Настройка параметров сборки CMake

::: moniker range="vs-2019"

В Visual Studio 2019 и более поздних версий можно добавлять конфигурации и настраивать их параметры с помощью **редактора параметров CMake**. Редактор предназначен для более простой альтернативы изменению файла *CMakeSettings. JSON* вручную, но если вы предпочитаете редактировать файл напрямую, щелкните ссылку **изменить JSON** в правом верхнем углу редактора. 

Чтобы открыть редактор, перейдите в раскрывающееся меню **Конфигурация** на главной панели инструментов и выберите **Управление конфигурациями**.

![Раскрывающийся список конфигураций CMake](media/vs2019-cmake-manage-configurations.png)

Откроется **редактор параметров** с установленными конфигурациями слева. 

![Редактор параметров CMake](media/cmake-settings-editor.png)

По умолчанию Visual `x64-Debug` Studio предоставляет одну конфигурацию. Можно добавить дополнительные конфигурации, щелкнув зеленый знак «плюс». Параметры, отображаемые в редакторе, могут различаться в зависимости от выбранной конфигурации.

Параметры, выбираемые в редакторе, записываются в файл с именем *CMakeSettings. JSON*. Этот файл предоставляет аргументы командной строки и переменные среды, передаваемые CMake при сборке проектов. Visual Studio автоматически не изменяет *CMakeLists. txt* . с помощью *CMakeSettings. JSON* можно настроить сборку в Visual Studio, сохранив файлы проекта CMAK без изменений, чтобы другие участники вашей команды могли использовать их со всеми используемыми инструментами.

## <a name="cmake-general-settings"></a>Общие параметры CMake

Следующие параметры доступны под заголовком **Общие**:

### <a name="configuration-name"></a>Имя конфигурации

Соответствует параметру **name**. Это имя появится в раскрывающемся списке C++ конфигурация. Вы можете использовать макрос `${name}` для создания других значений свойств, например путей.


### <a name="configuration-type"></a>Тип конфигурации

Соответствует параметру **configurationType**. Определяет тип конфигурации сборки для выбранного генератора. Сейчас поддерживаются значения Debug, MinSizeRel, Release и RelWithDebInfo. Он сопоставляется с [CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html).

### <a name="toolset"></a>Набор инструментов

Соответствует параметру **inheritedEnvironments**. Определяет среду компилятора, используемую для построения выбранной конфигурации. Поддерживаемые значения зависят от типа конфигурации. Чтобы создать пользовательскую среду, щелкните ссылку **изменить JSON** в правом верхнем углу редактора параметров и непосредственно измените файл *CMakeSettings. JSON* .

### <a name="cmake-toolchain-file"></a>Файл цепочки инструментов CMake

Путь к [файлу цепочки инструментов CMAK](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html). Этот путь передается в CMAK как "-DCMAKE_TOOLCHAIN_FILE = \<FilePath >". Файлы цепочки инструментов указывают расположение компиляторов и служебных программ цепочки инструментов, а другая целевая платформа и сведения, связанные с компилятором. По умолчанию Visual Studio использует [файл цепочки инструментов vcpkg](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake) , если этот параметр не задан. 

### <a name="build-root"></a>Корневой путь к сборке

Соответствует **buildRoot**. Сопоставляется с [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)и указывает, где следует создать кэш CMAK. Указанная папка создается, если она не существует.

## <a name="command-arguments"></a>Аргументы команд

Следующие параметры доступны под заголовком **Аргументы команд**:

### <a name="cmake-command-arguments"></a>Аргументы команд CMake

Соответствует **cmakeCommandArgs**. Указывает все дополнительные [Параметры командной строки](https://cmake.org/cmake/help/latest/manual/cmake.1.html) , передаваемые в CMAK. exe.

### <a name="build-command-arguments"></a>Аргументы команд сборки

Соответствует **буилдкоммандаргс**. Указывает дополнительные параметры для передачи в базовую систему сборки. Например, передача `-v` при использовании генератора Ninja заставляет Ninja выводить командные строки.


### <a name="ctest-command-arguments"></a>Аргументы команд CTest

Соответствует **ктесткоммандаргс**. Задает дополнительные [Параметры командной строки](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html) для передачи в CTest при выполнении тестов.

## <a name="general-settings-for-remote-builds"></a>Общие параметры для удаленных сборок

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="rsync-command-arguments"></a>Аргументы команды rsync

Дополнительные параметры командной строки, передаваемые в [rsync](https://download.samba.org/pub/rsync/rsync.html), быстрое и гибкое средство копирования файлов. 

## <a name="cmake-variables-and-cache"></a>Переменные и кэш CMake

Эти параметры позволяют задавать переменные CMak и сохранять их в *CMakeSettings. JSON*. Они передаются в CMak во время сборки и переопределяют, какие значения находятся в файле *CMakeLists. txt* . Этот раздел можно использовать так же, как вы используете CMakeGUI для просмотра списка всех доступных для изменения переменных CMake. Нажмите кнопку **Сохранить и создать кэш**, чтобы просмотреть список всех переменных CMake, доступных для редактирования, включая дополнительные переменные (для CMakeGUI). Список можно отфильтровать по имени переменной. 

Соответствует **переменным**. Содержит пару «имя-значение» переменных CMAK, переданных в качестве *_значения_ _имени_=* **D** в CMAK. Если в инструкциях по сборке проекта CMak указано Добавление переменных непосредственно в файл кэша CMak, рекомендуется добавить их здесь.

## <a name="advanced-settings"></a>Дополнительные параметры

### <a name="cmake-generator"></a>Генератор CMake

Соответствует **генератору**. Сопоставляется с параметром CMak **-G** и указывает используемый [генератор CMAK](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) . Это свойство можно также использовать как макрос `${generator}`, чтобы задать другие значения свойств. Сейчас Visual Studio поддерживает следующие генераторы CMake:

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
  
Поскольку Ninja разрабатывается для ускорения сборки, а не гибкости и функций, он устанавливается в качестве значения по умолчанию. Однако некоторые проекты CMake могут быть неспособны использовать Ninja правильно. В этом случае можно указать, что CMak должен создать проект Visual Studio.

### <a name="intellisense-mode"></a>Режим IntelliSense

Режим IntelliSense, используемый ядром IntelliSense. Если режим не выбран, Visual Studio будет наследовать из указанного набора инструментов.  

### <a name="install-directory"></a>Каталог установки

Каталог, в котором устанавливаются целевые объекты CMak. Сопоставляется с [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html). 

### <a name="cmake-executable"></a>Исполняемый файл CMake

Полный путь к исполняемому файлу программы CMak, включая имя файла и расширение. Она позволяет использовать настраиваемую версию CMak с Visual Studio. Для удаленных сборок укажите расположение CMake на удаленном компьютере.

Для таких конфигураций, как Linux, которые используют удаленные сборки, также доступны следующие параметры:

### <a name="remote-cmakeliststxt-root"></a>Удаленный корневой каталог CMakeLists.txt

Каталог на удаленном компьютере, который содержит корневой файл *CMakeLists. txt* .

### <a name="remote-install-root"></a>Удаленный корневой каталог установки

Каталог на удаленном компьютере, в который CMake устанавливает целевые объекты. Сопоставляется с [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html). 

### <a name="remote-copy-sources"></a>Удаленное копирование источников

Указывает, следует ли копировать исходные файлы на удаленный компьютер, и позволяет указать, следует ли использовать rsync или SFTP. 

## <a name="directly-edit-cmakesettingsjson"></a>Прямое изменение CMakeSettings.json

Вы также можете напрямую отредактировать *CMakeSettings. JSON* для создания пользовательских конфигураций. В **редакторе параметров** есть кнопка **Изменить JSON** в правом верхнем углу, которая открывает файл для редактирования. 

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

Технология JSON IntelliSense позволяет редактировать файл *CMakeSettings. JSON* :

   ![JSON IntelliSense CMake](media/cmake-json-intellisense.png "JSON IntelliSense CMake")

Редактор JSON также информирует вас о выборе несовместимых параметров.

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 предоставляет несколько конфигураций CMake, которые определяют, как вызывается CMake.exe для создания кэша CMake для данного проекта. Чтобы добавить новую конфигурацию, щелкните раскрывающийся список конфигурации на панели инструментов и выберите **Управление конфигурациями**.

   ![Управление конфигурациями CMake](media/cmake-manage-configurations.png)

Можно выбрать из списка стандартных конфигураций:

   ![Предопределенные конфигурации CMake](media/cmake-configurations.png)

При первом выборе конфигурации Visual Studio создает файл *CMakeSettings. JSON* в корневой папке проекта. Этот файл используется для повторного создания файла кэша CMake, например после операции **Очистить**. 

Чтобы добавить дополнительную конфигурацию, щелкните правой кнопкой мыши *CMakeSettings. JSON* и выберите **Добавить конфигурацию**. 

   ![Добавление конфигурации CMake](media/cmake-add-configuration.png "Добавление конфигурации CMake")

Можно также изменить файл с помощью **редактора параметров CMake**. Щелкните правой кнопкой мыши *CMakeSettings. JSON* в **Обозреватель решений** и выберите **изменить параметры CMAK**. Или выберите **Управление конфигурациями** из раскрывающегося списка конфигурации в верхней части окна редактора. 

Вы также можете напрямую отредактировать *CMakeSettings. JSON* для создания пользовательских конфигураций. Ниже приведен пример конфигурации, который можно использовать в качестве отправной точки:

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

Технология JSON IntelliSense позволяет редактировать файл *CMakeSettings. JSON* :

   ![JSON IntelliSense CMake](media/cmake-json-intellisense.png "JSON IntelliSense CMake")

Дополнительные сведения обо всех свойствах в файле см. в разделе [Справочник по схеме CMakeSettings.json](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)
