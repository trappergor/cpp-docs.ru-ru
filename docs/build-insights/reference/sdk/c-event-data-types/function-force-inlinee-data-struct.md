---
title: структура FUNCTION_FORCE_INLINEE_DATA
description: Ссылка на структуру SDK Build Insights SDK FUNCTION_FORCE_INLINEE_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a4781c9157130cb46e92906017af98710f5637b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325492"
---
# <a name="function_force_inlinee_data-structure"></a>структура FUNCTION_FORCE_INLINEE_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `FUNCTION_FORCE_INLINEE_DATA` описывает функцию, подстеженную силой.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `Name` | Название функции, закодированное в UTF-8. |
| `Size` | Размер функции, как ряд промежуточных инструкций. |

::: moniker-end
