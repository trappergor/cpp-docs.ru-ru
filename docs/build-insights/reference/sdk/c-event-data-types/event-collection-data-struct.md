---
title: Структура EVENT_COLLECTION_DATA
description: Справочник по структуре EVENT_COLLECTION_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 58be46d31af154bfe7ecef5c440092eaafdcbb0f
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039603"
---
# <a name="event_collection_data-structure"></a>Структура EVENT_COLLECTION_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В структуре `EVENT_COLLECTION_DATA` описывается массив элементов [EVENT_DATA](event-data-struct.md).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `Count` | Количество элементов `EVENT_DATA` в массиве. |
| `Elements` | Указатель на первый элемент `EVENT_DATA` массива. |

::: moniker-end
