---
title: структура EVENT_COLLECTION_DATA
description: Ссылка на структуру СЗ «Сборка» sDK EVENT_COLLECTION_DATA структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88ba39ede8c86f47c2e6458332ae005eddc06fda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325691"
---
# <a name="event_collection_data-structure"></a>структура EVENT_COLLECTION_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `EVENT_COLLECTION_DATA` описывает массив [EVENT_DATA](event-data-struct.md) элементов.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `Count` | Количество элементов `EVENT_DATA` в массиве. |
| `Elements` | Указатель на `EVENT_DATA` первый элемент массива. |

::: moniker-end
