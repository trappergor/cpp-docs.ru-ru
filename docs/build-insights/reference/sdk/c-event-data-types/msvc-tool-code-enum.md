---
title: Перечисление MSVC_TOOL_CODE
description: В C++ пакете SDK для аналитики сборки MSVC_TOOL_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MSVC_TOOL_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d88a2227808867b04ef3b0557aee9c869beaead1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335126"
---
# <a name="msvc_tool_code-enum"></a>Перечисление MSVC_TOOL_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `MSVC_TOOL_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `MSVC_TOOL_CODE_CL` | 0 (0x00000000) | Компилятор (Cl. exe). |
| `MSVC_TOOL_CODE_LINK` | 1 (0x00000001) | Компоновщик (Link. exe). |

## <a name="remarks"></a>Remarks

Используется в функциях пакета SDK C.

::: moniker-end
