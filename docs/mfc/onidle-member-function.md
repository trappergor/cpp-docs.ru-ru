---
title: Функция-член OnIdle | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbe912db448e424f18b6d72f6e148312c5940687
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="onidle-member-function"></a>Функция-член OnIdle
При обработке сообщения не Windows платформа вызывает [CWinApp](../mfc/reference/cwinapp-class.md) функции-члена [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (описаны в справочнике по библиотеке MFC).  
  
 Переопределить `OnIdle` для выполнения фоновых задач. Версия по умолчанию обновляет состояние объектов пользовательского интерфейса, таких как кнопки панели инструментов и выполняет очистку временные объекты, создаваемые средой во время операции. На следующем рисунке показано, как цикл обработки сообщений вызывает `OnIdle` при нет сообщений в очереди.  
  
 ![Процесс цикла сообщений](../mfc/media/vc387c1.gif "vc387c1")  
Цикл обработки сообщений  
  
 Дополнительные сведения о том, что можно сделать на цикла простоя см. в разделе [обработку цикла простоя](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
