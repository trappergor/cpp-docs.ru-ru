---
title: "Сообщения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d03eed129fd5a2a7c73f7c7948cb766813f63c34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="messages"></a>Сообщения
Цикл обработки сообщений в **запуска** функции-члена класса `CWinApp` извлекает в очередь сообщения, сформированные при различных событий. Например, когда пользователь нажимает кнопку мыши, Windows отправляет несколько сообщений, связанных с мышью, таких как `WM_LBUTTONDOWN` при нажатии левой кнопки мыши и `WM_LBUTTONUP` при отпускании левой кнопки мыши. Реализация framework цикл обработки сообщений приложения отправляет сообщение, соответствующее окно.  
  
 Описываются важные категории сообщений в [категории сообщений](../mfc/message-categories.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

