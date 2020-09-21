---
title: Пакет SDK Аналитики сборки C++
description: Общие сведения о пакете SDK Аналитики сборок C++ для Visual Studio.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6f53a9b6c682a0af7d8a01f6378ed0574d8fa4ca
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041176"
---
# <a name="c-build-insights-sdk"></a>Пакет SDK Аналитики сборки C++

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Пакет SDK Аналитики сборок C++ — это набор API-интерфейсов, позволяющих создавать персонализированные средства на основе платформы Аналитики сборок C++. На этой странице представлены общие сведения, необходимые на начальном этапе работы.

## <a name="obtaining-the-sdk"></a>Получение пакета SDK

Пакет SDK Аналитики сборок C++ можно скачать в виде пакета NuGet, выполнив следующие действия:

1. Откройте Visual Studio 2017 или новее и создайте проект C++.
1. В области **Обозревателя решений** щелкните правой кнопкой мыши свой проект.
1. В контекстном меню выберите **Управление пакетами NuGet**.
1. В правом верхнем углу выберите источник пакета **nuget.org**.
1. Найдите последнюю версию пакета Microsoft.Cpp.BuildInsights.
1. Выберите **Установить**.
1. Примите условия лицензии.

Ознакомьтесь с информацией об общих понятиях, связанных с пакетом SDK. Вы также можете получить доступ к официальному [репозиторию GitHub с примерами Аналитики сборок C++](https://github.com/microsoft/cpp-build-insights-samples), чтобы просмотреть примеры реальных приложений C++, использующих пакет SDK.

## <a name="collecting-a-trace"></a>Сбор данных трассировки

Для анализа событий, исходящих из цепочки инструментов MSVC, с помощью пакета SDK Аналитики сборок C++, сначала необходимо собрать данные трассировки. Пакет SDK использует функцию трассировки событий Windows (ETW) в качестве базовой технологии трассировки. Сбор данных трассировки можно выполнить двумя способами:

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>Метод 1. Использование vcperf в Visual Studio 2019 и более поздних версий

1. Откройте командную строку Native Tools x64 с повышенными привилегиями для VS 2019.
1. Выполните следующую команду: `vcperf /start MySessionName`
1. Построить проект.
1. Выполните следующую команду: `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > При остановке трассировки с помощью vcperf используйте команду `/stopnoanalyze`. Пакет SDK Аналитики сборок C++ нельзя использовать для анализа трассировок, остановленных с помощью обычной команды `/stop`.

### <a name="method-2-programmatically"></a>Метод 2. Программный способ

Используйте любую из этих функций сбора данных трассировки пакета SDK Аналитики сборок C++, чтобы программно запускать и останавливать трассировки. **Для программы, выполняющей эти вызовы функций, необходимы права администратора.** Права администратора требуются только для функций запуска и остановки трассировки. Все остальные функции пакета SDK Аналитики сборок C++ можно выполнять без них.

### <a name="sdk-functions-related-to-trace-collection"></a>Функции пакета SDK, связанные со сбором данных трассировки

| Функциональность | API C++ | API C |
|--|--|--|
| Запуск трассировки | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingSessionW](functions/start-tracing-session-w.md) |
| Остановка трассировки | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| Остановка трассировки и<br />немедленный анализ результата | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| Остановка трассировки и<br />немедленная перерегистрация результата | [StopAndRelogTracingSession](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

В следующих разделах показано, как настроить анализ или сеанс перерегистрации. Это необходимо для функций объединенных возможностей, таких как [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md).

## <a name="consuming-a-trace"></a>Использование трассировки

После выполнения трассировки ETW для распаковки используйте пакет SDK Аналитики сборок C++. Пакет SDK предоставляет события в формате, который позволяет быстро разрабатывать средства. Не рекомендуется использовать необработанные данные трассировки ETW без использования пакета SDK. Формат событий, используемый MSVC, не документирован и оптимизирован для увеличения масштаба до огромных сборок. Он сложен в использовании. Кроме того, API пакета SDK Аналитики сборок C++ является стабильным, в то время как необработанный формат трассировки ETW может быть изменен без предварительного уведомления.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>Типы и функции пакета SDK, связанные с использованием данных трассировки

| Функциональность | API C++ | API C | Примечания |
|--|--|--|--|
| Настройка обратных вызовов событий | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | Пакет SDK Аналитики сборки C++ предоставляет события с помощью функций обратного вызова. При использовании C ++ реализуйте функции обратного вызова, создав класс анализатора или перерегистрации, который наследует интерфейс IAnalyzer или IRelogger. При использовании C реализуйте обратные вызовы в глобальных функциях и предоставьте указатели на них в структуре ANALYSIS_CALLBACKS или RELOG_CALLBACKS. |
| Создание групп | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | API C++ предоставляет вспомогательные функции и типы для группирования нескольких анализаторов и объектов перерегистрации. Группы — это прямой путь к разделению сложного анализа на более простые этапы. Таким образом работает [vcperf](https://github.com/microsoft/vcperf). |
| Анализ или перерегистрация | [Анализ](functions/analyze.md)<br />[Relog](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>Анализ и перерегистрация

Использование данных трассировки выполняется либо в сеансе анализа, либо в сеансе перерегистрации.

Использование обычного анализа подходит для большинства сценариев. Этот метод предоставляет гибкие возможности для выбора формата выходных данных: текст `printf`, XML, JSON, база данных, вызовы REST и т. д.

Перерегистрация предназначена для анализа специальных целей, требующих создания выходного файла ETW. С помощью перерегистрации можно преобразовать события Аналитики сборок C++ в собственный формат событий ETW. Надлежащим использованием перерегистрации является привязка данных Аналитики сборок C++ к имеющимся средствам и инфраструктуре ETW. Например, [vcperf](https://github.com/microsoft/vcperf) использует интерфейсы перерегистрации. Это обусловлено тем, что это средство должно создавать данные, которые может понять Windows Performance Analyzer, средство ETW. Если вы планируете использовать интерфейсы перерегистрации, вам необходимо иметь представление о функционировании ETW.

### <a name="creating-analyzer-groups"></a>Создание групп анализаторов

Сведения о создании групп очень важны. Ниже приведен пример, демонстрирующий создание группы анализаторов, которая выводит *Hello, World!* для каждого полученного события запуска действия.

```cpp
using namespace Microsoft::Cpp::BuildInsights;

class Hello : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "Hello, " << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

class World : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "world!" << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

int main()
{
    Hello hello;
    World world;

    // Let's make Hello the first analyzer in the group
    // so that it receives events and prints "Hello, "
    // first.
    auto group = MakeStaticAnalyzerGroup(&hello, &world);

    unsigned numberOfAnalysisPasses = 1;

    // Calling this function initiates the analysis and
    // forwards all events from "inputTrace.etl" to my analyzer
    // group.
    Analyze("inputTrace.etl", numberOfAnalysisPasses, group);

    return 0;
}
```

## <a name="using-events"></a>Использование событий

### <a name="sdk-types-and-functions-related-to-events"></a>Типы и функции пакета SDK, связанные с событиями

| Функциональность | API C++ | API C | Примечания |
|--|--|--|--|
| Сортировка и фильтрация событий | [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberFunction](functions/match-event-in-member-function.md)<br />[MatchEvent](functions/match-event.md) |  | API C++ предоставляет функции, которые позволяют легко извлекать необходимые события из данных трассировки. При использовании API C эту фильтрацию необходимо выполнять вручную. |
| Типы данных событий | [Действие](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[CommandLine](cpp-event-data-types/command-line.md)<br />[Компилятор](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[Событие](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[FileOutput](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[Function](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[Вызов](cpp-event-data-types/invocation.md)<br />[InvocationGroup](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[Компоновщик](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[SymbolName](cpp-event-data-types/symbol-name.md)<br />[TemplateInstantiation](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[Поток](cpp-event-data-types/thread.md)<br />[TopDown](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>Действия и простые события

Существует две категории событий: *действия* и *простые события*. Действия — это текущие процессы, имеющие начало и конец. Простые события являются мгновенными вхождениями и не имеют длительности. При анализе трассировок MSVC с помощью пакета SDK Аналитики сборок C++ вы получаете отдельные события для запуска и остановки действия. В случае простого события вы получите лишь одно событие.

### <a name="parent-child-relationships"></a>Родительско-дочерние связи

Между действиями и простыми событиями существуют родительско-дочерние связи. Родительским элементом действия или простого события является комплексная операция, во время выполнения которой они возникают. Например, при компиляции исходного файла компилятор должен проанализировать файл, а затем создать код. Действия анализа и создания кода являются дочерними элементами операции компилятора.

Простые события не имеют длительности, поэтому во время их выполнения ничего не может произойти. Таким образом, они никогда не имеют дочерних элементов.

Родительско-дочерние связи для каждого действия и простого события указаны в [таблице событий](event-table.md). Знание этих связей важно при использовании событий Аналитики сборок C++. Часто оно необходимо для понимания полного контекста события.

### <a name="properties"></a>Свойства

Все события имеют следующие свойства:

| Свойство | Описание |
|--|--|
| Идентификатор типа | Код, который уникально идентифицирует тип события. |
| Идентификатор экземпляра | Код, который уникально идентифицирует событие в трассировке. Если в трассировке встречаются два события одного типа, то они получают уникальный идентификатор экземпляра. |
| Время начала | Время начала действия или время возникновения простого события. |
| Идентификатор процесса | Код, который идентифицирует процесс, в котором возникло текущее событие. |
| Идентификатор потока | Код, который идентифицирует поток, в котором возникло текущее событие. |
| Индекс процессора | Указатель, начинающийся с нуля, который указывает на логический процессор, в котором было создано событие. |
| Имя события | Строка с описанием типа события. |

Все действия, кроме простых событий, также имеют следующие свойства:

| Свойство | Описание |
|--|--|
| Время остановки | Время, когда было остановлено действие. |
| Исключительная длительность | Время, затраченное на действие, без учета времени, затраченного на выполнение его дочерних действий. |
| Время ЦП | Время, затраченное ЦП на выполнение кода в потоке, присоединенном к действию. Не включает время пребывания в спящем режиме потока, присоединенного к действию. |
| Эксклюзивное время ЦП | То же, что и время ЦП, но без учета времени ЦП, потраченного на выполнение дочерних действий. |
| Время выполнения по часам | Вклад действия в общее время выполнения по часам. В реальном времени выполнения учитывается параллелизм при выполнении действий. Например, предположим, что два несвязанных действия выполняются параллельно. Длительность обоих составляет 10 секунд и точно такое же время начала и окончания. В этом случае Аналитика сборок присвоит обоим процессам значение 5 тактов времени по часам. В противоположность этому, если эти действия выполняются друг за другом (не параллельно), им назначается значение 10 тактов времени по часам. |
| Исключительное время выполнения по часам | Это то же самое, что и время выполнения по часам, но без учета времени выполнения дочерних действий по часам. |

Некоторые события имеют собственные свойства, которые не упомянуты здесь. Эти дополнительные свойства перечислены в [таблице событий](event-table.md).

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>Использование событий, предоставленных пакетом SDK Аналитики сборок C++

#### <a name="the-event-stack"></a>Стек событий

Каждый раз, когда пакет SDK Аналитики сборок C++ предоставляет событие, оно поступает в виде стека. Последняя запись в стеке — это текущее событие, а записи до этого — родительская иерархия. Например, события запуска и завершение [LTCG](event-table.md#ltcg) происходят во время 1-го прохода компоновщика. В этом случае полученный стек содержит: \[[LINKER](event-table.md#linker), [PASS1](event-table.md#pass1), LTCG\]. Родительская иерархия удобна, так как вы можете отследить событие до его корневого элемента. Если указанное выше действие LTCG работает медленно, можно сразу узнать, какой вызов компоновщика был задействован.

#### <a name="matching-events-and-event-stacks"></a>Сопоставление событий и стеков событий

Пакет SDK Аналитики сборок C++ предоставляет каждое событие в трассировке, но в большинстве случаев вам нужно только их подмножество. В некоторых случаях может потребоваться только подмножество *стеков событий*. Пакет SDK предоставляет средства, помогающие быстро извлечь нужные события или стек событий, а также отклонить ненужные. Это можно сделать с помощью этих подходящих функций:

| Функция | Описание |
|--|--|
| [MatchEvent](functions/match-event.md) | Сохраняет событие, если оно соответствует одному из указанных типов. Переадресовывает сопоставленные события в лямбда или другие вызываемые типы. Эта функция не учитывает родительскую иерархию события. |
| [MatchEventInMemberFunction](functions/match-event-in-member-function.md) | Сохраняет событие, если оно соответствует типу, указанному в параметре функции-члена. Переадресовывает сопоставленные события в функцию-член. Эта функция не учитывает родительскую иерархию события. |
| [MatchEventStack](functions/match-event-stack.md) | Сохраняет событие, если и событие, и его родительская иерархия соответствуют указанным типам. Переадресовывает событие и сопоставленные события родительской иерархии в лямбда или другие вызываемые типы. |
| [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md) | Сохраняет событие, если и событие, и его родительская иерархия соответствуют типам, указанным в списке параметров функции-члена. Переадресовывает событие и сопоставленные события родительской иерархии в функцию-член. |

Подходящие функции стека событий, такие как `MatchEventStack`, допускают пропуски при описании родительской иерархии для сопоставления. Например, вас интересует стек \[[LINKER](event-table.md#linker), [LTCG](event-table.md#ltcg)\]. Он также будет соответствовать стеку \[LINKER, [PASS1](event-table.md#pass1), LTCG\]. Последний указанный тип должен быть типом события для сопоставления. Он не является частью родительской иерархии.

#### <a name="capture-classes"></a>Классы фиксации

Для использования функций `Match*` необходимо указать типы для сопоставления. Эти типы выбираются из списка *классов записи*. Классы записи могут иметь несколько категорий, которые описаны ниже.

| Категория | Описание |
|--|--|
| Exact | Эти классы записи используются только для сопоставления определенного типа событий. Примером является класс [Compiler](cpp-event-data-types/compiler.md), который соответствует событию [COMPILER](event-table.md#compiler). |
| Подстановочный знак | Эти классы записи можно использовать для сопоставления любого события из списка поддерживаемых ими событий. Например, подстановочный знак [Activity](cpp-event-data-types/activity.md) соответствует любому событию действия. Еще один пример — подстановочный знак [CompilerPass](cpp-event-data-types/compiler-pass.md), который может соответствовать [FRONT_END_PASS](event-table.md#front-end-pass) или [BACK_END_PASS](event-table.md#back-end-pass). |
| Group | В конце имен классов групповой записи указано *Group*. Они используются для сопоставления нескольких событий одного типа в строке без учета пропусков. Они имеют смысл только при сопоставлении рекурсивных событий, так как их количество в стеке событий неизвестно. Например, действие [FRONT_END_FILE](event-table.md#front-end-file) происходит каждый раз, когда компилятор анализирует файл. Это действие является рекурсивным, так как компилятор может найти директиву include при анализе файла. Класс [FrontEndFile](cpp-event-data-types/front-end-file.md) соответствует только одному событию FRONT_END_FILE в стеке. Используйте класс [FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) для сопоставления всей иерархии include. |
| Группа подстановочных знаков | Группа подстановочных знаков объединяет свойства подстановочных знаков и групп. Единственным классом этой категории является [InvocationGroup](cpp-event-data-types/invocation-group.md), который сопоставляет и записывает все события [LINKER](event-table.md#linker) и [COMPILER](event-table.md#compiler) в одном стеке событий. |

Сведения о том, какие классы захвата можно использовать для сопоставления каждого события, см. в [таблице событий](event-table.md).

#### <a name="after-matching-using-captured-events"></a>После сопоставления: использование записанных событий

После успешного завершения сопоставления функции `Match*` создают объекты класса capture и пересылают их в указанную функцию. Используйте эти объекты класса capture для доступа к свойствам событий.

#### <a name="example"></a>Пример

```cpp
AnalysisControl MyAnalyzer::OnStartActivity(const EventStack& eventStack)
{
    // The event types to match are specified in the PrintIncludes function
    // signature.  
    MatchEventStackInMemberFunction(eventStack, this, &MyAnalyzer::PrintIncludes);
}

// We want to capture event stacks where:
// 1. The current event is a FrontEndFile activity.
// 2. The current FrontEndFile activity has at least one parent FrontEndFile activity
//    and possibly many.
void PrintIncludes(FrontEndFileGroup parentIncludes, FrontEndFile currentFile)
{
    // Once we reach this point, the event stack we are interested in has been matched.
    // The current FrontEndFile activity has been captured into 'currentFile', and
    // its entire inclusion hierarchy has been captured in 'parentIncludes'.

    cout << "The current file being parsed is: " << currentFile.Path() << endl;
    cout << "This file was reached through the following inclusions:" << endl;

    for (auto& f : parentIncludes)
    {
        cout << f.Path() << endl;
    }
}
```

::: moniker-end
