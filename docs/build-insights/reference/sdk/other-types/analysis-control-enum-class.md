---
title: Класс перечисления Аналисисконтрол
description: Ссылка C++ на перечисление АНАЛИСИСКОНТРОЛ пакета SDK для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf162c11e0a7109b8d733dab79df80782398e14d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334124"
---
# <a name="analysiscontrol-enum-class"></a>Класс перечисления Аналисисконтрол

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс перечисления `AnalysisControl` используется для управления потоком анализа или сеанса повторного ведения журнала. Возвращает `AnalysisControl` код из функции члена [ианализер](ianalyzer-class.md) или [ирелогжер](irelogger-class.md) , чтобы контролировать, что должно происходить далее.

## <a name="members"></a>Члены

|  |  |
|--|--|
| `BLOCK` | Предотвращает дальнейшее распространение текущего события в анализаторе или группе повторного ведения журнала. |
| `CANCEL` | Отмена текущего сеанса анализа или перезаписи в журнал. |
| `CONTINUE` | Продолжить текущий анализ или сеанс повторного ведения журнала в обычном режиме. Распространить текущее событие в следующий анализатор или член группы повторного ведения журнала. |
| `FAILURE` | Отменить текущий сеанс анализа или перезаписи и сообщить об ошибке. |

::: moniker-end
