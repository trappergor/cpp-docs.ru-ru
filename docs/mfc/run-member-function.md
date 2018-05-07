---
title: Выполнение функции-члена | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be1d7d90b4c13a23e2e3456e7371abbae61be4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="run-member-function"></a>Выполнение функции-члена
Приложение framework тратит больше всего времени в [запуска](../mfc/reference/cwinapp-class.md#run) функции-члена класса [CWinApp](../mfc/reference/cwinapp-class.md). После инициализации `WinMain` вызовы **запуска** для обработки в цикл обработки сообщений.  
  
 **Запустите** циклический перебор цикл обработки сообщений, проверка доступных сообщений очереди сообщений. Если сообщение не станет доступным, **запуска** пересылает его для действия. Часто задано значение true, если доступных сообщений нет, который **запуска** вызовы `OnIdle` любой времени простоя обработку вы или framework может потребоваться сделать. Если ни одного сообщения и обработка без простоя для выполнения, приложение ожидает, пока происходит событие. Когда приложение завершает работу, **запуска** вызовов `ExitInstance`. Рисунок в [функция-член OnIdle](../mfc/onidle-member-function.md) показана последовательность действий в цикле обработки сообщений.  
  
 Диспетчеризация сообщений зависит от типа сообщения. Дополнительные сведения см. в разделе [сообщения и команды в Framework](../mfc/messages-and-commands-in-the-framework.md).  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
