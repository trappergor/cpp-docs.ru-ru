---
title: Использование средств проверки на соответствие C++ Core Guidelines
description: Как настроить и использовать правила анализа кода Microsoft C++ для C++ Core Guidelines.
ms.date: 07/27/2020
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 4fb06b0f78c93e6b76e0b8d64d7dfbdc541cf299
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334147"
---
# <a name="use-the-c-core-guidelines-checkers"></a>Использование средств проверки на соответствие C++ Core Guidelines

C++ Core Guidelines являются переносимым набором руководств, правил и рекомендаций по написанию кода на C++, созданного экспертами и дизайнерами C++. В настоящее время Visual Studio поддерживает подмножество этих правил в составе средств анализа кода для C++. Основные компоненты проверки по рекомендациям устанавливаются по умолчанию в Visual Studio 2017 и Visual Studio 2019. Они [доступны в виде пакета NuGet для Visual Studio 2015](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>Проект C++ Core Guidelines

C++ Core Guidelines, созданные с помощью Бьерном Страуструп и других, являются руководством по безопасному и эффективному использованию современных C++. В рекомендациях особое внимание уделяется безопасности статического типа и безопасности ресурсов. Они позволяют устранить или свести к минимальным причинам наиболее подверженные ошибкам части языка. Они также предлагают, как сделать код более простым, надежным и повысить производительность. Эти рекомендации поддерживаются стандартом C++ Foundation. Дополнительные сведения см. в документации, [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)и доступ к файлам проекта документации по C++ Core Guidelines в [GitHub](https://github.com/isocpp/CppCoreGuidelines).

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Включение рекомендаций по C++ Core Check в анализе кода

::: moniker range="<=msvc-150"

Подмножество правил C++ Core Check входит в набор правил, рекомендуемых Microsoft Native. Это набор правил, который запускается по умолчанию при включении анализа кода.

### <a name="to-enable-code-analysis-on-your-project"></a>Включение анализа кода для проекта

1. Откройте диалоговое окно  **страницы свойств** для проекта.

1. Выберите **Configuration Properties** > страницу свойств **анализ кода** свойств конфигурации.

1. Установите флажок **Включить анализ кода при сборке** .

![Страница свойств для общих параметров анализа кода](media/cppcorecheck_codeanalysis_general.png)

Чтобы включить дополнительные правила основной проверки, откройте раскрывающийся список и выберите наборы правил, которые необходимо включить.

![Раскрывающийся список для дополнительных наборов правил C++ Core Check](media/cppcorecheck_codeanalysis_extensions.png)

::: moniker-end
::: moniker range=">=msvc-160"

Подмножество правил C++ Core Check входит в набор правил, рекомендуемых Microsoft Native. Это набор правил, выполняемый по умолчанию при включенном анализе кода Майкрософт.

### <a name="to-enable-code-analysis-on-your-project"></a>Чтобы включить анализ кода в проекте, выполните следующие действия.

1. Откройте диалоговое окно  **страницы свойств** для проекта.

1. Выберите **Configuration Properties** > страницу свойств **анализ кода** свойств конфигурации.

1. Установите параметр **Включить анализ кода при сборке** и **включить свойства анализа кода Майкрософт** .

Можно также выбрать запуск всех поддерживаемых правил C++ Core Check или выбрать собственное подмножество для запуска:

### <a name="to-enable-additional-core-check-rules"></a>Включение дополнительных правил базовой проверки

1. Откройте диалоговое окно  **страницы свойств** для проекта.

1. Выберите страницу свойств **Конфигурация** > **анализ кода** свойства > **Майкрософт** .

1. Откройте раскрывающийся список **активные правила** и выберите **пункт выбрать несколько наборов правил**.

1. В диалоговом окне **Добавление или удаление наборов правил** выберите наборы правил, которые необходимо включить.

::: moniker-end

## <a name="examples"></a>Примеры

Ниже приведен пример некоторых проблем, которые могут найти C++ Core Check правила.

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

В этом примере показано несколько предупреждений, которые могут найти C++ Core Check правила.

- C26494 — тип правила. 5: всегда инициализировать объект.

- C26485 является границей правила. 3: отсутствует Decay массива в указатель.

- C26481 является границей правила. 1: не используйте арифметические действия с указателями. Используйте вместо этого `span`.

Установите и включите наборы правил анализа кода C++ Core Check, а затем скомпилируйте этот код. Анализ кода выводит два первых предупреждения и подавляет третье. Ниже приведены выходные данные сборки из примера кода в Visual Studio 2015:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Core Guidelines, которые помогут вам в написании лучшего и безопасного кода. Однако вы можете найти экземпляр, в котором не следует применять правило или профиль. Его легко скрыть непосредственно в коде. Атрибут можно использовать `[[gsl::suppress]]` для сохранения C++ Core Check обнаружения и сообщения о нарушении правила в следующем блоке кода. Можно пометить отдельные инструкции для подавления определенных правил. Можно даже отключать весь профиль границ путем записи `[[gsl::suppress(bounds)]]` без включения определенного номера правила.

## <a name="supported-rule-sets"></a>Поддерживаемые наборы правил

По мере добавления новых правил в средство проверки C++ Core Guidelines количество предупреждений, возникших для существующего кода, может увеличиться. Для фильтрации типов правил, которые следует включить, можно использовать готовые наборы правил. Справочные статьи по большинству правил можно найти в разделе [Справочник по Visual Studio C++ Core Check](code-analysis-for-cpp-corecheck.md).

- **Арифметические правила** : правила для обнаружения арифметического [переполнения](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [беззнаковых операций с подписью](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)и [побитовой обработки](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative). <sup>15,6</sup>

- **Правила границ** : принудительно примените [профиль границ C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile). <sup>15,3</sup>

- **Правила классов**. несколько правил, которые касаются правильного использования специальных функций-членов и виртуальных спецификаций. Они являются подмножеством проверок, рекомендуемых для [классов и иерархий классов](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class). <sup>15,5</sup>

- **Правила параллелизма** : одно правило, которое перехватывает неправильные объявления объектов Guard. Дополнительные сведения см. [в разделе рекомендации, связанные с параллелизмом](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency). <sup>15,5</sup>

- **Константные правила** : принудительное применение [проверок, связанных с константой, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability). <sup>15,3</sup>

- **Правила объявления** : несколько правил из [руководств по интерфейсам](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) , в которых основное внимание уделяется объявлению глобальных переменных. <sup>15,5</sup>

- **Правила перечисления**. Эти правила применяют [проверки, связанные с перечислением, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-enum). <sup>16,3</sup>

- **Экспериментальные правила** Это экспериментальные C++ Core Check правила, которые полезны, но не готовы к ежедневному использованию. Попробуйте их и [Предоставьте отзыв](https://aka.ms/feedback/suggest?space=62). <sup>16,0</sup>

- **Правила функций** : две проверки, помогающие при внедрении **`noexcept`** спецификатора. Они являются частью рекомендаций по [очистке проектирования и реализации функций](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions). <sup>15,5</sup>

- **Правила GSL**. Эти правила применяют проверки, связанные с [библиотекой поддержки руководств, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-gsl). <sup>15,7</sup>

- **Правила времени существования**. Эти правила применяют [профиль времени существования C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prolifetime-lifetime-safety-profile). <sup>15,7</sup>

- **Правила для указателей владельца** : принудительная [Проверка управления ресурсами, связанная с владельцем \<T> C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management). <sup> 15,3</sup>

- **Правила необработанных указателей** : принудительно применять [проверки управления ресурсами, связанные с необработанными указателями, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management). <sup>15,3</sup>

- **Правила общих указателей** : это часть рекомендаций по [управлению ресурсами](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) . <sup>15,5</sup> мы добавили несколько правил, специфичных для передачи общих указателей в функции или локального использования.

- **Правила STL**. Эти правила применяют проверки, связанные с [стандартной библиотекой C++ (STL), из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-stdlib). <sup>15,7</sup>

- **Правила стилей** : одна простая, но важная проверка, Ban использование [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto). <sup>15,5</sup> . это первый шаг к улучшению стиля написания кода и использованию выражений и инструкций в C++.

- **Правила типов**. Примените [профиль типа C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile). <sup>15,3</sup>

- **Правила уникальных указателей** : принудительная [Проверка управления ресурсами, связанная с типами с семантикой уникального указателя из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management). <sup>15,3</sup>

- **Правила C++ Core Check**. Этот набор правил содержит все реализованные в настоящее время проверки из [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-core-guidelines), за исключением экспериментальных правил.

<sup>15,3</sup> . Эти правила впервые появились в Visual Studio 2017 версии 15,3 \
<sup>15,5</sup> . Эти правила впервые появились в Visual Studio 2017 версии 15,5 \
<sup>15,6</sup> . Эти правила впервые появились в Visual Studio 2017 версии 15,6 \
<sup>15,7</sup> . Эти правила впервые появились в Visual Studio 2017 версии 15,7 \
<sup>16,0</sup> . Эти правила впервые появились в Visual Studio 2019 версии 16,0 \
<sup>16,3</sup> . Эти правила впервые появились в Visual Studio 2019 версии 16,3

Предупреждения можно ограничить только одной или несколькими группами. **Собственные минимальные** и **Рекомендуемые** наборы правил включают C++ Core Check правила и другие предварительные проверки.

::: moniker range="<=msvc-150"

Чтобы просмотреть доступные наборы правил, откройте диалоговое окно **Свойства проекта** . В диалоговом окне **страницы свойств** перейдите на страницу свойств **Свойства конфигурации**  >  **Code Analysis**  >  **Общие** свойства анализ кода. Затем откройте раскрывающийся список в поле со списком **наборы правил** , чтобы просмотреть доступные наборы правил. Чтобы создать пользовательское сочетание наборов правил, выберите **выбрать несколько наборов правил**. В диалоговом окне **Добавление или удаление наборов правил** перечислены правила, которые можно выбрать. Дополнительные сведения об использовании наборов правил в Visual Studio см. в разделе [Использование наборов правил для указания выполняемых правил C++](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

::: moniker-end
::: moniker range=">=msvc-160"

Чтобы просмотреть доступные наборы правил, откройте диалоговое окно **Свойства проекта** . В диалоговом окне **страницы свойств** откройте страницу свойств **Конфигурация**  >  **анализ кода** свойства  >  **Майкрософт** . Затем откройте раскрывающееся меню в поле со списком **активные правила** , чтобы просмотреть доступные наборы правил. Чтобы создать пользовательское сочетание наборов правил, выберите **выбрать несколько наборов правил**. В диалоговом окне **Добавление или удаление наборов правил** перечислены правила, которые можно выбрать. Дополнительные сведения об использовании наборов правил в Visual Studio см. в разделе [Использование наборов правил для указания выполняемых правил C++](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

::: moniker-end

## <a name="macros"></a>Макросы

Средство проверки C++ Core Guidelines поставляется с файлом заголовка, который определяет макросы, упрощающие вывод целых категорий предупреждений в коде:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Эти макросы соответствуют наборам правил и разворачиваются в список номеров предупреждений с разделителями-пробелами. С помощью соответствующих конструкций директивы pragma можно настроить эффективный набор правил, которые представляют интерес для проекта или раздела кода. В следующем примере анализ кода предупреждает только об отсутствующих модификаторах константы:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Атрибуты

Компилятор Microsoft C++ имеет ограниченную поддержку `[[gsl::suppress]]` атрибута. Он может использоваться для отключения предупреждений о выражениях и блоках инструкций внутри функций.

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppress-analysis-by-using-command-line-options"></a>Подавлять анализ с помощью параметров командной строки

Вместо #pragmas можно использовать параметры командной строки на странице свойств файла, чтобы отключить предупреждения для проекта или отдельного файла. Например, чтобы отключить предупреждение C26400 для файла, выполните следующие действия.

1. Щелкните правой кнопкой мыши файл в **Обозреватель решений** и выберите пункт **свойства**.

1. В диалоговом окне **страницы свойств** откройте страницу свойств **конфигурации**  >  **C/C++**  >  **Командная строка** .

1. В поле ввода **Дополнительные параметры** добавьте *`/wd26400`* .

Можно использовать параметр командной строки, чтобы временно отключить весь анализ кода для файла, указав **`/analyze-`** . Вы увидите предупреждение *D9025 переопределение "/Analyze" на "/анализе-"* , которое напоминает вам снова включить анализ кода позже.

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a> Включение средства проверки C++ Core Guidelines для конкретных файлов проекта

Иногда полезно выполнять анализ кода и по-прежнему использовать интегрированную среду разработки Visual Studio. Используйте следующий пример сценария для больших проектов. Он может сэкономить время сборки и упростить фильтрацию результатов:

1. В командной оболочке задайте `esp.extension` `esp.annotationbuildlevel` переменные среды и.

1. Чтобы унаследовать эти переменные, откройте Visual Studio из командной оболочки.

1. Загрузите проект и откройте его свойства.

1. Включите анализ кода, выберите соответствующие наборы правил, но не включайте расширения анализа кода.

1. Перейдите к файлу, который необходимо проанализировать, с помощью средства проверки C++ Core Guidelines и откройте его свойства.

1. Выберите **Свойства конфигурации**  >  **C/C++**  >  **Командная строка**  >  **Дополнительные параметры** и добавьте *`/analyze:plugin EspXEngine.dll`*

1. Отключить использование предкомпилированного заголовка (предварительно скомпилированные заголовки **свойств конфигурации**  >  **C/C++**  >  **Precompiled Headers** ). Это необходимо потому, что модуль расширений может попытаться прочитать свою внутреннюю информацию из предкомпилированного заголовка (PCH). Если PCH скомпилирован с параметрами проекта по умолчанию, он не будет совместимым.

1. Выполните повторную сборку проекта. Стандартные предбыстрые проверки должны выполняться для всех файлов. Так как средство проверки C++ Core Guidelines не включено по умолчанию, оно должно выполняться только в том файле, который настроен для использования.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Использование средства проверки C++ Core Guidelines за пределами Visual Studio

Можно использовать C++ Core Guidelines проверки в автоматизированных сборках.

### <a name="msbuild"></a>MSBuild

Средство проверки анализа машинного кода (Предварительная) интегрировано в среду MSBuild пользовательскими целевыми файлами. Можно использовать свойства проекта, чтобы включить его, и добавить средство проверки C++ Core Guidelines (основанное на предбыстрых действиях):

```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```

Убедитесь, что эти свойства добавлены перед импортом *`Microsoft.Cpp.targets`* файла. Можно выбрать определенные наборы правил или создать настраиваемый набор правил. Или используйте набор правил по умолчанию, который включает другие предбыстрые проверки.

Модуль проверки C++ ядра можно запустить только для указанных файлов. Используйте тот же подход, который [описан ранее](#corecheck_per_file), но используйте файлы MSBuild. Переменные среды можно задать с помощью `BuildMacro` элемента:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Если вы не хотите изменять файл проекта, можно передать свойства в командной строке:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>Проекты, не относящиеся к MSBuild

Если вы используете систему сборки, которая не использует MSBuild, вы по-прежнему можете запустить средство проверки. Чтобы использовать его, необходимо ознакомиться с некоторыми внутренними настройками модуля анализа кода. Мы не гарантируем поддержку этих внутренних компонентов в будущих версиях Visual Studio.

Для анализа кода требуется несколько переменных среды и параметров командной строки компилятора. Мы рекомендуем использовать среду **командной строки для собственных средств** , чтобы не выполнять поиск конкретных путей для компилятора, включаемых каталогов и т. д.

- **Переменные среды**
  - `set esp.extensions=cppcorecheck.dll` Это указывает обработчику загрузить модуль C++ Core Guidelines.
  - `set esp.annotationbuildlevel=ignore` Это отключает логику, которая обрабатывает аннотации SAL. Аннотации не влияют на анализ кода в средстве проверки C++ Core Guidelines, но их обработка занимает некоторое время (иногда длительное время). Этот параметр является необязательным, но настоятельно рекомендуется.
  - `set caexcludepath=%include%` Мы настоятельно рекомендуем отключить предупреждения, которые срабатывают в стандартных заголовках. Здесь можно добавить дополнительные пути, например путь к общим заголовкам в проекте.

- **Параметры командной строки**
  - **`/analyze`**  Включает анализ кода (рекомендуется также использовать **`/analyze:only`** и **`/analyze:quiet`** ).
  - **`/analyze:plugin EspXEngine.dll`** При выборе этого варианта модуль расширений анализа кода загружается в предвысокую скорость. Этот модуль, в свою очередь, загружает средство проверки C++ Core Guidelines.

## <a name="use-the-guideline-support-library"></a>Использование библиотеки поддержки рекомендаций

Библиотека поддержки нормативных руководств (GSL) разработана, чтобы помочь вам следовать основным рекомендациям. GSL включает определения, позволяющие заменять подверженные ошибкам конструкции более безопасными альтернативами. Например, можно заменить `T*, length` пару параметров на `span<T>` тип. GSL доступен по адресу [http://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl) . Библиотека является открытым исходным кодом, поэтому вы можете просматривать источники, создавать комментарии или участвовать в программе. Проект можно найти по адресу [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

::: moniker range="msvc-140"

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a> Использование C++ Core Check рекомендаций в проектах Visual Studio 2015

При использовании Visual Studio 2015 наборы правил анализа кода C++ Core Check не устанавливаются по умолчанию. Перед включением средств анализа кода C++ Core Check в Visual Studio 2015 необходимо выполнить дополнительные действия. Корпорация Майкрософт предоставляет поддержку проектов Visual Studio 2015 с помощью пакета NuGet. Пакет называется Microsoft. CppCoreCheck и доступен по адресу [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) . Для этого пакета требуется по крайней мере Visual Studio 2015 с обновлением 1.

Пакет также устанавливает другой пакет в качестве зависимости — библиотеку поддержки рекомендаций только для заголовков (GSL). GSL также доступен на сайте GitHub по адресу [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

Из-за способа загрузки правил анализа кода в Visual Studio 2015 `Microsoft.CppCoreCheck` пакет NuGet необходимо установить в каждый проект C++, который требуется проверить.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Добавление пакета Microsoft. CppCoreCheck в проект в Visual Studio 2015

1. В **Обозреватель решений** щелкните правой кнопкой мыши, чтобы открыть контекстное меню проекта в решении, в которое требуется добавить пакет. Выберите **Управление пакетами NuGet** , чтобы открыть **Диспетчер пакетов NuGet**.

1. В окне **Диспетчер пакетов NuGet** найдите Microsoft. CppCoreCheck.

    ![В окне диспетчера пакетов NuGet отображается пакет CppCoreCheck](../code-quality/media/cppcorecheck_nuget_window.png)

1. Выберите пакет Microsoft. CppCoreCheck, а затем нажмите кнопку " **установить** ", чтобы добавить правила в проект.

   Пакет NuGet добавляет дополнительный *`.targets`* файл MSBuild в проект, который вызывается при включении анализа кода для проекта. *`.targets`* Файл добавляет правила C++ Core Check в качестве дополнительного расширения для средства анализа кода Visual Studio. После установки пакета можно использовать диалоговое окно страницы свойств, чтобы включить или отключить правила выпуска и экспериментального использования.

::: moniker-end

## <a name="see-also"></a>См. также

- [Справочник по Visual Studio C++ Core Check](code-analysis-for-cpp-corecheck.md)
