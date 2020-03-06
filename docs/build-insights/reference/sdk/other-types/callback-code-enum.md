---
title: Перечисление CALLBACK_CODE
description: В C++ пакете SDK для аналитики сборки CALLBACK_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 68eaa9aa04d2f0a55ac12fb7dde14a080188a38d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334094"
---
# <a name="callback_code-enum"></a>Перечисление CALLBACK_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `CALLBACK_CODE` используется для управления потоком анализа или сеанса повторного ведения журнала. Возвращает CALLBACK_CODE значение из функций в [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) или [RELOG_CALLBACKS](relog-callbacks-struct.md) , чтобы контролировать, что должно происходить далее.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Продолжить текущий анализ или сеанс повторного ведения журнала в обычном режиме. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Отменить текущий сеанс анализа или перезаписи и сообщить об ошибке. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Отмена текущего сеанса анализа или перезаписи в журнал. |

::: moniker-end
