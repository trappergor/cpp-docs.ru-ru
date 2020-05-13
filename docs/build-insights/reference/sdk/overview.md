---
title: СЗ Сборка Исследования SDK
description: Обзор Визуальной студии СЗ Построить Исследования SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 126abb0d039227eb269500966d46ef0a729763ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323264"
---
# <a name="c-build-insights-sdk"></a>СЗ Сборка Исследования SDK

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

SDK Build Insights — это коллекция AI, которая позволяет создавать персонализированные инструменты поверх платформы «С» Build Insights. Эта страница предоставляет обзор на высоком уровне, чтобы помочь вам начать работу.

## <a name="obtaining-the-sdk"></a>Получение SDK

Вы можете скачать sDK Build Insights в виде пакета NuGet, высовывая следующие действия:

1. Из Visual Studio 2017 и выше, создайте новый проект СЗЗ.
1. В панели **Solution Explorer** нажмите на ваш проект.
1. Выберите **пакеты Управления NuGet** из контекстного меню.
1. В правом верхнем правом положении выберите источник **nuget.org** пакет.
1. Поиск последней версии пакета Microsoft.Cpp.BuildInsights.
1. Выберите **Установить**.
1. Примите лицензию.

Читайте дальше для получения информации об общих концепциях, окружающих SDK. Вы также можете получить доступ к официальным [образцам GitHub, которые используют репозиторий GitHub,](https://github.com/microsoft/cpp-build-insights-samples) чтобы увидеть примеры реальных приложений СЗ, которые используют SDK.

## <a name="collecting-a-trace"></a>Сбор следа

Использование SDK Build Insights для анализа событий, выходящих из цепочки инструментов MSVC, требует, чтобы вы сначала собрали след. SDK использует отслеживание событий для Windows (ETW) в качестве основной технологии отслеживания. Сбор следа можно сделать двумя способами:

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>Метод 1: использование vcperf в Visual Studio 2019 и выше

1. Откройте повышенный x64 Родные инструменты Команды Подсказка для VS 2019.
1. Выполните следующую команду: `vcperf /start MySessionName`
1. Выполните сборку проекта.
1. Выполните следующую команду: `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > Используйте `/stopnoanalyze` команду при остановке трассы с помощью vcperf. Для анализа следов, остановленных обычной `/stop` командой, нельзя использовать SDK Build Insights SDK.

### <a name="method-2-programmatically"></a>Метод 2: программно

Используйте любую из этих функций сбора следов SDK Build Insights SDK, чтобы начать и остановить отслеживание программно. **Программа, выполняя эти вызовы функций, должна иметь административные привилегии.** Только функции отслеживания запуска и остановки требуют административных привилегий. Все остальные функции в SDK Build Insights могут быть выполнены без них.

### <a name="sdk-functions-related-to-trace-collection"></a>Функции SDK, связанные со сбором следов

| Функциональность | API C++ | API C |
|--|--|--|
| Запуск трассы | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingRacingW](functions/start-tracing-session-w.md) |
| Остановка следа | [StopTracingSession](functions/stop-tracing-session.md) | [СтопТрейсингИя](functions/stop-tracing-session-a.md)<br />[StopTracingRacingSessionW](functions/stop-tracing-session-w.md) |
| Остановка следа и<br />немедленно анализируя результат | [StopandAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [СтопэндАнализТрейсингЕЯ](functions/stop-and-analyze-tracing-session-a.md)<br />[StopandAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| Остановка следа и<br />немедленное повторное завораживание результата | [СтопАндрелогТрейсингСессия](functions/stop-and-relog-tracing-session.md) | [СтопАндрелогТрейсингСея](functions/stop-and-relog-tracing-session-a.md)<br />[СтопАндрелогТрейсингСессияW](functions/stop-and-relog-tracing-session-w.md) |

Следующие разделы показывают, как настроить анализ или сеанс перезаписи. Это необходимо для комбинированных функций функциональности, таких как [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md).

## <a name="consuming-a-trace"></a>Потребление следа

Если у вас есть след ETW, используйте SDK Build Insights SDK, чтобы распаковать его. SDK дает вам события в формате, который позволяет быстро разрабатывать инструменты. Мы не рекомендуем вам потреблять сырой след ETW без использования SDK. Формат мероприятия, используемый MSVC, не документирован, оптимизирован для масштабирования до огромных сборок и трудно понять. Кроме того, API SDK Build Insights sDK является стабильным, в то время как необработанный формат трассировки ETW может быть изменен без предварительного уведомления.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>Типы и функции SDK, связанные с потреблением следов

| Функциональность | API C++ | API C | Примечания |
|--|--|--|--|
| Настройка обратных вызовов событий | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | SDK Build Insights обеспечивает события с помощью функций обратного вызова. В c', реализуйте функции обратного вызова, создав класс анализатора или перелога, который наследует интерфейс IAnalyzer или IRelogger. В C реализуйте обратные вызовы в глобальных функциях и предоставляйте указатели на них в ANALYSIS_CALLBACKS или RELOG_CALLBACKS структуре. |
| Строительные группы | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | API СЗ обеспечивает функции и типы помощников для группы нескольких объектов анализатора и перелога. Группы – это аккуратный способ разделить сложный анализ на более простые шаги. [vcperf](https://github.com/microsoft/vcperf) организован таким образом. |
| Анализ или перезапись | [Анализировать](functions/analyze.md)<br />[Релог](functions/relog.md) | [АнализA](functions/analyze-a.md)<br />[АнализW](functions/analyze-w.md)<br />[Релога](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>Анализ и перезапись

Потребление трассировки осуществляется либо через сеанс анализа, либо через сеанс перезаписи.

Использование регулярного анализа подходит для большинства сценариев. Этот метод позволяет вам гибко выбирать `printf` формат вывода: текст, xml, JSON, база данных, REST звонки и так далее.

Повторирование предназначено для специальных анализов, которые должны производить выходной файл ETW. Используя relogging, вы можете перевести события «Сборка» в свой собственный формат событий ETW. Надлежащее использование перезаписи было бы подключить данные по сборке с существующими инструментами и инфраструктурой ETW. Например, [vcperf](https://github.com/microsoft/vcperf) использует интерфейсы перезаписи. Это потому, что он должен производить данные Windows Производительность анализатор, инструмент ETW, может понять. Некоторые предварительные знания о том, как работает ETW, необходимы, если вы планируете использовать интерфейсы перезаписи.

### <a name="creating-analyzer-groups"></a>Создание аналитических групп

Важно знать, как создавать группы. Вот пример, который показывает, как создать группу анализаторов, которая печатает *Hello, World!* для каждого события начала действия, которое оно получает.

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

### <a name="sdk-types-and-functions-related-to-events"></a>Типы и функции SDK, связанные с событиями

| Функциональность | API C++ | API C | Примечания |
|--|--|--|--|
| Соответствие и фильтрация событий | [MatchEventstackinMemberФункция](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberФункция](functions/match-event-in-member-function.md)<br />[МатчСобытие](functions/match-event.md) |  | API-нацим с точки вашего усмотрения предлагает функции, которые позволяют легко извлечь из ваших следов события, которые вам заблагорудуны. С помощью C API эта фильтрация должна быть выполнена вручную. |
| Типы данных событий | [Действие](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[БоттомАп](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[Командный пункт](cpp-event-data-types/command-line.md)<br />[Компилятор](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[Событие](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ИсполняемыйИзображениеВыход](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[ФайлВыход](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[Функция](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[Вызов](cpp-event-data-types/invocation.md)<br />[Призывгруппа](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[Компоновщик](cpp-event-data-types/linker.md)<br />[ЛинкерГрупп](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[ПреЛТКГОпреф](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[СимволИ](cpp-event-data-types/symbol-name.md)<br />[ШаблонМеймикция](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[Поток](cpp-event-data-types/thread.md)<br />[ТопДаун](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[ЦельПрограммноеАнализ](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>Мероприятия и простые мероприятия

События бывают двух категорий: *мероприятия* и *простые события.* Мероприятия являются текущими процессами во времени, которые имеют начало и конец. Простые события являются пунктуальными случаями и не имеют продолжительности. При анализе следов MSVC с помощью SDK Build Insights, вы будете получать отдельные события, когда действие начинается и останавливается. Вы получите только одно событие, когда происходит простое событие.

### <a name="parent-child-relationships"></a>Отношения между родителями и детьми

Мероприятия и простые события связаны друг с другом через отношения между родителями и детьми. Родительским элементом действия или простого события является охватывающая деятельность, в которой они происходят. Например, при компиляции исходного файла компилятор должен разобрать файл, а затем сгенерировать код. Действия по разбору и генерации кода являются детьми деятельности компилятора.

Простые события не имеют продолжительности, так что ничего не может произойти внутри них. Таким образом, у них никогда не бывает детей.

Отношения между родителями и детьми каждого действия и простого события указаны в [таблице событий.](event-table.md) Знание этих отношений важно при потреблении событий « сборка знаний». Часто приходится полагаться на них, чтобы понять весь контекст события.

### <a name="properties"></a>Свойства

Все события имеют следующие свойства:

| Свойство | Описание |
|--|--|
| Тип идентификатора | Номер, который однозначно идентифицирует тип события. |
| Идентификатор инстанции | Номер, который однозначно идентифицирует событие в пределах трассы. Если два события одного и того же типа происходят в следе, оба получают уникальный идентификатор экземпляра. |
| Время начала | Время начала действия действия или время, когда произошло простое событие. |
| Идентификатор процесса | Номер, идентифицирующие процесс, в котором произошло событие. |
| Идентификатор потока | Номер, идентифицирующие поток, в котором произошло событие. |
| Индекс процессора | Индекс с нулевым уровнем, указывающий на то, каким логическим процессором было испущено событием. |
| Имя события | Строка, описывающая тип события. |

Все действия, кроме простых событий, также имеют следующие свойства:

| Свойство | Описание |
|--|--|
| Время остановки | Время, когда действие остановлено. |
| Эксклюзивная продолжительность | Время, проведенное в деятельности, за исключением времени, затраченного на его деятельность ребенка. |
| время ЦП; | Время, которое процессор потратил на выполнение кода в потоке, прилагаемом к действию. Он не включает время, когда поток, прикрепленный к действию, спал. |
| Эксклюзивное время процессора | То же, что и время процессора, но за исключением времени процессора, затраченного на действия ребенка. |
| Ответственность за время ввлатых часов | Вклад деятельности в общее время настенных часов. Ответственность за время работы с настенными часами учитывает параллелизм между видами деятельности. Например, предположим, что два несвязанных действия выполняться параллельно. Оба имеют продолжительность 10 секунд, и точно такой же старт и время остановки. В этом случае Build Insights назначает как ответственность за время настенных часов в 5 секунд. В отличие от этого, если эти действия работают один за другим без перекрытия, они оба назначены стены часы ответственность 10 секунд. |
| Эксклюзивная ответственность за время настенных часов | То же самое, что и ответственность за время работы на стеночном часе, но исключает ответственность за деятельность ребенка. |

Некоторые события имеют свои собственные свойства за пределами упомянутых. В этом случае эти дополнительные свойства перечислены в [таблице событий.](event-table.md)

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>Потребление событий, предоставляемых SDK Build Insights

#### <a name="the-event-stack"></a>Стек событий

Всякий раз, когда SDK Build Insights дает вам событие, оно происходит в виде стека. Последней записью в стеке является текущее событие, а записи— перед его родительской иерархией. Например, события запуска и остановки [LTCG](event-table.md#ltcg) происходят во время прохождения 1 ссылки. В этом случае стек, который \[вы получите, содержит:\] [LINKER,](event-table.md#linker) [PASS1](event-table.md#pass1), LTCG . Родительская иерархия удобна тем, что можно отследить событие до его корня. Если деятельность LTCG, упомянутая выше, является медленной, вы можете сразу узнать, какой ссылка вызов был вовлечен.

#### <a name="matching-events-and-event-stacks"></a>Соответствие событиям и стекам событий

SDK Build Insights дает вам каждое событие в след, но большую часть времени вы заботитесь только о подмножестве из них. В некоторых случаях вы можете заботиться только о подмножестве *стеков событий.* SDK предоставляет средства, которые помогут вам быстро извлечь нужные события или стек событий и отклонить те, которые вы не делаете. Это делается с помощью этих соответствующих функций:

|  |  |
|--|--|
| [МатчСобытие](functions/match-event.md) | Храните событие, если оно соответствует одному из указанных типов. Форвард сопоставлял события с лямбдой или другим вызываемым типом. Иерархия родительской функции события не учитывается этой функцией. |
| [MatchEventInMemberФункция](functions/match-event-in-member-function.md) | Храните событие, если оно соответствует типу, указанному в параметре функции элемента. Форвард сопоставлял события с функцией участника. Иерархия родительской функции события не учитывается этой функцией. |
| [MatchEventStack](functions/match-event-stack.md) | Сохраняйте событие, если и событие, и его родительская иерархия совпадают с указанными типами. Переадрестив событие и совпадающие события родительской иерархии на lambda или другой вызываемый тип. |
| [MatchEventstackinMemberФункция](functions/match-event-stack-in-member-function.md) | Сохраняйте событие, если событие и его родительская иерархия совпадают с типами, указанными в списке параметров функции участника. Переадрестив событие и совпадающие события родительской иерархии в функцию участника. |

Функции сопоставления стеков событий, такие как `MatchEventStack` позволяют сопоставить пробелы при описании родительской иерархии. Например, вы можете сказать, что \[вас интересует стек [LINKER,](event-table.md#linker) [LTCG.](event-table.md#ltcg) \] Он также будет \[соответствовать LINKER,\] [PASS1](event-table.md#pass1), LTCG стек. Последний указанный тип должен соответствовать типу события и не является частью родительской иерархии.

#### <a name="capture-classes"></a>Классы захвата

Использование `Match*` функций требует указания типов, которые вы хотите сопоставить. Эти типы выбираются из списка *классов захвата.* Классы захвата бывают нескольких категорий, описанных ниже.

| Категория | Описание |
|--|--|
| Exact | Эти классы захвата используются для сопоставления определенного типа события и ни одного другого. Примером является класс [Компилятора,](cpp-event-data-types/compiler.md) который соответствует событию [COMPILER.](event-table.md#compiler) |
| Подстановочный знак | Эти классы захвата могут быть использованы для сопоставления любого события из списка событий, которые они поддерживают. Например, подстановочные [знаки активности](cpp-event-data-types/activity.md) совпадает с любым событием активности. Другим примером является подстановочный знак [CompilerPass,](cpp-event-data-types/compiler-pass.md) который может соответствовать [FRONT_END_PASS](event-table.md#front-end-pass) или [BACK_END_PASS](event-table.md#back-end-pass) событию. |
| Группа | Названия классов захвата групп заканчиваются в *группе*. Они используются для сопоставления нескольких событий одного и того же типа подряд, игнорируя пробелы. Они имеют смысл только при сопоставлении рекурсивных событий, потому что вы не знаете, сколько существует в стеке событий. Например, [FRONT_END_FILE](event-table.md#front-end-file) действие происходит каждый раз, когда компилятор разбирает файл. Это действие является повторяющейся, поскольку компилятор может найти директиву включить во время разбора файла. Класс [FrontEndFile](cpp-event-data-types/front-end-file.md) соответствует только одному FRONT_END_FILE событию в стеке. Используйте класс [FrontEndFileGroup,](cpp-event-data-types/front-end-file-group.md) чтобы соответствовать всей иерархии. |
| Группа Wildcard | Группа подстановочных знаков сочетает в себе свойства подстановочных знаков и групп. Единственным классом этой категории является [InvocationGroup](cpp-event-data-types/invocation-group.md), который соответствует и захватывает все события [LINKER](event-table.md#linker) и [COMPILER](event-table.md#compiler) в одном стеке событий. |

Обратитесь к [таблице событий,](event-table.md) чтобы узнать, какие классы захвата могут быть использованы для соответствия каждому событию.

#### <a name="after-matching-using-captured-events"></a>После сопоставления: использование захваченных событий

После успешного завершения матча `Match*` функции строят объекты класса захвата и направляют их в заданную функцию. Используйте эти объекты класса захвата для доступа к свойствам событий.

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
