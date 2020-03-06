---
title: Структура ANALYSIS_DESCRIPTOR
description: В C++ пакете SDK для аналитики сборки ANALYSIS_DESCRIPTOR ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fc11ce11e1faaae02edb36aac447c18ea8107e35
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334106"
---
# <a name="analysis_descriptor-structure"></a>Структура ANALYSIS_DESCRIPTOR

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_DESCRIPTOR` используется с функциями [Analyze](../functions/analyze-a.md) и [анализев](../functions/analyze-w.md) . В нем описывается анализ трассировки событий Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `NumberOfPasses` | Количество проходов анализа, которые следует выполнить по трассировке ETW. |
| `Callbacks` | Объект [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) , указывающий, какие функции следует вызывать во время сеанса анализа. |
| `Context` | Предоставленный пользователем контекст, передаваемый в качестве аргумента всем функциям обратного вызова, указанным в `Callbacks` |

## <a name="remarks"></a>Remarks

Структура `Callbacks` принимает указатели только на функции, не являющиеся членами. Это ограничение можно обойти, установив для `Context` указатель на объект. Этот указатель на объект будет передан как аргумент для всех функций обратного вызова, не являющихся членами. Этот указатель используется для вызова функций-членов из функций обратного вызова, не являющихся членами.

::: moniker-end
