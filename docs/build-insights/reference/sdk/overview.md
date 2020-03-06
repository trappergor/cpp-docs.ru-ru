---
title: C++Пакет SDK для сборки Insights
description: Обзор пакета SDK для Visual Studio C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5aafcc65bc30de77131d1945c9f4e78361db14ed
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334034"
---
# <a name="c-build-insights-sdk"></a>C++Пакет SDK для сборки Insights

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Пакет C++ SDK для Build Insights — это набор интерфейсов API, позволяющих создавать персонализированные средства на основе платформы C++ Build Insights. На этой странице представлен общий обзор, который поможет вам приступить к работе.

## <a name="obtaining-the-sdk"></a>Получение пакета SDK

Пакет SDK для C++ сборки Insights можно скачать как пакет NuGet, выполнив следующие действия.

1. В Visual Studio 2017 и более поздних версиях создайте C++ новый проект.
1. В области **Обозреватель решений** щелкните проект правой кнопкой мыши.
1. В контекстном меню выберите пункт **Управление пакетами NuGet** .
1. В правом верхнем углу выберите источник пакета **NuGet.org** .
1. Найдите последнюю версию пакета Microsoft. cpp. Буилдинсигхтс.
1. Нажмите кнопку **установить**.
1. Примите условия лицензии.

Ознакомьтесь со сведениями об общих понятиях, связанных с пакетом SDK. Для просмотра примеров реальных C++ приложений, использующих пакет SDK, можно также получить доступ к официальному [ C++ репозиторию примеров для Application Insights GitHub](https://github.com/microsoft/cpp-build-insights-samples) .

## <a name="collecting-a-trace"></a>Сбор данных трассировки

С помощью C++ пакета SDK для Build Insights для анализа событий, исходящих из компилятором MSVC цепочки инструментов, необходимо сначала собрать трассировку. Пакет SDK использует средство трассировки событий Windows (ETW) в качестве базовой технологии трассировки. Сбор данных трассировки может осуществляться двумя способами:

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>Метод 1. Использование вкперф в Visual Studio 2019 и более поздних версий

1. Откройте командная строка Native Tools x64 с повышенными правами для VS 2019.
1. Выполните следующую команду: `vcperf /start MySessionName`
1. Выполните сборку проекта.
1. Выполните следующую команду: `vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > Используйте команду `/stopnoanalyze` при остановке трассировки с помощью вкперф. Пакет SDK для C++ Build Insights нельзя использовать для анализа трассировок, остановленных обычной командой `/stop`.

### <a name="method-2-programmatically"></a>Метод 2. программный

Используйте любую из этих C++ функций сбора данных трассировки пакета SDK для аналитики, чтобы программно запускать и прекращать трассировку. **Программа, выполняющая эти вызовы функций, должна иметь права администратора.** Права администратора требуются только для функций трассировки запуск и завершение. Все остальные функции пакета SDK C++ для Build Insights можно выполнять без них.

### <a name="sdk-functions-related-to-trace-collection"></a>Функции пакета SDK, относящиеся к сбору трассировки

| Функциональность | API C++ | API C |
|--|--|--|
| Запуск трассировки | [старттраЦингсессион](functions/start-tracing-session.md) | [старттраЦингсессиона](functions/start-tracing-session-a.md)<br />[старттраЦингсессионв](functions/start-tracing-session-w.md) |
| Остановка трассировки | [стоптраЦингсессион](functions/stop-tracing-session.md) | [стоптраЦингсессиона](functions/stop-tracing-session-a.md)<br />[стоптраЦингсессионв](functions/stop-tracing-session-w.md) |
| Остановка трассировки и<br />немедленное анализ результата | [стопанданализетраЦингсессион](functions/stop-and-analyze-tracing-session.md) | [стопанданализетраЦингсессиона](functions/stop-and-analyze-tracing-session-a.md)<br />[стопанданализетраЦингсессион](functions/stop-and-analyze-tracing-session-w.md) |
| Остановка трассировки и<br />немедленное перезапись результатов | [стопандрелогтраЦингсессион](functions/stop-and-relog-tracing-session.md) | [стопандрелогтраЦингсессиона](functions/stop-and-relog-tracing-session-a.md)<br />[стопандрелогтраЦингсессионв](functions/stop-and-relog-tracing-session-w.md) |

В следующих разделах показано, как настроить анализ или сеанс повторного ведения журнала. Он необходим для функций Объединенных функций, таких как [стопанданализетраЦингсессион](functions/stop-and-analyze-tracing-session.md).

## <a name="consuming-a-trace"></a>Использование трассировки

После трассировки ETW используйте пакет SDK для C++ сборки Insights, чтобы распаковать его. Пакет SDK предоставляет события в формате, который позволяет быстро разрабатывать средства. Мы не рекомендуем использовать необработанную трассировку ETW без использования пакета SDK. Формат событий, используемый КОМПИЛЯТОРОМ MSVC, не документирован, оптимизирован для увеличения масштаба до огромных сборок и сложно понять. Кроме того, C++ API пакета SDK для аналитики сборки является стабильным, в то время как Необработанный формат трассировки ETW может быть изменен без предварительного уведомления.

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>Типы и функции пакета SDK, связанные с потреблением трассировки

| Функциональность | API C++ | API C | Примечания |
|--|--|--|--|
| Настройка обратных вызовов событий | [ианализер](other-types/ianalyzer-class.md)<br />[ирелогжер](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | Пакет C++ SDK для Build Insights предоставляет события с помощью функций обратного вызова. В C++Реализуйте функции обратного вызова, создав анализатор или класс повторного ведения журнала, который наследует интерфейс Ианализер или ирелогжер. В языке C реализуйте обратные вызовы в глобальных функциях и налагаюте указатели на них в структуре ANALYSIS_CALLBACKS или RELOG_CALLBACKS. |
| Создание групп | [макестатиканализерграуп](functions/make-static-analyzer-group.md)<br />[макестатикрелогжерграуп](functions/make-static-relogger-group.md)<br />[макединамиканализерграуп](functions/make-dynamic-analyzer-group.md)<br />[макединамикрелогжерграуп](functions/make-dynamic-relogger-group.md) |  | C++ API предоставляет вспомогательные функции и типы для объединения нескольких анализаторов и объектов многократного ведения журнала. Группы — это аккуратный способ разделить сложный анализ на более простые шаги. [вкперф](https://github.com/microsoft/vcperf) организованы таким образом. |
| Анализ или повторный вход | [Анализ](functions/analyze.md)<br />[Загрузить](functions/relog.md) | [Анализ](functions/analyze-a.md)<br />[анализев](functions/analyze-w.md)<br />[релога](functions/relog-a.md)<br />[релогв](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>Анализ и повторный вход

Использование трассировки выполняется либо в сеансе анализа, либо в сеансе повторного ведения журнала.

Использование обычного анализа подходит для большинства сценариев. Этот метод предоставляет гибкие возможности выбора формата выходных данных: `printf` Text, XML, JSON, Database, Calls и т. д.

Повторное ведение журнала предназначено для анализа специальных целей, требующих создания выходного файла ETW. С помощью повторного ведения журнала можно преобразовать C++ события сборки Insights в собственный формат событий ETW. Подходящее использование переведения журнала — привязать C++ данные аналитики к существующим средствам и инфраструктуре ETW. Например, [вкперф](https://github.com/microsoft/vcperf) использует интерфейсы перезаписи в журнал. Это обусловлено тем, что он должен создавать данные, которые может понять анализатор производительности Windows, средство ETW. Некоторые знания о том, как работает ETW, необходимы, если вы планируете использовать интерфейсы повторного протоколирования.

### <a name="creating-analyzer-groups"></a>Создание групп анализаторов

Важно уметь создавать группы. Ниже приведен пример, в котором показано, как создать группу анализаторов, которая выводит *Hello, World!* для каждого события начала действия, которое он получает.

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
| Сопоставление и фильтрация событий | [матчевентстаккинмемберфунктион](functions/match-event-stack-in-member-function.md)<br />[матчевентстакк](functions/match-event-stack.md)<br />[матчевентинмемберфунктион](functions/match-event-in-member-function.md)<br />[матчевент](functions/match-event.md) |  | C++ API предоставляет функции, которые позволяют легко извлекать события, которые вам интересуют. При использовании C API Эта фильтрация должна выполняться вручную. |
| Типы данных событий | [Действие](cpp-event-data-types/activity.md)<br />[баккендпасс](cpp-event-data-types/back-end-pass.md)<br />[боттомуп](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[Стратегию](cpp-event-data-types/code-generation.md)<br />[Команд](cpp-event-data-types/command-line.md)<br />[Компилятора](cpp-event-data-types/compiler.md)<br />[компилерпасс](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[Событие](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[евентстакк](cpp-event-data-types/event-stack.md)<br />[ексекутаблеимажеаутпут](cpp-event-data-types/executable-image-output.md)<br />[експаутпут](cpp-event-data-types/exp-output.md)<br />[филеинпут](cpp-event-data-types/file-input.md)<br />[филеаутпут](cpp-event-data-types/file-output.md)<br />[форцеинлини](cpp-event-data-types/force-inlinee.md)<br />[фронтендфиле](cpp-event-data-types/front-end-file.md)<br />[фронтендфилеграуп](cpp-event-data-types/front-end-file-group.md)<br />[фронтендпасс](cpp-event-data-types/front-end-pass.md)<br />[Компонент](cpp-event-data-types/function.md)<br />[имплибаутпут](cpp-event-data-types/imp-lib-output.md)<br />[Вызов](cpp-event-data-types/invocation.md)<br />[инвокатионграуп](cpp-event-data-types/invocation-group.md)<br />[либаутпут](cpp-event-data-types/lib-output.md)<br />[Компоновщик](cpp-event-data-types/linker.md)<br />[линкерграуп](cpp-event-data-types/linker-group.md)<br />[линкерпасс](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[обжаутпут](cpp-event-data-types/obj-output.md)<br />[оптикф](cpp-event-data-types/opt-icf.md)<br />[оптлбр](cpp-event-data-types/opt-lbr.md)<br />[оптреф](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[прелткгоптреф](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[симпливент](cpp-event-data-types/simple-event.md)<br />[симболнаме](cpp-event-data-types/symbol-name.md)<br />[темплатеинстантиатион](cpp-event-data-types/template-instantiation.md)<br />[темплатеинстантиатионграуп](cpp-event-data-types/template-instantiation-group.md)<br />[Поток](cpp-event-data-types/thread.md)<br />[топдовн](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[вхолепрограманалисис](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>Действия и простые события

События бывают двух категорий: *действия* и *простые события*. Действия — это непрерывные процессы, имеющие начало и конец. Простые события являются пунктуал вхождениями и не имеют длительности. При анализе трассировок КОМПИЛЯТОРОМ MSVC с помощью C++ пакета SDK для Build Insights вы получаете отдельные события при запуске и остановке действия. При возникновении простого события будет получено только одно событие.

### <a name="parent-child-relationships"></a>Связи типа «родители-потомки»

Действия и простые события связаны друг с другом через связи типа «родители-потомки». Родителем действия или простого события является охватывающая операция, в которой они происходят. Например, при компиляции исходного файла компилятор должен проанализировать файл, а затем создать код. Операции синтаксического анализа и создания кода являются дочерними элементами действия компилятора.

Простые события не имеют длительности, поэтому в них не может быть ничего другого. Таким образом, они никогда не имеют дочерних элементов.

Связи типа «родители-потомки» для каждого действия и простого события указываются в [таблице событий](event-table.md). Знание этих связей важно при использовании событий C++ сборки Insights. Часто приходится полагаться на них, чтобы понять полный контекст события.

### <a name="properties"></a>Свойства

Все события имеют следующие свойства.

| Свойство | Description |
|--|--|
| Идентификатор типа | Число, уникально идентифицирующее тип события. |
| Идентификатор экземпляра | Число, однозначно идентифицирующее событие в трассировке. Если в трассировке встречаются два события одного типа, то они получают уникальный идентификатор экземпляра. |
| Время начала | Время начала действия или время возникновения простого события. |
| Идентификатор процесса | Число, идентифицирующее процесс, в котором произошло событие. |
| Идентификатор потока | Число, идентифицирующее поток, в котором произошло событие. |
| Индекс процессора | Отсчитываемый от нуля индекс, указывающий, в каком логическом процессоре было создано событие. |
| Имя события | Строка, описывающая тип события. |

Все действия, Кроме простых событий, также имеют следующие свойства:

| Свойство | Description |
|--|--|
| Время окончания | Время остановки действия. |
| Эксклюзивная длительность | Время, затраченное на действие, за исключением времени, затраченного на его дочерние действия. |
| время ЦП; | Время, затраченное ЦП на выполнение кода в потоке, присоединенном к действию. Он не включает время, когда поток, присоединенный к действию, находится в спящем режиме. |
| Эксклюзивное время ЦП | То же, что и время ЦП, но не исключая время ЦП, потраченное дочерними действиями. |
| Ответственность за почасовое время | Вклад действия в общее время стены. При работе с простенными часами учитывается параллелизм между действиями. Например, предположим, что два несвязанных действия выполняются параллельно. Оба имеют длительность в 10 секунд и точно такие же время начала и окончания. В этом случае при сборке Insights настраивается время работы со временем простенки 5 секунд. В противоположность этому, если эти действия выполняются друг за другом, не перекрываются, им одновременно назначается время прочтения на стене, равное 10 секундам. |
| Ответственность за эксклюзивное время на стене | Это то же самое, что и почасовая обязанность, но не включает в себя ответственность за время работы дочерних действий. |

Некоторые события имеют собственные свойства за пределами упомянутых. В этом случае эти дополнительные свойства перечислены в [таблице событий](event-table.md).

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>Использование событий, предоставленных пакетом SDK для C++ Build Insights

#### <a name="the-event-stack"></a>Стек событий

Каждый раз C++ , когда пакет SDK для аналитики создает событие, он поступает в виде стека. Последняя запись в стеке — это текущее событие, а записи до его родительской иерархии. Например, события начала и окончания [LTCG](event-table.md#ltcg) возникают во время прохода 1 из компоновщика. В этом случае полученный стек содержит: \[[Компоновщик](event-table.md#linker), [PASS1](event-table.md#pass1), LTCG\]. Родительская иерархия удобна, так как вы можете отследить событие до его корневого элемента. Если указанное выше действие LTCG работает медленно, можно сразу узнать, какой вызов компоновщика был задействован.

#### <a name="matching-events-and-event-stacks"></a>Сопоставление событий и стеков событий

Пакет C++ SDK для Build Insights предоставляет все события в трассировке, но в большинстве случаев вы только Следите за их подмножеством. В некоторых случаях может потребоваться только подмножество *стеков событий*. Пакет SDK предоставляет средства, помогающие быстро извлечь нужные события или стек событий, а также отклонить их. Это можно сделать с помощью соответствующих функций:

|  |  |
|--|--|
| [матчевент](functions/match-event.md) | Сохраняет событие, если оно соответствует одному из указанных типов. Пересылка сопоставленных событий в лямбда-или другие вызываемые типы. Эта функция не учитывает родительскую иерархию события. |
| [матчевентинмемберфунктион](functions/match-event-in-member-function.md) | Сохраняет событие, если оно соответствует типу, указанному в параметре функции-члена. Пересылка сопоставленных событий функции члена. Эта функция не учитывает родительскую иерархию события. |
| [матчевентстакк](functions/match-event-stack.md) | Сохраняет событие, если оба события и его родительская иерархия соответствуют указанным типам. Перешлите события и сопоставленные события родительской иерархии в лямбда-или другой вызываемый тип. |
| [матчевентстаккинмемберфунктион](functions/match-event-stack-in-member-function.md) | Сохраняет событие, если оба события и его родительская иерархия соответствуют типам, указанным в списке параметров функции-члена. Перешлите события и сопоставленные события родительской иерархии функции члена. |

Функции сопоставления стека событий, такие как `MatchEventStack`, допускают разрывы при описании соответствия родительской иерархии. Например, вы можете сказать, что вас интересует \[[компоновщика](event-table.md#linker), [LTCG](event-table.md#ltcg)\] Stack. Он также будет соответствовать \[КОМПОНОВЩИКа, [PASS1](event-table.md#pass1), LTCG\] Stack. Последний указанный тип должен быть типом события для сопоставления и не является частью родительской иерархии.

#### <a name="capture-classes"></a>Классы отслеживания

Для использования функций `Match*` необходимо указать типы, которые необходимо сопоставить. Эти типы выбираются из списка *классов отслеживания*. Классы отслеживания бывают в нескольких категориях, описанных ниже.

| Категория | Description |
|--|--|
| Exact | Эти классы отслеживания используются для сопоставления определенного типа событий и других. Примером является класс [компилятора](cpp-event-data-types/compiler.md) , который соответствует событию [компилятора](event-table.md#compiler) . |
| Подстановочный знак | Эти классы отслеживания можно использовать для сопоставления любого события из списка поддерживаемых им событий. Например, шаблон [действия](cpp-event-data-types/activity.md) соответствует любому событию действия. Другим примером является подстановочный знак [компилерпасс](cpp-event-data-types/compiler-pass.md) , который может соответствовать [FRONT_END_PASS](event-table.md#front-end-pass) или [BACK_END_PASS](event-table.md#back-end-pass) события. |
| Группа | Имена классов отслеживания группы, заканчивающиеся на " *Группа*". Они используются для сопоставления нескольких событий одного типа в строке без учета пропусков. Они имеют смысл только при сопоставлении рекурсивных событий, так как неизвестно, сколько существует в стеке событий. Например, [FRONT_END_FILE](event-table.md#front-end-file) действие происходит каждый раз, когда компилятор анализирует файл. Это действие является рекурсивным, так как компилятор может найти директиву include при анализе файла. Класс [фронтендфиле](cpp-event-data-types/front-end-file.md) соответствует только одному событию FRONT_END_FILE в стеке. Используйте класс [фронтендфилеграуп](cpp-event-data-types/front-end-file-group.md) для сопоставления всей иерархии include. |
| Группа подстановочных знаков | Группа с подстановочными знаками объединяет свойства подстановочных знаков и групп. Единственным классом этой категории является [инвокатионграуп](cpp-event-data-types/invocation-group.md), который сопоставляет и записывает все события [компоновщика](event-table.md#linker) и [компилятора](event-table.md#compiler) в одном стеке событий. |

Сведения о том, какие классы отслеживания можно использовать для сопоставления каждого события, см. в [таблице событий](event-table.md) .

#### <a name="after-matching-using-captured-events"></a>После сопоставления: использование захваченных событий

После успешного завершения сопоставления функции `Match*` создают объекты класса Capture и пересылают их в указанную функцию. Используйте эти объекты класса Capture для доступа к свойствам событий.

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
