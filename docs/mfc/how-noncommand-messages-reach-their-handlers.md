---
title: "Доступ Некомандных сообщений к обработчикам | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33d0d65c9916cfc571ecfd623138938c0c883ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам
В отличие от команд стандартные сообщения Windows не будут направляться через цели цепочке управления, но обычно осуществляется с помощью окна, к которому Windows отправляет сообщение. Окно может быть фрейма главного окна, дочернего окна MDI, стандартный элемент управления, диалоговое окно, представление или другой вид дочернего окна.  
  
 Во время выполнения каждого окна Windows присоединяется к объекту window (прямо или косвенно производными `CWnd`), имеет свои собственные функции карты и обработчик соответствующее сообщение. Платформа использует схему сообщений, и для команды — для сопоставления входящих сообщений к обработчикам.  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

