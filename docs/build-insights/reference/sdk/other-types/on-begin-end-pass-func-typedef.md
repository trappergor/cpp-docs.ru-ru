---
title: Определение типа Онбегинендпассфунк
description: Справочник C++ по ОНБЕГИНЕНДПАССФУНК typedef SDK для Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6f5e602fdc460acf8e53307e88a1a3d7ad000893
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334058"
---
# <a name="onbeginendpassfunc-typedef"></a>Определение типа Онбегинендпассфунк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

`OnBeginEndPassFunc` typedef — одна из сигнатур функций, используемых в структурах [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) и [RELOG_CALLBACKS](relog-callbacks-struct.md) .

## <a name="syntax"></a>Синтаксис

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `callbackContext` |  |

::: moniker-end
