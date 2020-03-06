---
title: Структура TRACE_INFO_DATA
description: В C++ пакете SDK для аналитики сборки TRACE_INFO_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 04cb5c013bca8879507983d169b38e5af0f1322b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335054"
---
# <a name="trace_info_data-structure"></a>Структура TRACE_INFO_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACE_INFO_DATA` описывает анализируемую или регистрируемую трассировку.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `LogicalProcessorCount` | Число логических процессоров на компьютере, на котором была собрана трассировка. |
| `TickFrequency` | Число тактов в секунду, используемое при вычислении длительности, измеряемой в тактах. |
| `StartTimestamp` | Для этого поля задается значение Tick, заданное во время запуска трассировки. |
| `StopTimestamp` | Для этого поля задается значение Tick, заданное во время остановки трассировки. |

## <a name="remarks"></a>Remarks

Вычтите `StartTimestamp` из `StopTimestamp`, чтобы получить число тактов, прошедших во время всей трассировки. Используйте `TickFrequency`, чтобы преобразовать полученное значение в единицу времени. Пример преобразования тактов в единицы времени см. в разделе [EVENT_DATA](event-data-struct.md).

::: moniker-end
