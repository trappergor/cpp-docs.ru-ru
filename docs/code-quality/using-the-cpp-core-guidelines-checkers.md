---
title: Использование средств проверки на соответствие C++ Core Guidelines
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 9c36c17e819e954d66833f059fe794ac14898e75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227729"
---
# <a name="use-the-c-core-guidelines-checkers"></a>Использование средств проверки на соответствие C++ Core Guidelines

C++ Core Guidelines являются переносимым набором руководств, правил и рекомендаций по написанию кода на C++, созданного экспертами и дизайнерами C++. В настоящее время Visual Studio поддерживает подмножество этих правил в составе средств анализа кода для C++. Основные проверочные проверки по умолчанию устанавливаются в Visual Studio 2017 и Visual Studio 2019 и доступны в [виде пакета NuGet для Visual studio 2015](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>Проект C++ Core Guidelines

C++ Core Guidelines, созданные с помощью Бьерном Страуструп и других, являются руководством по безопасному и эффективному использованию современных C++. В рекомендациях особое внимание уделяется безопасности статического типа и безопасности ресурсов. Они позволяют устранить или свести к минимальному числу наиболее подверженные ошибкам части языка и предложить, как сделать код более простым и надежным способом. Эти рекомендации поддерживаются стандартом C++ Foundation. Дополнительные сведения см. в документации, [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)и доступ к файлам проекта документации по C++ Core Guidelines в [GitHub](https://github.com/isocpp/CppCoreGuidelines).

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Включение рекомендаций по C++ Core Check в анализе кода

Вы можете включить анализ кода для проекта, установив флажок **Включить анализ кода при сборке** в разделе **анализ кода** диалогового окна **страницы свойств** проекта.

![Страница свойств для общих параметров анализа кода](media/cppcorecheck_codeanalysis_general.png)

Подмножество правил C++ Core Check включается в набор правил, рекомендуемый Microsoft Native, который запускается по умолчанию при включении анализа кода. Чтобы включить дополнительные правила базовой проверки, щелкните раскрывающийся список и выберите наборы правил, которые необходимо включить.

![Раскрывающийся список для дополнительных наборов правил C++ Core Check](media/cppcorecheck_codeanalysis_extensions.png)

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

Если C++ Core Check наборы правил анализа кода установлены и включены при компиляции этого кода, первые два предупреждения выводятся, но третья подавляется. Вот выходные данные сборки из примера кода:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Core Guidelines, которые помогут вам в написании лучшего и безопасного кода. Однако если у вас есть экземпляр, в котором не следует применять правило или профиль, легко подавить его непосредственно в коде. Атрибут можно использовать `gsl::suppress` для сохранения C++ Core Check обнаружения и сообщения о нарушении правила в следующем блоке кода. Можно пометить отдельные инструкции для подавления определенных правил. Можно даже отключать весь профиль границ путем записи `[[gsl::suppress(bounds)]]` без включения определенного номера правила.

## <a name="supported-rule-sets"></a>Поддерживаемые наборы правил

По мере добавления новых правил в средство проверки C++ Core Guidelines количество предупреждений, возникших для существующего кода, может увеличиться. Для фильтрации типов правил, которые следует включить, можно использовать готовые наборы правил.
Справочные разделы для большинства правил находятся в [справочнике по Visual Studio C++ Core Check](code-analysis-for-cpp-corecheck.md).

Начиная с Visual Studio 2017 версии 15,3, поддерживаются следующие наборы правил:

- **Правила указателей владельца** применяют [проверки управления ресурсами \<T> , связанные с владельцем C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Правила const** применяют [к C++ Core Guidelines проверки, связанные с константами](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability).

- **Правила необработанных указателей** применяют [проверки управления ресурсами, связанные с необработанными указателями, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Правила уникальных указателей** применяют [проверки управления ресурсами, связанные с типами с семантикой уникальных указателей, из C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Правила границ** применяют [профиль границ C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

- **Правила типов** применяют [профиль типа C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile).

**Visual Studio 2017 версии 15,5**:

- **Правила классов** Несколько правил, которые касаются правильного использования специальных функций-членов и виртуальных спецификаций. Это подмножество проверок, рекомендованных для [классов и иерархий классов](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class).
- **Правила параллелизма** Одно правило, которое перехватывает неверно объявленные объекты Guard. Дополнительные сведения см. [в разделе рекомендации, связанные с параллелизмом](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency).
- **Правила объявления** Несколько правил из [руководств по интерфейсам](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) , в которых основное внимание уделяется объявлению глобальных переменных.
- **Правила функций** Две проверки, помогающие при внедрении **`noexcept`** спецификатора. Это часть рекомендаций по [очистке конструктора и реализации функций](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions).
- **Правила общих указателей** В рамках применения рекомендаций по [управлению ресурсами](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) мы добавили несколько правил, специфичных для передачи общих указателей в функции или их использования локально.
- **Правила стилей** Одна простая, но важная проверка, Ban использование [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto). Это первый шаг в улучшении стиля написания кода и использования выражений и инструкций в C++.

**Visual Studio 2017 версии 15,6**:

- **Арифметические правила** Правила для обнаружения арифметического [переполнения](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [беззнаковых операций с подписью](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned) и [битовой обработки](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative).

Предупреждения можно ограничить только одной или несколькими группами. В качестве **минимального** и **исходного рекомендуемого** набора правил применяются правила C++ Core Check в дополнение к другим предварительным проверкам. Чтобы просмотреть доступные наборы правил, откройте диалоговое окно Свойства проекта, выберите **код аналисис\женерал**, откройте раскрывающийся список в поле со списком **наборы правил** и выберите **пункт выбрать несколько наборов правил**. Дополнительные сведения об использовании наборов правил в Visual Studio см. в разделе [Использование наборов правил для указания выполняемых правил C++](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

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

Компилятор Microsoft C++ имеет ограниченную поддержку атрибута GSL подавлять. Он может использоваться для отключения предупреждений о выражениях и блоках инструкций внутри функции.

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

1. Щелкните файл правой кнопкой мыши в **Обозреватель решений**

1. Выбор **свойств | C/C++ | Командная строка**

1. В окне **Дополнительные параметры** добавьте `/wd26400` .

Можно использовать параметр командной строки, чтобы временно отключить весь анализ кода для файла, указав `/analyze-` . Это выдает предупреждение, *D9025 переопределение "/Analyze" на "/анализе-"*, которое напоминает вам снова включить анализ кода позже.

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a>Включение средства проверки C++ Core Guidelines для конкретных файлов проекта

Иногда может быть полезно выполнить анализ кода и по-прежнему использовать интегрированную среду разработки Visual Studio. Следующий пример сценария можно использовать для больших проектов, чтобы сэкономить время сборки и упростить фильтрацию результатов:

1. В командной оболочке задайте `esp.extension` `esp.annotationbuildlevel` переменные среды и.
1. Чтобы унаследовать эти переменные, откройте Visual Studio из командной оболочки.
1. Загрузите проект и откройте его свойства.
1. Включите анализ кода, выберите соответствующие наборы правил, но не включайте расширения для анализа кода.
1. Перейдите к файлу, который необходимо проанализировать, с помощью средства проверки C++ Core Guidelines и откройте его свойства.
1. Выберите **Параметры линии C/C++ \комманд** и добавьте`/analyze:plugin EspXEngine.dll`
1. Отключить использование предкомпилированного заголовка (**заголовки C/C++ \прекомпилед**). Это необходимо, поскольку модуль расширений может попытаться считать внутреннюю информацию из предкомпилированного заголовка (PCH); Если PCH скомпилирован с параметрами проекта по умолчанию, он не будет совместимым.
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

Убедитесь, что эти свойства добавлены перед импортом файла Microsoft. cpp. targets. Можно выбрать определенные наборы правил или создать настраиваемый набор правил или использовать набор правил по умолчанию, включающий другие предварительные проверки.

Модуль проверки C++ ядра можно запустить только для указанных файлов, используя тот же подход, который [описан ранее](#corecheck_per_file), но с помощью файлов MSBuild. Переменные среды можно задать с помощью `BuildMacro` элемента:

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

Если вы используете систему сборки, которая не использует MSBuild, вы по-прежнему можете запустить средство проверки, но вам необходимо ознакомиться с некоторыми внутренними настройками модуля анализа кода. Эти внутренние компоненты не гарантируют поддержку в будущем.

Необходимо задать несколько переменных среды и использовать правильные параметры командной строки для компилятора. Лучше работать в среде "Командная строка собственных средств", чтобы вам не нужно было искать конкретные пути для компилятора, включаемых каталогов и т. д.

- **Переменные среды**
  - `set esp.extensions=cppcorecheck.dll`Это указывает обработчику загрузить модуль C++ Core Guidelines.
  - `set esp.annotationbuildlevel=ignore`Это отключает логику, которая обрабатывает аннотации SAL. Аннотации не влияют на анализ кода в средстве проверки C++ Core Guidelines, но их обработка занимает некоторое время (иногда длительное время). Этот параметр является необязательным, но настоятельно рекомендуется.
  - `set caexcludepath=%include%`Мы настоятельно рекомендуем отключить предупреждения, которые срабатывают в стандартных заголовках. Здесь можно добавить дополнительные пути, например путь к общим заголовкам в проекте.

- **Параметры командной строки**
  - `/analyze`Включает анализ кода (Рассмотрите также использование/Analyze: only и/analyze: quiet).
  - `/analyze:plugin EspXEngine.dll`При выборе этого варианта модуль расширений анализа кода загружается в предвысокую скорость. Этот модуль, в свою очередь, загружает средство проверки C++ Core Guidelines.

## <a name="use-the-guideline-support-library"></a>Использование библиотеки поддержки рекомендаций

Библиотека поддержки рекомендаций предназначена для того, чтобы помочь вам следовать основным рекомендациям. GSL включает определения, позволяющие заменять подверженные ошибкам конструкции более безопасными альтернативами. Например, можно заменить `T*, length` пару параметров на `span<T>` тип. GSL доступен по адресу [http://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl) . Библиотека является открытым исходным кодом, поэтому вы можете просматривать источники, создавать комментарии или участвовать в программе. Проект можно найти по адресу [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a>Использование C++ Core Check рекомендаций в проектах Visual Studio 2015

При использовании Visual Studio 2015 наборы правил анализа кода C++ Core Check не устанавливаются по умолчанию. Перед включением средств анализа кода C++ Core Check в Visual Studio 2015 необходимо выполнить некоторые дополнительные действия. Корпорация Майкрософт предоставляет поддержку проектов Visual Studio 2015 с помощью пакета NuGet. Пакет называется Microsoft. CppCoreCheck и доступен по адресу [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) . Для этого пакета требуется по крайней мере Visual Studio 2015 с обновлением 1.

Пакет также устанавливает другой пакет как зависимость — библиотеку поддержки рекомендаций только для заголовков (GSL). GSL также доступен на сайте GitHub по адресу [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

Из-за способа загрузки правил анализа кода необходимо установить пакет NuGet Microsoft. CppCoreCheck в каждый проект C++, который требуется проверить в Visual Studio 2015.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Добавление пакета Microsoft. CppCoreCheck в проект в Visual Studio 2015

1. В **Обозреватель решений**щелкните правой кнопкой мыши, чтобы открыть контекстное меню проекта в решении, в которое требуется добавить пакет. Выберите **Управление пакетами NuGet** , чтобы открыть **Диспетчер пакетов NuGet**.

1. В окне **Диспетчер пакетов NuGet** найдите Microsoft. CppCoreCheck.

    ![В окне диспетчера пакетов NuGet отображается пакет CppCoreCheck](../code-quality/media/cppcorecheck_nuget_window.png)

1. Выберите пакет Microsoft. CppCoreCheck, а затем нажмите кнопку " **установить** ", чтобы добавить правила в проект.

   Пакет NuGet добавляет дополнительный файл MSBuild *. targets* в проект, который вызывается при включении анализа кода для проекта. Этот файл *Targets* добавляет правила C++ Core Check в качестве дополнительного расширения для средства анализа кода Visual Studio. После установки пакета можно использовать диалоговое окно страницы свойств, чтобы включить или отключить правила выпуска и экспериментального использования.

## <a name="see-also"></a>См. также статью

- [Справочник по Visual Studio C++ Core Check](code-analysis-for-cpp-corecheck.md)
