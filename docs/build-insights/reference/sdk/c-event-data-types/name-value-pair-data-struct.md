---
title: Структура NAME_VALUE_PAIR_DATA
description: В C++ пакете SDK для аналитики сборки NAME_VALUE_PAIR_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f6c4f6fef11e6365bdc930d5df1f48f72186ebdb
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335102"
---
# <a name="name_value_pair_data-structure"></a>Структура NAME_VALUE_PAIR_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `NAME_VALUE_PAIR_DATA` описывает пару "имя-значение".

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `Name` | Имя. |
| `Value` | Значение. |

::: moniker-end
