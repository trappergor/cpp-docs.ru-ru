---
title: Перечисление CALLBACK_CODE
description: Справочник по перечислению CALLBACK_CODE из пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146d191d0b642ad538f5a314016b41fdbdf26113
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922601"
---
# <a name="callback_code-enum"></a>Перечисление CALLBACK_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `CALLBACK_CODE` используется для управления потоком сеанса анализа или повторной записи в журнал. Выполните возврат значения CALLBACK_CODE из функций в [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) или [RELOG_CALLBACKS](relog-callbacks-struct.md), чтобы управлять следующими действиями.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Продолжает выполнение текущего сеанса анализа или повторной записи в журнал в обычном режиме. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Отменяет текущий сеанс анализа или повторной записи в журнал и сигнал об ошибке. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Отменяет текущий сеанс анализа или повторной записи в журнал. |

::: moniker-end
