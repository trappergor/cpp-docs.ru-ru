---
title: Проекты "Открыть папку" в Visual C++ | Документы Майкрософт
ms.custom: ''
ms.date: 08/02/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe4eba09f06b987ab11f35429e13796fe6baafb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337289"
---
# <a name="open-folder-projects-in-visual-c"></a>Проекты "Открыть папку" в Visual C++
В Visual Studio 2017 появилась функция "Открыть папку", позволяющая открыть папку исходных файлов и немедленно приступить к написанию кода с поддержкой IntelliSense, просмотра, рефакторинга, отладки и т. п. Никакие файлы SLN или VCXPROJ не загружаются. При необходимости вы можете указать настраиваемые задачи и параметры запуска, используя простые файлы JSON. Благодаря функции "Открыть папку" Visual C++ теперь может поддерживать не только свободные коллекции файлов, но и практически любые системы сборки, включая CMake, Ninja, QMake (для проектов Qt), gyp, SCons, Gradle, Buck, make и многие другие. 

Чтобы использовать функцию "Открыть папку", в главном меню выберите *Файл | Открыть | Папка* или нажмите клавиши *CTRL+SHIFT+ALT+O*. Обозреватель решений сразу отображает все файлы в папке. Щелкните любой из них, чтобы приступить к изменению. В фоновом режиме Visual Studio индексирует файлы для поддержки функций навигации, рефакторинга и IntelliSense. Когда вы изменяете, создаете и удаляете файлы, Visual Studio автоматически отслеживает эти изменения и постоянно обновляет индекс IntelliSense. 
  
## <a name="cmake-projects"></a>Проекты CMake
Средство CMake интегрировано в интегрированную среду разработки Visual Studio как компонент рабочей нагрузки рабочего стола C++ "Инструменты CMake для Visual C++". Дополнительные сведения см. в разделе [Инструменты CMake для Visual C++](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>Проекты QMake, ориентированные на платформу Qt
Вы можете использовать Инструменты CMake для Visual C++, чтобы ориентироваться на Qt при создании проектов Qt, либо использовать расширение Qt Visual Studio Extension. Примечание. Начиная с августа 2017 г. [поддержка расширения Qt Visual Studio Extension для Visual Studio 2017](https://download.qt.io/development_releases/vsaddin/) доступна в виде бета-версии.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, Cons, SCons, Buck и т. д.
Вы можете использовать любую систему сборки в Visual C++ и по-прежнему пользоваться преимуществами интегрированной среды разработки Visual C++ и отладчика. При открытии корневой папки проекта Visual C++ использует эвристику, чтобы индексировать исходные файлы для поддержки IntelliSense и просмотра. Вы можете дать указания относительно структуры своего кода, отредактировав файл CppProperties.json. Аналогичным образом можно настроить программу сборки, изменив файл launch.vs.json. 

## <a name="configuring-open-folder-projects"></a>Настройка проектов "Открыть папку"
Проект "Открыть папку" можно настроить с помощью трех файлов JSON:
|||
|-|-|
|CppProperties.json|Указывает сведения о настраиваемой конфигурации для просмотра. При необходимости вы можете создать этот файл в корневой папке проекта.|
|launch.vs.json|Задает аргументы командной строки. Доступ к файлу можно получить в **обозревателе решений**, воспользовавшись пунктом контекстного меню **Параметры отладки и запуска**.|
|tasks.vs.json|Определяет настраиваемые команды сборки и параметры компилятора. Доступ к файлу можно получить в **обозревателе решений**, воспользовавшись пунктом контекстного меню **Настройка задач**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Настройка IntelliSense с помощью CppProperties.json
Поведение IntelliSense и просмотра частично зависит от активной конфигурации сборки, которая определяет пути #include, параметры компилятора и другие параметры. По умолчанию Visual Studio предоставляет конфигурации отладки и выпуска. Для некоторых проектов может потребоваться создать настраиваемую конфигурацию, чтобы функции IntelliSense и просмотра полностью понимали ваш код. Чтобы определить новую конфигурацию, создайте файл CppProperties.json в корневой папке. Пример:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Конфигурация может иметь любое из следующих свойств:

|||  
|-|-| 
|`name`|имя конфигурации, которое отображается в раскрывающемся списке конфигурации C++;|
|`includePath`|список папок, которые нужно указать в пути включения (для большинства компиляторов сопоставляется с /i);|
|`defines`|список макросов, которые нужно определить (для большинства компиляторов сопоставляется с /D);|
|`compilerSwitches`|один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense;|
|`forcedInclude`|заголовок, автоматически включаемый в каждый блок компиляции (сопоставляется с /FI для MSVC или с -include для clang);|
|`undefines`|список макросов, которые должны быть неопределенными (сопоставляется с /U для MSVC);|
|`intelliSenseMode`|используемая подсистема IntelliSense. Для MSVC, gcc или Clang вы можете указать варианты, привязанные к конкретной архитектуре:
- msvc-x86 (по умолчанию)
- msvc-x64
- msvc-arm
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

#### <a name="environment-variables"></a>Переменные среды
CppProperties.json поддерживает расширение системных переменных среды для включения путей и других значений свойств. Для расширения переменной среды `%FOODIR%` используется синтаксис `${env.FOODIR}`. Кроме того, поддерживаются следующие системные переменные.

|Имя переменной|Описание:|  
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

|Имя переменной|Описание:|  
|-----------|-----------------|
|linux_x86|Удаленная ориентация на Linux x86|
|linux_x64|Удаленная ориентация на Linux x64|
|linux_arm|Удаленная ориентация на Linux ARM|

В файле CppProperties.json можно определить пользовательские переменные среды либо глобально, либо для отдельных конфигураций. В примере ниже показано, как можно объявить и использовать стандартные и пользовательские переменные среды. Глобальное свойство **environments** объявляет переменную **INCLUDE**, которую может использовать любая конфигурация:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
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
      "intelliSenseMode": "msvc-x86"
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
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
Вы также можете определить свойство **environments** внутри конфигурации, чтобы оно применялось только к ней и переопределяло все глобальные переменные с таким же именем. В примере ниже конфигурация x64 определяет локальную переменную **INCLUDE**, переопределяющую глобальное значение.

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
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
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
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
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

Все пользовательские и стандартные переменные среды также доступны в файлах tasks.vs.json и launch.vs.json.

#### <a name="macros"></a>Макросы
Вам доступны следующие встроенные макросы внутри CppProperties.json:
|||
|-|-|
|`${workspaceRoot}`| полный путь к папке рабочей области;|
|`${projectRoot}`| полный путь к папке, где находится CppProperties.json;|
|`${vsInstallDir}`| полный путь к папке, где установлен запущенный экземпляр Visual Studio 2017.|

Например, если проект имеет папку включения, а также включает windows.h и другие общие заголовки из Windows SDK, может потребоваться обновить файл конфигурации CppProperties.json с учетом этих включений.

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Примечание.** `%WindowsSdkDir%` и `%VCToolsInstallDir%` не заданы в качестве глобальных переменных среды, поэтому запустите из командной строки разработчика для VS 2017 программу devenv.exe, определяющую эти переменные.

Для устранения ошибок IntelliSense, вызванных отсутствием путей включения, откройте **Список ошибок** и отфильтруйте выходные данные до "Только IntelliSense" и кода ошибки E1696 "Не удается открыть исходный файл...". 

В CppProperties.json можно создать любое число конфигураций. Каждая из них будет отображаться в раскрывающемся списке конфигурации.

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
### <a name="define-tasks-with-tasksvsjson"></a>Определение задач в файле tasks.vs.json
Вы можете автоматизировать скрипты сборки и любые внешние операции с файлами, размещенными в текущей рабочей области, запуская их как задачи в интегрированной среде разработки. Чтобы настроить новую задачу, щелкните правой кнопкой мыши нужный файл или папку и выберите **Настройка задач**. 

![Настройка задач "Открыть папку"](media/open-folder-config-tasks.png)

Создает (или открывает) файл `tasks.vs.json` в папке .vs, которую Visual Studio создает в корневой папке проекта. Можно определить в этом файле любую произвольную задачу, а затем вызывать ее из контекстного меню **обозревателя решений**. Ниже представлен пример файла tasks.vs.json, который определяет одну задачу. `taskName` определяет имя, отображаемое в контекстном меню. `appliesTo` определяет, для каких файлов можно выполнить эту команду. Свойство `command` ссылается на переменную среды COMSPEC, которая определяет путь для консоли (cmd.exe в Windows). Вы также можете ссылаться на переменные среды, объявленные в CppProperties.json или CMakeSettings.json. Свойство `args` определяет вызываемую командную строку. Макрос `${file}` передает выбранный файл в **обозреватель решений**. Приведенный ниже пример отображает имя для выбранного в этот момент CPP-файла.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Сохранив tasks.vs.json, можно щелкнуть любой CPP-файл в папке, выбрать пункт **Echo filename** (Вывести имя файла) в контекстном меню и просмотреть имя файла в окне вывода.



#### <a name="appliesto"></a>appliesTo
Вы можете создать задачи для любого файла или папки, указав их имена в поле `appliesTo`, например так: `"appliesTo" : "hello.cpp"`. В качестве значения можно использовать следующие маски файлов:
|||
|-|-|
|`"*"`| Задача доступна для всех файлов и папок в рабочей области.|
|`"*/"`| Задача доступна для всех папок в рабочей области.|
|`"*.cpp"`| задача доступна для всех CPP-файлов в рабочей области.|
|`"/*.cpp"`| задача доступна для всех CPP-файлов в корневой папке рабочей области.|
|`"src/*/"`| Задача доступна для всех подпапок в папке src.|
|`"makefile"`| Задача доступна для всех файлов makefile в рабочей области.|
|`"/makefile"`| Задача доступна только для файлов makefile в корневой папке рабочей области.|

#### <a name="output"></a>output
Используйте свойство `output`, чтобы указать исполняемый файл, который будет запущен при нажатии клавиши **F5**. Пример:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Макросы для tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Обозначает любую переменную среды (например, ${env.PATH}, ${env.COMSPEC} и т. д), которая определена для командной строки разработчика. Дополнительные сведения см. в статье [Командная строка разработчика для Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| Полный путь к папке рабочей области (например, "C:\sources\hello").|
|`${file}`| Полный путь к файлу или папке, для которых выполняется текущая задача (например, "C:\sources\hello\src\hello.cpp").|
|`${relativeFile}`| Относительный путь к файлу или папке (например, "src\hello.cpp").|
|`${fileBasename}`| Имя файла без пути или расширения (например, "hello").|
|`${fileDirname}`| Полный путь к файлу без имени этого файла (например, "C:\sources\hello\src").|
|`${fileExtname}`| Расширение выбранного файла (например, "CPP").|

#### <a name="custom-macros"></a>Пользовательские макросы
Чтобы определить пользовательский макрос в tasks.vs.json, добавьте пару "имя — значение" перед блоками задачи. Следующий пример определяет макрос `outDir`, используемый в свойстве `args`.

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Настройка параметров отладки с помощью launch.vs.json
Чтобы настроить аргументы командной строки для своей программы, щелкните правой кнопкой мыши исполняемый файл в **обозревателе решений** и выберите **Параметры отладки и запуска**. Открывается существующий файл `launch.vs.json` или, если он не существует, создается новый, предварительно заполненный сведениями о выбранной программе. 

Чтобы указать дополнительные аргументы, просто добавьте их в массив JSON `args`, как показано в следующем примере.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Когда вы сохраняете этот файл, новая конфигурация отображается в раскрывающемся списке "Цель отладки". Вы можете выбрать ее, чтобы запустить отладчик. Можно создать любое количество конфигураций отладки для любого количества исполняемых файлов. Нажатие клавиши **F5** запускает отладчик, который будет останавливаться на всех заданных точках останова. Все обычные окна отладчика и их функции теперь доступны.

## <a name="see-also"></a>См. также
[Интегрированная среда разработки и средства разработки Visual C++](ide-and-tools-for-visual-cpp-development.md)

