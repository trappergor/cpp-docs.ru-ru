---
title: АнализКонтроль enum класса
description: Ссылка на ссылку «СИ Тиз СборкА» SDK AnalysisControl перечисляет.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9431f878390127f2cefbe8f0ee42ca509e147de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323644"
---
# <a name="analysiscontrol-enum-class"></a>АнализКонтроль enum класса

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `AnalysisControl` enum используется, контролируя поток сеанса анализа или перезаписи. Верните `AnalysisControl` код из функции [iAnalyzer](ianalyzer-class.md) или [IRelogger,](irelogger-class.md) чтобы контролировать, что должно произойти дальше.

## <a name="members"></a>Участники

|  |  |
|--|--|
| `BLOCK` | Предотвращает дальнейшее распространение текущего события в группе анализатора или перелога. |
| `CANCEL` | Отмените текущий анализ или сеанс перезаписи. |
| `CONTINUE` | Продолжить текущий анализ или сеанс перезаписи в обычном режиме. Распространение текущего события следующему участнику группы анализатора или релоггеру. |
| `FAILURE` | Отмените текущий анализ или сеанс перезаписи и отодвинете ошибку. |

::: moniker-end
