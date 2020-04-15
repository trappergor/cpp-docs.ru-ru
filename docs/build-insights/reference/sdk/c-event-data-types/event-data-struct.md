---
title: структура EVENT_DATA
description: Ссылка на структуру СЗ Build Insights SDK EVENT_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ce396febe278c5e7c34fe170939c9522913f92a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325599"
---
# <a name="event_data-structure"></a>структура EVENT_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `EVENT_DATA` описывает событие, полученное в ходе анализа или сеанса перезаписи. Эти сеансы начинаются с вызова функций [Analyse,](../functions/analyze.md) [AnalyseA,](../functions/analyze-a.md) [AnalyseW,](../functions/analyze-w.md) [Relog,](../functions/relog.md) [RelogA](../functions/relog-a.md)или [RelogW.](../functions/relog-w.md)

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct EVENT_DATA_TAG
{
    unsigned short          EventId;
    unsigned long long      EventInstanceId;

    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;
    long long               ExclusiveDurationTicks;
    long long               CPUTicks;
    long long               ExclusiveCPUTicks;
    long long               WallClockTimeResponsibilityTicks;
    long long               ExclusiveWallClockTimeResponsibilityTicks;

    const void*             Data;

    unsigned long           ProcessId;
    unsigned long           ThreadId;
    unsigned short          ProcessorIndex;

    const char*             EventName;
    const wchar_t*          EventWideName;

} EVENT_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `EventId` | Номер, идентифицирующие событие. Список идентификаторов событий можно узнать [EVENT_ID.](event-id-enum.md) |
| `EventInstanceId` | Номер, который однозначно идентифицирует текущее событие внутри трассы. Это значение не изменяется при анализе или повторном прослеживании одного и того же следа несколько раз. Используйте это поле для определения одного и того же события в нескольких анализа или перезаписи проходов по тому же следу. |
| `TickFrequency` | Количество тиков в секунду для использования при оценке продолжительности, измеренной в клещах. |
| `StartTimestamp` | Когда событие является *действием,* это поле настроено на значение тика, захваченное во время начала действия. Если это событие является *простым событием,* это поле настроено на значение тика, захваченное во время события. |
| `StopTimestamp` | Когда событие является *действием,* это поле настроено на значение тика, захваченное во время остановки действия. Если событие остановки еще не получено для этого действия, это поле настроено до нуля. Если это событие является *простым событием,* это поле настроено на ноль. |
| `ExclusiveDurationTicks` | Если это событие является *действием,* это поле устанавливается на количество тиков, которые произошли непосредственно в этом действии. Количество тиков, которые произошли в деятельности ребенка, исключено. Это поле установлено к нулю для *простых событий.* |
| `CPUTicks` | Если это событие является *действием,* это поле устанавливается на количество тиков процессора, которые произошли во время этого действия. Тик процессора отличается от обычного тика. Клещи процессора учитываются только тогда, когда CPU исполняет код в действии. Тики процессора не учитываются при сном потоке, связанном с действием. Это поле установлено к нулю для *простых событий.* |
| `ExclusiveCPUTicks` | Это поле имеет такое же значение, как, `CPUTicks`за исключением того, что оно не включает клещи процессора, которые произошли в детских мероприятиях. Это поле установлено к нулю для *простых событий.* |
| `WallClockTimeResponsibilityTicks` | Если это событие является *действием,* это поле настроено на подсчет тика, который отражает вклад этого действия в общее время настенных часов. Настенные часы время ответственность тик отличается от обычного тика. Ответственность за время стены учитывает параллелизм между действиями. Например, два параллельных действия могут иметь продолжительность 50 тиков и одно и то же время начала и остановки. В этом случае обоим будет назначена ответственность за время настенных часов в размере 25 тиков. Это поле установлено к нулю для *простых событий.* |
| `ExclusiveWallClockTimeResponsibilityTicks` | Это поле имеет такое же значение, как `WallClockTimeResponsibilityTicks`, за исключением того, что он не включает в себя настенные часы время ответственности тикает деятельности детей. Это поле установлено к нулю для *простых событий.* |
| `Data` | Очки на дополнительные данные, хранящиеся в случае. Тип данных, на которые указывается, `EventId` отличается в зависимости от поля. |
| `ProcessId` | Идентификатор процесса, в котором произошло событие. |
| `ThreadId` | Идентификатор для потока, в котором произошло событие. |
| `ProcessorIndex` | Номер процессора с нулевым индексом, на котором произошло событие. |
| `EventName` | Строка ANSI, содержащая имя `EventId`объекта, идентифицированного . |
| `EventWideName` | Широкая строка, содержащая `EventId`имя объекта, идентифицированного . |

## <a name="remarks"></a>Remarks

Многие поля `EVENT_DATA` в содержат количество тиков. В качестве источника тиков используется счетчик производительности Window. Подсчет тиков должен использоваться с полем, `TickFrequency` чтобы преобразовать его в соответствующую единицу времени, такую как секунды. Приведенный ниже пример для выполнения этого преобразования. `EVENT_DATA`не содержит поля для регулярного подсчета тиков оговора деятельности. Чтобы получить это значение, вычесть `StartTimestamp` из `StopTimestamp`. `EVENT_DATA`— это структура, предназначенная для использования пользователями C API. Для пользователей API СЗ, такие классы, как [Event,](../cpp-event-data-types/event.md) автоматически переражают время.

Значение `EVENT_DATA` `Data` поля зависит от стоимости `EventId` его поля. Значение `Data` описано в таблице ниже. Некоторые идентификаторы сущности могут отсутствовать в таблице ниже. В этом случае `Data` поле настроено до `nullptr` нуля.

| Значение `EventId` | Тип, на который указывается`Data` |
|--|--|
| `EVENT_ID_BACK_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_COMMAND_LINE` | `const wchar_t` |
| `EVENT_ID_COMPILER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | [NAME_VALUE_PAIR_DATA](name-value-pair-data-struct.md) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_EXP_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FILE_INPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FORCE_INLINE` | [FUNCTION_FORCE_INLINEE_DATA](function-force-inlinee-data-struct.md) |
| `EVENT_ID_FRONT_END_FILE` | [FRONT_END_FILE_DATA](front-end-file-data-struct.md) |
| `EVENT_ID_FRONT_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_FUNCTION` | [FUNCTION_DATA](function-data-struct.md) |
| `EVENT_ID_IMP_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LINKER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_OBJ_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_SYMBOL_NAME` | [SYMBOL_NAME_DATA](symbol-name-data-struct.md) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | [TEMPLATE_INSTANTIATION_DATA](template-instantiation-data-struct.md) |

## <a name="tick-conversion-example"></a>Пример преобразования клещей

```cpp
//
// We have the elapsed number of ticks, along with the
// number of ticks per second. We use these values
// to convert to the number of elapsed microseconds.
// To guard against loss-of-precision, we convert
// to microseconds *before* dividing by ticks-per-second.
//

long long ConvertDurationToMicroseconds(const sruct EVENT_DATA& eventData)
{
    long long duration = eventData.StopTimestamp - eventData.StartTimestamp;
    long long duration *= 1000000;
    return duration / eventData.TickFrequency;
}
```

::: moniker-end
