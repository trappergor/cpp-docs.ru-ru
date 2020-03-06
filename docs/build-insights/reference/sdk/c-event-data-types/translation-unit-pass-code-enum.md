---
title: Перечисление TRANSLATION_UNIT_PASS_CODE
description: В C++ пакете SDK для аналитики сборки TRANSLATION_UNIT_PASS_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1219eed98fd01e8c91d8750977e2d8ca4498d649
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335048"
---
# <a name="translation_unit_pass_code-enum"></a>Перечисление TRANSLATION_UNIT_PASS_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `TRANSLATION_UNIT_PASS_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | Интерфейсный этап, отвечающий за анализ исходного кода и его преобразование в промежуточный язык. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | Серверный этап, отвечающий за оптимизацию промежуточного языка и его преобразование в машинный код. |

## <a name="remarks"></a>Remarks

Используется в функциях пакета SDK C.

::: moniker-end
