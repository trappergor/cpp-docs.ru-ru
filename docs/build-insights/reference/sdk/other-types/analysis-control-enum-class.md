---
title: Класс перечисления AnalysisControl
description: Справочник по перечислению AnalysisControl из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a7b7fc0ce404f414b3ec07449bdc110d578fa101
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042021"
---
# <a name="analysiscontrol-enum-class"></a>Класс перечисления AnalysisControl

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс перечисления `AnalysisControl` используется для управления потоком сеанса анализа или повторной записи в журнал. Он возвращает код `AnalysisControl` из функции-члена [IAnalyzer](ianalyzer-class.md) или [IRelogger](irelogger-class.md) для управления дальнейшими действиями.

## <a name="members"></a>Члены

| Имя | Описание |
|--|--|
| `BLOCK` | Запрещает распространение текущего события в анализаторе или группе повторной записи. |
| `CANCEL` | Отменяет текущий сеанс анализа или повторной записи в журнал. |
| `CONTINUE` | Продолжает выполнение текущего сеанса анализа или повторной записи в журнал в обычном режиме. Распространяет текущее событие в следующий анализатор или элемент группы повторной записи в журнал. |
| `FAILURE` | Отменяет текущий сеанс анализа или повторной записи в журнал и сигнал об ошибке. |

::: moniker-end
