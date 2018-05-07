---
title: 'Затраченное время: Классы автоматизации | Документы Microsoft'
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
ms.openlocfilehash: c1abf6274137ae67b159ad43612d24020a0d14e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="elapsed-time-automation-classes"></a>Затраченное время: Классы автоматизации
Эта процедура показано, как вычислить разницу между двумя `CTime` объектов и get `CTimeSpan` результат.  
  
#### <a name="to-calculate-elapsed-time"></a>Для вычисления истекшего времени  
  
1.  Создайте два `COleDateTime` объектов.  
  
2.  Задайте одно из `COleDateTime` объектов на текущий момент времени.  
  
3.  Выполнение некоторых трудоемкой задачей.  
  
4.  Задать другие `COleDateTime` объекта на текущий момент времени.  
  
5.  Найти разность между двумя значениями времени.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Дата и время. Поддержка автоматизации](../atl-mfc-shared/date-and-time-automation-support.md)

