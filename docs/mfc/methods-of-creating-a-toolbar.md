---
title: "Способы создания панели инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d93f8e43c933e9c8054e798c11754cc48bf54a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-a-toolbar"></a>Способы создания панели инструментов
MFC предоставляет две классы для создания панелей инструментов: [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (который создает оболочку для стандартного элемента управления Windows API). `CToolBar`предоставляет все функциональные возможности стандартного элемента панели инструментов управления и обрабатывает многие необходимые общие параметры управления и структуры. Однако полученный исполняемый файл обычно будет больше, созданные с помощью `CToolBarCtrl`.  
  
 `CToolBarCtrl`обычно приводит к исполняемый объект меньшего размера и может потребоваться `CToolBarCtrl` Если вы не собираетесь интегрировать в архитектуру MFC панели инструментов. Если вы планируете использовать `CToolBarCtrl` и интегрировать в архитектуру MFC панели инструментов, вы должны быть дополнительные меры предосторожности для взаимодействия инструментов управления манипуляций с MFC. Эта связь не является сложным; Однако это дополнительную работу, которая ненужные при использовании `CToolBar`.  
  
 Visual C++ предоставляет два способа использовать преимущества стандартного элемента управления панели инструментов.  
  
-   Создается при помощи инструментов `CToolBar`, а затем вызвать [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) получить доступ к `CToolBarCtrl` функции-члены.  
  
-   Создайте панель инструментов с помощью [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)в конструктор.  
  
 В обоих случаях будет получить доступ к функции-члены элемента управления панели инструментов. При вызове `CToolBar::GetToolBarCtrl`, он возвращает ссылку на `CToolBarCtrl` таким образом можно использовать любой набор функций-членов. В разделе [CToolBar](../mfc/reference/ctoolbar-class.md) сведения о построении и создание с помощью инструментов `CToolBar`.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

