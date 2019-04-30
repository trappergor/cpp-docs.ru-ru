---
title: Справочник по схеме CppProperties.json
ms.date: 03/21/2019
helpviewer_keywords:
- CMake in Visual C++
ms.openlocfilehash: 43ffa0e92649fe233c6a743d4b64a2749cb28f5a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341644"
---
# <a name="cpppropertiesjson-schema-reference"></a>Справочник по схеме CppProperties.json

Проекты "Открыть папку", не использующие CMake, могут хранить параметры конфигурации проекта в файле `CppProperties.json`. (Проекты CMake используют файл [CMakeSettings.json](customize-cmake-settings.md).) Интегрированная среда разработки Visual Studio IDE использует `CppProperties.json` для навигации по коду и IntelliSense. Конфигурация состоит из пар имя-значение и определяет пути #include, параметры компилятора и другие параметры. 


## <a name="default-configurations"></a>Конфигурации по умолчанию

Visual Studio предоставляет предопределенные конфигурации для отладки и выпуска x86 и x64. По умолчанию ваш проект имеет конфигурацию отладки x86-Debug в `CppProperties.json`. Чтобы добавить новую конфигурацию, в **обозревателе решений** щелкните правой кнопкой мыши файл `CppProperties.json` и выберите команду **Добавить конфигурацию**:

![Добавление конфигурации для проекта "Открыть папку"](media/open-folder-add-config.png "Добавление конфигурации для проекта \"Открыть папку\"")

Конфигурации по умолчанию показаны ниже:

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
Для свойства, имеющих набор допустимых значений, редактор кода отображает доступные варианты, когда вы начинаете вводить данные:

![IntelliSense для проекта "Открыть папку"](media/open-folder-intellisense-mode.png "IntelliSense для проекта \"Открыть папку\"")



## <a name="configuration-properties"></a>Свойства конфигурации

Конфигурация может иметь любое из следующих свойств:

|||
|-|-|
|`name`|Имя конфигурации, которое отображается в раскрывающемся списке конфигурации C++|
|`includePath`|Список папок, которые нужно указать в пути включения (для большинства компиляторов сопоставляется с /I)|
|`defines`|Список макросов, которые нужно определить (для большинства компиляторов сопоставляется с /D)|
|`compilerSwitches`|Один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense|
|`forcedInclude`|Заголовок, автоматически включаемый в каждый блок компиляции (сопоставляется с /FI для MSVC или с -include для clang)|
|`undefines`|Список макросов, которые должны быть неопределенными (сопоставляется с /U для MSVC)|
|`intelliSenseMode`|Используемая подсистема IntelliSense. Для MSVC, gcc или Clang вы можете указать варианты, привязанные к конкретной архитектуре:<br/><br/>— windows — msvc-x86 (по умолчанию)<br/>- windows-msvc-x64<br/>- msvc-arm<br/>- windows-clang-x86<br/>- windows-clang-x64<br/>- windows-clang-arm<br/>- Linux-x64<br/>- Linux-x86<br/>- Linux-arm<br/>- gccarm|

Примечание. Значения `msvc-x86` и `msvc-x64` поддерживаются для обеспечения обратной совместимости. Используйте `windows-msvc*` вариантов.

## <a name="custom-configurations"></a>Настраиваемые конфигурации


Вы можете настроить любую из конфигураций по умолчанию в `CppProperties.json` либо создать новые конфигурации. Каждая из них будет отображаться в раскрывающемся списке конфигурации.

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```

## <a name="system-environment-variables"></a>Системные переменные среды 

 `CppProperties.json` поддерживает расширение системных переменных среды для путей включения и других значений свойств. Для расширения переменной среды `%FOODIR%` используется синтаксис `${env.FOODIR}`. Кроме того, поддерживаются следующие системные переменные.

|Имя переменной|Описание|
|-----------|-----------------|
|vsdev|Среда Visual Studio по умолчанию|
|msvc_x86|Компиляция для x86 с помощью средств x86|
|msvc_arm|Компиляция для ARM с помощью средств x86|
|msvc_arm64|Компиляция для ARM64 с помощью средств x86|
|msvc_x86_x64|Компиляция для AMD64 с помощью средств x86|
|msvc_x64_x64|Компиляция для AMD64 с помощью 64-разрядных средств|
|msvc_arm_x64|Компиляция для ARM с помощью 64-разрядных средств|
|msvc_arm64_x64|Компиляция для ARM64 с помощью 64-разрядных средств|

При установке рабочей нагрузки Linux для удаленной ориентации на Linux и WSL доступны следующие среды.

|Имя переменной|Описание|
|-----------|-----------------|
|linux_x86|Удаленная ориентация на Linux x86|
|linux_x64|Удаленная ориентация на Linux x64|
|linux_arm|Удаленная ориентация на Linux ARM|

## <a name="custom-environment-variables"></a>Пользовательские переменные среды

В `CppProperties.json` можно определить пользовательские переменные среды либо глобально, либо для отдельных конфигураций. В примере ниже показано, как можно объявить и использовать стандартные и пользовательские переменные среды. Глобальное свойство **environments** объявляет переменную **INCLUDE**, которую может использовать любая конфигурация:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
## <a name="per-configuration-environment-variables"></a>Переменные среды для отдельных конфигураций

Вы также можете определить свойство **environments** внутри конфигурации, чтобы оно применялось только к ней и переопределяло все глобальные переменные с таким же именем. В примере ниже конфигурация x64 определяет локальную переменную **INCLUDE**, переопределяющую глобальное значение.

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\src\includes64"
        }
      ],

      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

Все пользовательские и стандартные переменные среды также доступны в `tasks.vs.json` и `launch.vs.json`.

#### <a name="build-in-macros"></a>Встроенные макросы

Вам доступны следующие встроенные макросы внутри `CppProperties.json`:

|||
|-|-|
|`${workspaceRoot}`| полный путь к папке рабочей области;|
|`${projectRoot}`| полный путь к папке, где находится `CppProperties.json`;|
|`${vsInstallDir}`| полный путь к папке, где установлен запущенный экземпляр Visual Studio 2017.|

Например, если проект имеет папку включения, а также включает windows.h и другие общие заголовки из Windows SDK, может потребоваться обновить файл конфигурации `CppProperties.json` с учетом этих включений:

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
> `%WindowsSdkDir%` и `%VCToolsInstallDir%` не заданы в качестве глобальных переменных среды, поэтому запустите из командной строки разработчика для VS 2017 программу devenv.exe, определяющую эти переменные.

## <a name="troubleshoot-intellisense-errors"></a>Устранение ошибок IntelliSense

Для устранения ошибок IntelliSense, вызванных отсутствием путей включения, откройте **Список ошибок** и отфильтруйте выходные данные до "Только IntelliSense" и кода ошибки E1696 "Не удается открыть исходный файл...".



