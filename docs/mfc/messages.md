---
title: Сообщения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abd49410f9982788e9403f0cb83ca8656473417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344108"
---
# <a name="messages"></a>Сообщения
Цикл обработки сообщений в **запуска** функции-члена класса `CWinApp` извлекает в очередь сообщения, сформированные при различных событий. Например, когда пользователь нажимает кнопку мыши, Windows отправляет несколько сообщений, связанных с мышью, таких как `WM_LBUTTONDOWN` при нажатии левой кнопки мыши и `WM_LBUTTONUP` при отпускании левой кнопки мыши. Реализация framework цикл обработки сообщений приложения отправляет сообщение, соответствующее окно.  
  
 Описываются важные категории сообщений в [категории сообщений](../mfc/message-categories.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

