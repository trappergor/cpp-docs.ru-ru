---
title: "Создание и отображение диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d436301a979dbba2bc4a922f8427f355a398f654
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-displaying-dialog-boxes"></a>Создание и отображение диалоговых окон
Создание объекта диалогового окна — это двухфазная операция. Во-первых создайте объект диалогового окна, а затем создать диалоговое окно. Модальные и немодальные диалоговые окна несколько в процесс, используемый для создания и отображения их отличаться. В следующей таблице перечислены диалогового окна как модальные и немодальные поля обычно создается и отображаются.  
  
### <a name="dialog-creation"></a>Создание диалогового окна  
  
|Тип диалогового окна|Способ его создания|  
|-----------------|----------------------|  
|[Немодальный](../mfc/creating-modeless-dialog-boxes.md)|Создать `CDialog`, затем вызовите **создать** функции-члена.|  
|[Модальные](../mfc/creating-modal-dialog-boxes.md)|Создать `CDialog`, затем вызовите `DoModal` функции-члена.|  
  
 Если необходимо, создаются в диалоговое окно [шаблона диалогового окна в памяти](../mfc/using-a-dialog-template-in-memory.md) , сформированного, а не из ресурса шаблона диалогового окна. Однако это довольно сложная тема.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

