---
title: CppProperties.json ссылка
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: be6db52e1e62244e9f44db8ac86238242ab50ca0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328722"
---
# <a name="cpppropertiesjson-reference"></a>CppProperties.json ссылка

Проекты Open Folder, не использовав cMake, могут хранить настройки конфигурации проекта для IntelliSense в файле *CppProperties.json.* (Проекты CMake используют файл [CMakeSettings.json.)](customize-cmake-settings.md) Конфигурация состоит из пар имен/значений и определяет #include путей, компиляторных переключателей и других параметров. Для получения дополнительной информации о том, как добавлять конфигурации в проектOpen Folder, можно ознакомиться с [проектами Open Folder.](open-folder-projects-cpp.md) В следующих разделах кратко излагаются различные параметры. Для полного описания схемы перейдите на *CppProperties_schema.json*, полный путь которого дается в верхней части редактора кода, когда *CppProperties.json* открыт.

## <a name="configuration-properties"></a>Свойства конфигурации

Конфигурация может иметь любое из следующих свойств:

|||
|-|-|
|`inheritEnvironments`| Определяет, какие среды применяются к этой конфигурации.|
|`name`|Имя конфигурации, которое появится в отсечке конфигурации СЗ|
|`includePath`|Запятый разделенный список папок, которые должны быть указаны в пути включения (карты к /I для большинства компиляторов)|
|`defines`|Список макросов, которые нужно определить (для большинства компиляторов сопоставляется с /D)|
|`compilerSwitches`|Один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense|
|`forcedInclude`|Заголовок, автоматически включаемый в каждый блок компиляции (сопоставляется с /FI для MSVC или с -include для clang)|
|`undefines`|Список макросов, которые должны быть неопределенными (сопоставляется с /U для MSVC)|
|`intelliSenseMode`|Используемая подсистема IntelliSense. Можно указать один из предопределенных вариантов архитектуры для MSVC, gcc или Clang.|
|`environments`|Определенные пользователем наборы переменных, которые ведут себя как переменные среды в\< запросе команды и доступны с помощью $senv. VARIABLE> макрос.|

### <a name="intellisensemode-values"></a>значения intelliSenseMode

Редактор кода показывает доступные варианты при вводе:

![Открыть Folder IntelliSense](media/open-folder-intellisense-mode.png "Открыть Folder IntelliSense")

Это поддерживаемые значения:

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
- linux-gcc-рука

Примечание: Значения `msvc-x86` и `msvc-x64` поддерживаются только по устаревшим причинам. Вместо `windows-msvc-*` этого используйте варианты.

## <a name="pre-defined-environments"></a>Заранее определенные среды

Visual Studio предоставляет следующие предопределенные среды для Microsoft C, которые отображают соответствующую команду разработчика Prompt. Когда вы наследуете одну из этих сред, вы можете обратиться `env` к любой из переменных среды, используя глобальное свойство с этим макро синтаксисом: $\< ПЕРЕМЕНЕУ>.

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

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a>Среды, определяемые пользователем

Можно дополнительно использовать `environments` свойство для определения наборов переменных в *CppProperties.json* как глобально, так и по конфигурации. Эти переменные ведут себя как переменные среды в контексте проекта Open Folder и\< могут быть доступны с помощью $senv. VARIABLE> синтаксис от *tasks.vs.json* и *launch.vs.json* после того, как они будут определены здесь. Однако они не обязательно устанавливаются в качестве фактических переменных среды в любой командной подсказке, которую Visual Studio использует внутренне.

**Visual Studio 2019 версия 16.4 и позже:** Переменные, определенные в *CppProperties.json,* автоматически подбираются целями и `inheritEnvironments`задачами отладки без необходимости установки. Цели debug запускаются автоматически с помощью указанной среды *cppProperties.json.*

**Visual Studio 2019 версия 16.3 и более ранняя:** При потреблении среды необходимо указать ее `inheritsEnvironments` в свойстве, даже если среда определена как часть той же конфигурации; свойство `environment` определяет название окружающей среды. В следующем примере показана примерконфигурация для включения IntelliSense для GCC в установке MSYS2. Обратите внимание, как конфигурация определяет `mingw_64` и наследует `includePath` среду, `INCLUDE` и как свойство может получить доступ к переменной.

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

При определении свойства среды внутри **конфигурации** он переопределяет любые глобальные переменные с тем же именем.

## <a name="built-in-macros"></a>Встроенные макросы

У вас есть доступ к следующим встроенным макросам внутри *CppProperties.json:*

|||
|-|-|
|`${workspaceRoot}`| Полный путь к папке рабочей области|
|`${projectRoot}`| Полный путь к папке, где *находится CppProperties.json*|
|`${env.vsInstallDir}`| Полный путь к папке, где установлен запущенный экземпляр Visual Studio|

### <a name="example"></a>Пример

Если ваш проект включает папку, а также включает в себя *windows.h* и другие общие заголовки из Windows SDK, вы можете обновить файл конфигурации *CppProperties.json* со следующими сведениями:

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

Если вы не видите IntelliSense, что вы ожидаете, вы можете устранить неполадки, перейдя в **Инструменты** > **Параметры** > **Текстовый редактор** > **C / C '** > **Расширенный** и настройки **Enable Logging** на **истину**. Для начала попробуйте установить **уровень регистрации** до 5, а **фильтры регистрации** — до 8.

![Ведение журнала диагностики](media/diagnostic-logging.png)

Выход по трубопроводу в **окно вывода** и отображается при выборе вывода **Show From: Visual C ' Log**. Выход содержит, среди прочего, список фактических включают пути, которые IntelliSense пытается использовать. Если пути не совпадают с теми, что есть в *CppProperties.json,* попробуйте закрыть папку и удалить субпапу *.vs,* содержащую кэшированные данные просмотра.

Для устранения ошибок IntelliSense, вызванных отсутствием путей включения, откройте **Список ошибок** и отфильтруйте выходные данные до "Только IntelliSense" и кода ошибки E1696 "Не удается открыть исходный файл...".
