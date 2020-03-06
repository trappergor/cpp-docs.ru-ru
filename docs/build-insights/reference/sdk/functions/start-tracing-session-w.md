---
title: старттраЦингсессионв
description: Справочник C++ по функциям SDK для Build Insights старттраЦингсессионв.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 072b02166f2841e6d210306ef75c9fc64fea9778
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334250"
---
# <a name="starttracingsessionw"></a>старттраЦингсессионв

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StartTracingSessionW` запускает сеанс трассировки. Исполняемые файлы, вызывающие эту функцию, должны иметь права администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Имя запускаемого сеанса трассировки. Используйте то же имя при вызове [стоптраЦингсессионв](stop-tracing-session-w.md)или любой другой функции трассировки.

\ *параметров*
Указатель на объект [TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) . Этот объект используется для выбора событий, собираемых сеансом трассировки.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
