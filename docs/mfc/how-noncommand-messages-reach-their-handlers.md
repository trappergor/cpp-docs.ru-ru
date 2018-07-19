---
title: Доступ Некомандных сообщений к обработчикам | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3999c74bf7a612acb998e7a044c12948d7679d9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343886"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам
В отличие от команд стандартные сообщения Windows не будут направляться через цели цепочке управления, но обычно осуществляется с помощью окна, к которому Windows отправляет сообщение. Окно может быть фрейма главного окна, дочернего окна MDI, стандартный элемент управления, диалоговое окно, представление или другой вид дочернего окна.  
  
 Во время выполнения каждого окна Windows присоединяется к объекту window (прямо или косвенно производными `CWnd`), имеет свои собственные функции карты и обработчик соответствующее сообщение. Платформа использует схему сообщений, и для команды — для сопоставления входящих сообщений к обработчикам.  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

