---
title: 'Затраченное время: Классы автоматизации | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dcde08e8ffdb30f9ebf0ae7577bf836e84513a07
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751681"
---
# <a name="elapsed-time-automation-classes"></a>Затраченное время: Классы автоматизации

Эта процедура демонстрирует для вычисления разницы между двумя `CTime` объектов и получите `CTimeSpan` результат.

#### <a name="to-calculate-elapsed-time"></a>Для вычисления истекшего времени

1. Создайте две `COleDateTime` объектов.

2. Задать один из `COleDateTime` объектов на текущий момент времени.

3. Для выполнения некоторых много времени задачи.

4. Задать другие `COleDateTime` объекта на текущий момент времени.

5. Использовать разницу между двумя значениями времени.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>См. также

[Дата и время. Поддержка автоматизации](../atl-mfc-shared/date-and-time-automation-support.md)

