---
title: Структура EVENT_COLLECTION_DATA
description: В C++ пакете SDK для аналитики сборки EVENT_COLLECTION_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a622a8459b6aa6d9dcbe0faaf90ae545b449466
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335246"
---
# <a name="event_collection_data-structure"></a>Структура EVENT_COLLECTION_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `EVENT_COLLECTION_DATA` описывает массив элементов [EVENT_DATA](event-data-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `Count` | Число элементов `EVENT_DATA` в массиве. |
| `Elements` | Указатель на первый элемент `EVENT_DATA` в массиве. |

::: moniker-end
