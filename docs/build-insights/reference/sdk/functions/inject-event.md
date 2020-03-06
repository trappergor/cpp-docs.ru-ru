---
title: инжектевент
description: Справочник C++ по функциям SDK для Build Insights инжектевент.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7b53eb71cf7a2ae40d04dbc3f8b5829f2737aba4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334418"
---
# <a name="injectevent"></a>инжектевент

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `InjectEvent` вызывается в средстве ведения журнала, реализующем интерфейс [ирелогжер](../other-types/irelogger-class.md) . Он используется для записи события трассировки событий Windows (ETW) в выходном файле трассировки сеанса повторного ведения журнала.

## <a name="syntax"></a>Синтаксис

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>Параметры

*релогсессион*\
Указатель на сеанс перезаписи. Для средств ведения журнала, реализующих интерфейс `IRelogger`, предоставляется сеанс повторного ведения журнала. Дополнительные сведения см. в разделе [ирелогжер](../other-types/irelogger-class.md).

*providerId*\
Идентификатор GUID поставщика трассировки событий для Windows (ETW), в котором регистрируется событие ETW.

*eventDescriptor*\
Дескриптор события ETW для события ETW, регистрируемого в журнале.

Идентификатор *процесса*\
Идентификатор процесса (PID) для события ETW, которое регистрируется повторно.

*threadId*\
Идентификатор потока (TID) для события трассировки событий Windows, которое регистрируется снова.

*процессориндекс*\
Индекс процессора для события трассировки событий Windows, которое регистрируется повторно.

*отметка времени*\
Метка времени для события ETW, регистрируемого в журнале.

\ *данных*
Указатель на данные, которые должны быть добавлены в событие трассировки событий Windows, зарегистрированное в журнале событий.

\ *byteCount*
Размер данных в байтах, на которые указывают *данные*.

## <a name="remarks"></a>Remarks

Дополнительные сведения о концепциях ETW, таких как *идентификатор GUID поставщика* и *дескриптор события*, см. в [документации по ETW](/windows/win32/etw/about-event-tracing). Дополнительные сведения о том, как запустить сеанс повторного ведения журнала C++ с помощью пакета SDK для аналитики сборки, см. в разделе [Relog](relog.md).

::: moniker-end
