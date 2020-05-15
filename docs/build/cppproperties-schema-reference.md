---
title: Справочник по CppProperties.json
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: be6db52e1e62244e9f44db8ac86238242ab50ca0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328722"
---
# <a name="cpppropertiesjson-reference"></a>Справочник по CppProperties.json

Проекты Open Folder, не использующие CMake, могут хранить параметры конфигурации проекта для IntelliSense в файле *CppProperties.json*. (Проекты CMake используют файл [CMakeSettings.json](customize-cmake-settings.md).) Конфигурация состоит из пар имя-значение и определяет пути #include, параметры компилятора и другие параметры. Дополнительные сведения о добавлении конфигураций в проект Open Folder см. в разделе [Проекты Open Folder для C++](open-folder-projects-cpp.md). В следующих разделах приводятся общие сведения о различных параметрах. Полное описание схемы см. в файле *CppProperties_schema.json*, полный путь к которому указан в верхней части редактора кода при открытии файла *CppProperties.json*.

## <a name="configuration-properties"></a>Свойства конфигурации

Конфигурация может иметь любое из следующих свойств:

|||
|-|-|
|`inheritEnvironments`| Указывает, какие среды применяются к этой конфигурации.|
|`name`|Имя конфигурации, которое будет отображаться в раскрывающемся списке конфигурации C++|
|`includePath`|Список папок, указанных через запятую, которые нужно указать в пути включения (для большинства компиляторов сопоставляется с /I)|
|`defines`|Список макросов, которые нужно определить (для большинства компиляторов сопоставляется с /D)|
|`compilerSwitches`|Один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense|
|`forcedInclude`|Заголовок, автоматически включаемый в каждый блок компиляции (сопоставляется с /FI для MSVC или с -include для clang)|
|`undefines`|Список макросов, которые должны быть неопределенными (сопоставляется с /U для MSVC)|
|`intelliSenseMode`|Используемая подсистема IntelliSense. Для MSVC, gcc или Clang можно указать один их предварительно заданных вариантов для конкретной архитектуры.|
|`environments`|Определяемые пользователем наборы переменных, которые ведут себя как переменные среды в командной строке и доступны с помощью макроса ${env.\<VARIABLE>}.|

### <a name="intellisensemode-values"></a>Значения intelliSenseMode

В редакторе кода доступные параметры отображаются при начале ввода:

![Open Folder IntelliSense](media/open-folder-intellisense-mode.png "Open Folder IntelliSense")

Поддерживаются следующие значения:

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

Примечание. Значения `msvc-x86` и `msvc-x64` поддерживаются только для обеспечения обратной совместимости. Вместо этого используйте варианты `windows-msvc-*`.

## <a name="pre-defined-environments"></a>Предварительно заданные среды

Visual Studio предоставляет следующие стандартные среды для Microsoft C++, которые сопоставляются с соответствующей командной строкой разработчика. При наследовании одной из этих сред можно ссылаться на любую из переменных среды, используя глобальное свойство `env` с этим синтаксисом макроса: ${env.\<VARIABLE>}.

|Имя переменной|Описание|
|-----------|-----------------|
|vsdev|Среда Visual Studio по умолчанию|
|msvc_x86|Компиляция для x86 с помощью средств x86|
|msvc_x64|Компиляция для AMD64 с помощью 64-разрядных средств|
|msvc_arm|Компиляция для ARM с помощью средств x86|
|msvc_arm64|Компиляция для ARM64 с помощью средств x86|
|msvc_x86_x64|Компиляция для AMD64 с помощью средств x86|
|msvc_arm_x64|Компиляция для ARM с помощью 64-разрядных средств|
|msvc_arm64_x64|Компиляция для ARM64 с помощью 64-разрядных средств|

При установке рабочей нагрузки Linux для удаленной ориентации на Linux и WSL доступны следующие среды.

|Имя переменной|Описание|
|-----------|-----------------|
|linux_x86|Удаленная ориентация на Linux x86|
|linux_x64|Удаленная ориентация на Linux x64|
|linux_arm|Удаленная ориентация на Linux ARM|

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a> Определяемые пользователем среды

Можно воспользоваться свойством `environments`, чтобы определить в файле *CppProperties.json* пользовательские переменные среды либо глобально, либо для отдельных конфигураций. Эти переменные ведут себя как переменные среды в контексте проекта Open Folder. Доступ к ним можно получить с помощью синтаксиса ${env.\<VARIABLE>} из файлов *tasks.vs.json* и *launch.vs.json* после их определения. Однако они необязательно задаются в качестве фактических переменных среды в любой командной строке, используемой Visual Studio для внутренних целей.

**Visual Studio 2019 версии 16.4 и более поздней:** зависящие от конфигурации переменные, определенные в *CppProperties.json*, автоматически выбираются целевыми объектами и задачами отладки без необходимости задания `inheritEnvironments`. Целевые объекты отладки автоматически запускаются в среде, указанной в *CppProperties.json*.

**Visual Studio 2019 версии 16.3 и более ранней:** При использовании среды необходимо указать ее в свойстве `inheritsEnvironments`, даже если среда определена как часть той же конфигурации; свойство `environment` указывает имя среды. Ниже приведен пример конфигурации для включения IntelliSense для GCC в установке MSYS2. Обратите внимание, что конфигурация определяет и наследует среду `mingw_64`, а также то, как свойство `includePath` может получить доступ к переменной `INCLUDE`.

```json
"configurations": [
    {

      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath ,": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**",
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR};",
          "environment": "mingw_64"
        }
      ]
    }
  ]
```

При определении свойства **среды** в конфигурации оно переопределяет все глобальные переменные с таким же именем.

## <a name="built-in-macros"></a>Встроенные макросы

В *CppProperties.json* доступны следующие встроенные макросы:

|||
|-|-|
|`${workspaceRoot}`| полный путь к папке рабочей области;|
|`${projectRoot}`| полный путь к папке, где находится *CppProperties.json*;|
|`${env.vsInstallDir}`| полный путь к папке, где установлен запущенный экземпляр Visual Studio.|

### <a name="example"></a>Пример

Если проект имеет папку включения, а также включает *windows.h* и другие общие заголовки из Windows SDK, может потребоваться обновить файл конфигурации *CppProperties.json* с учетом этих включений.

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%` и `%VCToolsInstallDir%` не заданы в качестве глобальных переменных среды, поэтому запустите из командной строки разработчика программу devenv.exe, определяющую эти переменные. (Введите "разработчик" в меню Windows "Пуск".)

## <a name="troubleshoot-intellisense-errors"></a>Устранение ошибок IntelliSense

Если вы не видите IntelliSense, как ожидалось, можно устранить неполадки, выбрав **Сервис** > **Параметры** > **Текстовый редактор** > **C/C++**  > **Дополнительно** и установив для параметра **Включить ведение журнала** значение **true**. Для начала задайте для параметра **Уровень ведения журнала** значение 5, а для параметра **Фильтры ведения журнала** — значение 8.

![Ведение журналов диагностики](media/diagnostic-logging.png)

Выходные данные направляются в **окно вывода** и отображаются при выборе **Показать выходные данные из: журнал Visual C++** . Выходные данные содержат, помимо прочего, список фактических путей включения, которые IntelliSense пытается использовать. Если пути не совпадают с путями в *CppProperties.json*, закройте папку и удалите вложенную папку *.vs*, которая содержит кэшированные данные обзора.

Для устранения ошибок IntelliSense, вызванных отсутствием путей включения, откройте **Список ошибок** и отфильтруйте выходные данные до "Только IntelliSense" и кода ошибки E1696 "Не удается открыть исходный файл...".
