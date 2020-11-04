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
ms.openlocfilehash: 17daaa6feb784c501d180a982cd4ad2b405ccf67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921091"
---
# <a name="event_collection_data-structure"></a>Структура EVENT_COLLECTION_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

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
