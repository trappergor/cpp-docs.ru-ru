---
title: Структура FUNCTION_FORCE_INLINEE_DATA
description: Справочник по структуре FUNCTION_FORCE_INLINEE_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9de87bdc4e5a1a3e25483f8ba1766609c7d7622
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923567"
---
# <a name="function_force_inlinee_data-structure"></a>Структура FUNCTION_FORCE_INLINEE_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

В структуре `FUNCTION_FORCE_INLINEE_DATA` описывается принудительно встраиваемая функция.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `Name` | Имя функции в кодировке UTF-8. |
| `Size` | Размер функции, выраженный в числе инструкций промежуточного языка. |

::: moniker-end
