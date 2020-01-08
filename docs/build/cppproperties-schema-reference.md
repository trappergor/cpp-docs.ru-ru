---
title: Справочник по CppProperties. JSON
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: d59fca412a26d08f88ccbda20a2c0444cf33b1cb
ms.sourcegitcommit: 6c1960089b92d007fc28c32af1e4bef0f85fdf0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556673"
---
# <a name="cpppropertiesjson-reference"></a>Справочник по CppProperties. JSON

Открыть папки проекты, не использующие CMak, могут сохранять параметры конфигурации проекта для IntelliSense в файле *CppProperties. JSON* . (В проектах CMak используется файл [CMakeSettings. JSON](customize-cmake-settings.md) .) Конфигурация состоит из пар "имя-значение" и определяет #include пути, параметры компилятора и другие параметры. Дополнительные сведения о добавлении конфигураций в проекте открытой папки см. в разделе [проекты открытых папок для C++ ](open-folder-projects-cpp.md) . В следующих разделах приводятся общие сведения о различных параметрах. Чтобы получить полное описание схемы, перейдите к файлу *CppProperties_schema. JSON*, полный путь к которому указан в верхней части редактора кода, если открыт *CppProperties. JSON* .

## <a name="configuration-properties"></a>Свойства конфигурации

Конфигурация может иметь любое из следующих свойств:

|||
|-|-|
|`inheritEnvironments`| Указывает, какие среды применяются к этой конфигурации.|
|`name`|Имя конфигурации, которое будет отображаться в раскрывающемся списке C++ конфигурации|
|`includePath`|Разделенный запятыми список папок, которые должны быть указаны в пути поиска включаемых элементов (сопоставлены с/I для большинства компиляторов)|
|`defines`|Список макросов, которые нужно определить (для большинства компиляторов сопоставляется с /D)|
|`compilerSwitches`|Один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense|
|`forcedInclude`|Заголовок, автоматически включаемый в каждый блок компиляции (сопоставляется с /FI для MSVC или с -include для clang)|
|`undefines`|Список макросов, которые должны быть неопределенными (сопоставляется с /U для MSVC)|
|`intelliSenseMode`|Используемая подсистема IntelliSense. Можно указать один из стандартных вариантов конкретной архитектуры для КОМПИЛЯТОРОМ MSVC, GCC или Clang.|
|`environments`|Определяемые пользователем наборы переменных, которые ведут себя как переменные среды в командной строке и доступны с параметром $ {env.<VARIABLE>} макровирусах.|

### <a name="intellisensemode-values"></a>значения указан параметр intellisensemode

Редактор кода отображает доступные параметры при начале ввода:

![Открыть папку IntelliSense](media/open-folder-intellisense-mode.png "Открыть папку IntelliSense")

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
- Linux – GCC-ARM

Примечание. значения `msvc-x86` и `msvc-x64` поддерживаются только для устаревших причин. Вместо этого используйте `windows-msvc-*` варианты.

## <a name="pre-defined-environments"></a>Предварительно определенные среды

Visual Studio предоставляет следующие стандартные среды для Microsoft C++ , которые сопоставляются с соответствующими Командная строка разработчика. При наследовании одной из этих сред можно ссылаться на любую из переменных среды, используя глобальное свойство `env` с этим синтаксисом макроса: $ {env.\<VARIABLE >}.

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

## <a name="user_defined_environments"></a>Пользовательские среды

При необходимости можно использовать свойство `environments`, чтобы определить наборы переменных в *CppProperties. JSON* глобально или на уровне конфигурации. Эти переменные ведут себя так же, как переменные среды в контексте проекта открытой папки. к ним можно получить доступ с помощью синтаксиса $ {env.\<VARIABLE >} из *tasks. vs. JSON* и *Launch. vs. JSON* после их определения. Однако они не обязательно задаются в качестве реальных переменных среды в любой командной строке, используемой Visual Studio для внутренних целей.

**Visual Studio 2019 версии 16,4 и более поздних версий:** Зависящие от конфигурации переменные, определенные в *CppProperties. JSON* , автоматически выбираются целевыми объектами и задачами отладки без необходимости установки `inheritEnvironments`. Целевые объекты отладки автоматически запускаются в среде, указанной в *CppProperties. JSON*.

**Visual Studio 2019 версии 16,3 и более ранних версий:** При использовании среды необходимо указать ее в свойстве `inheritsEnvironments`, даже если среда определена как часть той же конфигурации; Свойство `environment` указывает имя среды. В следующем примере показан пример конфигурации для включения IntelliSense для GCC в установке MSYS2. Обратите внимание, что конфигурация определяет и наследует среду `mingw_64`, а также то, как свойство `includePath` может получить доступ к переменной `INCLUDE`.

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

При определении свойства **среды** внутри конфигурации он переопределяет все глобальные переменные с таким же именем.

## <a name="built-in-macros"></a>Встроенные макросы

У вас есть доступ к следующим встроенным макросам в *CppProperties. JSON*:

|||
|-|-|
|`${workspaceRoot}`| Полный путь к папке рабочей области|
|`${projectRoot}`| Полный путь к папке, в которую помещен *CppProperties. JSON*|
|`${env.vsInstallDir}`| Полный путь к папке, в которой установлен выполняющийся экземпляр Visual Studio|

### <a name="example"></a>Пример

Если проект содержит папку включения, а также содержит *Windows. h* и другие общие заголовки из Windows SDK, то, возможно, потребуется обновить файл конфигурации *CppProperties. JSON* следующими примерами:

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

Если вы не видите нужный IntelliSense, можно устранить неполадки, перейдя в **меню Сервис** > **Параметры** > **текстовый редактор** > **C/C++**  > **Дополнительно** и установив для параметра **включить ведение журнала** **значение true**. Чтобы начать, установите для параметра **уровень ведения журнала** значение 5 и **фильтры ведения журнала** — до 8.

![Ведение журналов диагностики](media/diagnostic-logging.png)

Выходные данные передаются в **окно вывода** и отображаются при выборе команды **Показать выходные данные из: C++ визуальный журнал**. Выходные данные содержат, помимо прочего, список фактических путей включения, которые IntelliSense пытается использовать. Если пути не соответствуют параметрам в *CppProperties. JSON*, попробуйте закрыть папку и удалить вложенную папку *. VS* , содержащую кэшированные данные обзора.

Для устранения ошибок IntelliSense, вызванных отсутствием путей включения, откройте **Список ошибок** и отфильтруйте выходные данные до "Только IntelliSense" и кода ошибки E1696 "Не удается открыть исходный файл...".
