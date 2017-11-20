---
title: "Затраченное время: Классы автоматизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 51479f73112ed80ee981f3919fd3941d1eb0c8f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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

