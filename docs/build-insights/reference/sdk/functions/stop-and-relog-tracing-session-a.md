---
title: СтопАндрелогТрейсингСея
description: Ссылка на функцию «СИ Тиз» построить исследования SDK StopAndRelogRacingSessionA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fa70d50ba79a7829adb985ab4d884b5773b5d40f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323671"
---
# <a name="stopandrelogtracingsessiona"></a>СтопАндрелогТрейсингСея

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndRelogTracingSessionA` останавливает текущий сеанс отслеживания и сохраняет полученный след во временном файле. Затем сеанс перезаписи немедленно начинает использовать временный файл в качестве ввода. Окончательный перезаписированный след, производимый сеансом перезаписи, сохраняется в файле, указанном абонентом. Исполнители вызова этой функции должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE StopAndRelogTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Название сеанса отслеживания, чтобы остановить. Используйте то же имя сеанса, что и имя, которое было передано [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)или [StartTracingSessionW.](start-tracing-session-w.md)

*выходНопок*\
Файл, в котором можно написать перезаписированный след, созданный сеансом перезаписи.

*Статистика*\
Указатель на [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) объект. `StopAndRelogTracingSessionA`записывает статистику сбора следов на этом объекте перед возвращением.

*анализДескриптор*\
Указатель на [RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) объект. Используйте этот объект для настройки сеанса `StopAndRelogTracingSessionA`перезаписи, который начался с.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
