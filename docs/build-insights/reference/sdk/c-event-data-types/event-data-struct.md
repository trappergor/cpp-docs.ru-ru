---
title: Структура EVENT_DATA
description: В C++ пакете SDK для аналитики сборки EVENT_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 572cbdaba346ddb77b665b5677b978c83a80aa3d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857097"
---
# <a name="event_data-structure"></a>Структура EVENT_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `EVENT_DATA` описывает событие, полученное из сеанса анализа или перезаписи в журнал. Эти сеансы запускаются путем вызова функций [Analyze](../functions/analyze.md), [Analyze](../functions/analyze-a.md), [анализев](../functions/analyze-w.md), [Relog](../functions/relog.md), [релога](../functions/relog-a.md)или [релогв](../functions/relog-w.md) .

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

## <a name="members"></a>Члены

|  |  |
|--|--|
| `EventId` | Число, идентифицирующее событие. Список идентификаторов событий см. в разделе [EVENT_ID](event-id-enum.md). |
| `EventInstanceId` | Число, однозначно идентифицирующее текущее событие в трассировке. Это значение не изменяется при многократном анализе или регистрации одной и той же трассировки несколько раз. Используйте это поле для обнаружения одного и того же события при нескольких анализа или перезаписи в ходе одной трассировки. |
| `TickFrequency` | Число тактов в секунду, используемое при вычислении длительности, измеряемой в тактах. |
| `StartTimestamp` | Если событие является *действием*, для этого поля устанавливается значение Tick, захваченное при запуске действия. Если это событие является *простым*, для этого поля задается значение Tick, захваченное на момент возникновения события. |
| `StopTimestamp` | Если событие является *действием*, для этого поля задается значение Tick, захваченное на момент остановки действия. Если событие «завершение» еще не было получено для этого действия, это поле устанавливается в нулевое значение. Если это событие является *простым*, это поле устанавливается в нулевое значение. |
| `ExclusiveDurationTicks` | Если это событие является *действием*, в этом поле задается число тактов, которые произошли непосредственно в этом действии. Число тактов, произошедших в дочерней операции. Для *простых событий*это поле имеет значение 0. |
| `CPUTicks` | Если это событие является *действием*, в этом поле задается число тактов ЦП, произошедших во время этого действия. Такт ЦП отличается от обычного такта. Такты ЦП учитываются только тогда, когда ЦП исполняет код в действии. Такты ЦП не учитываются, если поток, связанный с действием, находится в спящем режиме. Для *простых событий*это поле имеет значение 0. |
| `ExclusiveCPUTicks` | Это поле имеет то же значение, что и `CPUTicks`, за исключением того, что оно не включает такты ЦП, произошедшие в действиях дочерних элементов. Для *простых событий*это поле имеет значение 0. |
| `WallClockTimeResponsibilityTicks` | Если это событие является *действием*, для этого поля задается значение счетчика тактов, представляющее вклад этого действия в общее время стены. Тактовая частота на стене-часах отличается от обычной тактовой разницы. Такты ответственности за простенки времени принимают во внимание параллелизм между действиями. Например, два параллельных действия могут иметь длительность 50 тактов и одно и то же время начала и окончания. В этом случае для обоих будет назначено время, равное 25 тактам. Для *простых событий*это поле имеет значение 0. |
| `ExclusiveWallClockTimeResponsibilityTicks` | Это поле имеет то же значение, что и `WallClockTimeResponsibilityTicks`, за исключением того, что оно не включает в себя такты ответственности для дочерних действий. Для *простых событий*это поле имеет значение 0. |
| `Data` | Указывает на дополнительные данные, хранящиеся в событии. Тип данных, на который указывает, отличается в зависимости от поля `EventId`. |
| `ProcessId` | Идентификатор процесса, в котором произошло событие. |
| `ThreadId` | Идентификатор потока, в котором произошло событие. |
| `ProcessorIndex` | Нуль-индексируемый номер ЦП, на котором произошло событие. |
| `EventName` | Строка ANSI, содержащая имя сущности, определяемой `EventId`. |
| `EventWideName` | Широкая строка, содержащая имя сущности, определяемой `EventId`. |

## <a name="remarks"></a>Remarks

Многие поля в `EVENT_DATA` содержат счетчики тактов. C++В ходе сборки Insights в качестве источника тактов используется счетчик производительности окна. Чтобы преобразовать его в соответствующую единицу времени (например, в секундах), необходимо использовать счетчик тактов с полем `TickFrequency`. Для выполнения этого преобразования см. пример ниже. `EVENT_DATA` не содержит поля для регулярного счетчика тактов действия. Чтобы получить это значение, вычтите `StartTimestamp` из `StopTimestamp`. `EVENT_DATA` — это структура, которая предназначена для использования пользователями API C. Для C++ пользователей API такие классы, как преобразование времени [события](../cpp-event-data-types/event.md) , выполняются автоматически.

Значение поля `EVENT_DATA` `Data` зависит от значения поля `EventId`. Значение `Data` описывается в таблице ниже. Некоторые идентификаторы сущностей могут отсутствовать в таблице ниже. В этом случае поле `Data` имеет значение `nullptr` или равно нулю.

| Значение `EventId` | Тип, на который указывает `Data` |
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

## <a name="tick-conversion-example"></a>Пример преобразования тактов

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
