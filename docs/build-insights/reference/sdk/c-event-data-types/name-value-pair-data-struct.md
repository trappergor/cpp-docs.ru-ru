---
title: структура NAME_VALUE_PAIR_DATA
description: Ссылка на структуру СЗ «Сборка» sDK NAME_VALUE_PAIR_DATA структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4a0bf8e8ba32d94d30a56d0ef26ca4ed0c9b0711
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325360"
---
# <a name="name_value_pair_data-structure"></a>структура NAME_VALUE_PAIR_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `NAME_VALUE_PAIR_DATA` описывает пару имен и значений.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `Name` | Имя. |
| `Value` | Значение. |

::: moniker-end
