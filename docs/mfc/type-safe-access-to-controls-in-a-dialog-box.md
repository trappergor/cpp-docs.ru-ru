---
title: "Типобезопасный доступ к элементам управления в диалоговом окне | Документы Microsoft"
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
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6005f34b28a634b36aad93186a34a8806b8033d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Типобезопасный доступ к элементам управления в диалоговом окне
Элементы в диалоговом окне могут использовать интерфейсы классов элементов управления MFC, таких как `CListBox` и `CEdit`. Можно создать объект элемента управления и присоединить его к элементу управления диалогового окна. После этого можно обращаться к элементу управления через интерфейс его класса, вызывая функции-члены для выполнения операций над элементом управления. Описанные здесь методы предназначены для того, чтобы обеспечить типобезопасный доступ к элементу управления. Это особенно полезно в случае таких элементов управления, как поля ввода и списки.  
  
 Существует два подхода к созданию соединения между элементом управления в диалоговом окне и переменной-членом элемента управления C++ в классе, производном от `CDialog`:  
  
-   [Без помощи мастеров кода](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [С помощью мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)

