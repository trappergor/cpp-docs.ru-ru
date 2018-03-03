---
title: "Сопоставление сообщений Windows с классом | Документы Microsoft"
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
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4701b0ae9f71099febb1a239cea6285fb0a7b229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-windows-messages-to-your-class"></a>Сопоставление сообщений Windows с классом
Если вам требуется диалоговое для обработки сообщений Windows, заменяют функции, соответствующий обработчик. Чтобы сделать это, используйте окно свойств для [сопоставление сообщений](../mfc/reference/mapping-messages-to-functions.md) в класс диалоговых окон. Производит запись в схеме сообщений для каждого сообщения. при этом добавляет обработчик сообщений функции-члены класса. Используйте редактор исходного кода Visual C++ для написания кода в обработчике сообщений.  
  
 Можно также переопределить функции-члены [CDialog](../mfc/reference/cdialog-class.md) и его базовых классов, особенно [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)  
  
-   [Часто переопределяемые функции-члены](../mfc/commonly-overridden-member-functions.md)  
  
-   [Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

