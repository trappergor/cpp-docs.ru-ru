---
title: Структура FUNCTION_FORCE_INLINEE_DATA
description: В C++ пакете SDK для аналитики сборки FUNCTION_FORCE_INLINEE_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3d6929f2f16e9b1bd79b7fb8b383b40e031268bf
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335150"
---
# <a name="function_force_inlinee_data-structure"></a>Структура FUNCTION_FORCE_INLINEE_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `FUNCTION_FORCE_INLINEE_DATA` описывает функцию, встроенную принудительно.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `Name` | Имя функции в кодировке UTF-8. |
| `Size` | Размер функции в виде количества промежуточных инструкций. |

::: moniker-end
