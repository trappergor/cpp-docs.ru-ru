---
title: "Функция-член OnIdle | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfbc0a1f20cb6cc01143ed6f07a63e84b53be6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="onidle-member-function"></a>Функция-член OnIdle
При обработке сообщения не Windows платформа вызывает [CWinApp](../mfc/reference/cwinapp-class.md) функции-члена [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (описаны в справочнике по библиотеке MFC).  
  
 Переопределить `OnIdle` для выполнения фоновых задач. Версия по умолчанию обновляет состояние объектов пользовательского интерфейса, таких как кнопки панели инструментов и выполняет очистку временные объекты, создаваемые средой во время операции. На следующем рисунке показано, как цикл обработки сообщений вызывает `OnIdle` при нет сообщений в очереди.  
  
 ![Процесс цикла сообщений](../mfc/media/vc387c1.gif "vc387c1")  
Цикл обработки сообщений  
  
 Дополнительные сведения о том, что можно сделать на цикла простоя см. в разделе [обработку цикла простоя](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
