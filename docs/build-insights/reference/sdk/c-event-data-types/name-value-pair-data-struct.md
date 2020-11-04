---
title: Структура NAME_VALUE_PAIR_DATA
description: Справочник по структуре NAME_VALUE_PAIR_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bab9f7ccedc4a94478d50863f2fae248722468e2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923545"
---
# <a name="name_value_pair_data-structure"></a>Структура NAME_VALUE_PAIR_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

В структуре `NAME_VALUE_PAIR_DATA` описывается пара "Имя — значение".

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `Name` | Имя. |
| `Value` | Значение. |

::: moniker-end
