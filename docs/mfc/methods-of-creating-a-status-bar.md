---
title: "Способы создания строки состояния | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce14870db466727f93daea15b60c99d975783e87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-a-status-bar"></a>Способы создания строки состояния
MFC предоставляет две классы для создания строки состояния: [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (который создает оболочку для стандартного элемента управления Windows API). `CStatusBar`предоставляет все функциональные возможности, строки состояния, стандартного элемента управления, он автоматически взаимодействует с меню и панелей инструментов и обрабатывает многие необходимые общие параметры управления и структуры. Однако полученный исполняемый файл обычно будет больше, созданные с помощью `CStatusBarCtrl`.  
  
 `CStatusBarCtrl`обычно приводит к исполняемый объект меньшего размера и может потребоваться `CStatusBarCtrl` Если вы не собираетесь интегрировать в архитектуру MFC в строке состояния. Если вы планируете использовать `CStatusBarCtrl` и интегрировать в строке состояния в MFC архитектуру, должны быть дополнительные меры предосторожности, состоянии панели управления манипуляций с MFC. Эта связь не является сложным; Однако это дополнительную работу, которая ненужные при использовании `CStatusBar`.  
  
 Visual C++ предоставляет два способа, чтобы воспользоваться преимуществами общие строки состояния.  
  
-   Создание строки с помощью состояния `CStatusBar`, а затем вызвать [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) получить доступ к `CStatusBarCtrl` функции-члены.  
  
-   Создание строки с помощью состояния [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)в конструктор.  
  
 Оба этих метода позволит получить доступ к функциям-членам строки состояния. При вызове `CStatusBar::GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` таким образом можно использовать любой набор функций-членов. В разделе [CStatusBar](../mfc/reference/cstatusbar-class.md) сведения о построении и создания индикатора с помощью `CStatusBar`.  
  
## <a name="see-also"></a>См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

