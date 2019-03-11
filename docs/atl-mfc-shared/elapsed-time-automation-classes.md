---
title: 'Затраченное время: Классы автоматизации'
ms.date: 11/04/2016
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
ms.openlocfilehash: d6a77d57a88166354fcb222c0da09690426108e9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750053"
---
# <a name="elapsed-time-automation-classes"></a>Затраченное время: Классы автоматизации

Эта процедура демонстрирует для вычисления разницы между двумя `CTime` объектов и получите `CTimeSpan` результат.

## <a name="to-calculate-elapsed-time"></a>Для вычисления истекшего времени

1. Создайте две `COleDateTime` объектов.

1. Задать один из `COleDateTime` объектов на текущий момент времени.

1. Для выполнения некоторых много времени задачи.

1. Задать другие `COleDateTime` объекта на текущий момент времени.

1. Использовать разницу между двумя значениями времени.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>См. также

[Дата и время: Поддержка модели автоматизации](../atl-mfc-shared/date-and-time-automation-support.md)
