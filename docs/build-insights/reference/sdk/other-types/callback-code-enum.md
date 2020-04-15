---
title: CALLBACK_CODE enum
description: SDK Build Insights sDK CALLBACK_CODE ссылку.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0d3dcc70040f562cd40755188e545f709a807b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329191"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE enum

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Enum `CALLBACK_CODE` используется контролировать поток анализа или сеанса перезаписи. Верните CALLBACK_CODE значение от функций в [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) или [RELOG_CALLBACKS,](relog-callbacks-struct.md) чтобы контролировать, что должно произойти дальше.

## <a name="members"></a>Участники

| name | Значение | Описание |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Продолжить текущий анализ или сеанс перезаписи в обычном режиме. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Отмените текущий анализ или сеанс перезаписи и отодвинете ошибку. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x000000004) | Отмените текущий анализ или сеанс перезаписи. |

::: moniker-end
