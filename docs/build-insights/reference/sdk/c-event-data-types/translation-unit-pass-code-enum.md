---
title: Перечисление TRANSLATION_UNIT_PASS_CODE
description: Справочник по перечислению TRANSLATION_UNIT_PASS_CODE пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 31f3e16ce6d9aa8c3c9db6cf9c11069dc3ec22fe
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920922"
---
# <a name="translation_unit_pass_code-enum"></a>Перечисление TRANSLATION_UNIT_PASS_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `TRANSLATION_UNIT_PASS_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x00000000) | Этап внешнего интерфейса включает анализ исходного кода и его преобразование в промежуточный язык. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | Этап внутреннего интерфейса включает оптимизацию промежуточного языка и его преобразование в машинный код. |

## <a name="remarks"></a>Комментарии

Используется в функциях пакета SDK для C.

::: moniker-end
