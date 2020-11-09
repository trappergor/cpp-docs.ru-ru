---
title: InjectEvent
description: Справочник по функции InjectEvent пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4d85f17a6d553d9dffa727824e6d4de94518645
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922840"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `InjectEvent` вызывается средством перезаписи при реализации интерфейса [IRelogger](../other-types/irelogger-class.md). Она используется для записи события трассировки событий Windows (ETW) в выходном файле трассировки сеанса перезаписи.

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

*relogSession*\
Указатель на сеанс перезаписи. Сеанс перезаписи предоставляется средствам перезаписи, которые реализуют интерфейс `IRelogger`. Дополнительные сведения см. в разделе [IRelogger](../other-types/irelogger-class.md).

*providerId*\
GUID поставщика трассировки событий Windows (ETW), под которым событие ETW проходит перезапись.

*eventDescriptor*\
Дескриптор события трассировки событий Windows для события ETW, проходящего перезапись.

*processId*\
Идентификатор процесса события трассировки событий Windows, проходящего перезапись.

*threadId*\
Идентификатор потока (TID) для события трассировки событий Windows, которое проходит перезапись.

*processorIndex*\
Индекс процессора для события трассировки событий Windows, которое проходит перезапись.

*timestamp*\
Метка времени для события трассировки событий Windows, проходящего перезапись.

*data*\
Указатель на данные, которые должны быть включены в перезаписанное событие трассировки событий Windows.

*byteCount*\
Размер данных в байтах, на который указывает параметр *data*.

## <a name="remarks"></a>Комментарии

Дополнительные сведения об основных понятиях трассировки событий Windows, таких как *GUID поставщика* и *дескриптор события* , см. в [документации по трассировке событий Windows](/windows/win32/etw/about-event-tracing). Дополнительные сведения о том, как запустить сеанс перезаписи с помощью пакета SDK Аналитики сборки C++, см. в статье о функции [Relog](relog.md).

::: moniker-end
