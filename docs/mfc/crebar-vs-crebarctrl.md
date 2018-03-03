---
title: "CReBar vs. CReBarCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68cd21e21c14a34122f1b26345fab767728ac6a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crebar-vs-crebarctrl"></a>CReBar vs. CReBarCtrl
MFC предоставляет два класса, чтобы создать rebars: [CReBar](../mfc/reference/crebar-class.md) и [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (который создает оболочку для стандартного элемента управления Windows API). **CReBar** предоставляет все функциональные возможности стандартного элемента главной панели управления и обрабатывает многие необходимые общие параметры управления и структуры для вас.  
  
 `CReBarCtrl`класс-оболочку для элемента управления главной панели Win32 и таким образом, может быть проще реализовать, если вы не собираетесь интегрировать в архитектуру MFC главной панели. Если вы планируете использовать `CReBarCtrl` и интегрировать в архитектуру MFC главной панели, вы должны быть дополнительные меры предосторожности для взаимодействия главной панели управления манипуляций с MFC. Эта связь не является сложным; Однако это дополнительную работу, которая ненужные при использовании **CReBar**.  
  
 Visual C++ предоставляет два способа использовать преимущества стандартного элемента управления главной панели.  
  
-   Создать на главной панели с помощью **CReBar**, а затем вызвать [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) получить доступ к `CReBarCtrl` функции-члены.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl`— Это встроенная функция члена, приведение **это** указатель объекта главной панели. Это означает, что во время выполнения вызова функции отсутствие дополнительных расходов на.  
  
-   Создать на главной панели с помощью [CReBarCtrl](../mfc/reference/crebarctrl-class.md)в конструктор.  
  
 В обоих случаях будет получить доступ к функции-члены элемента управления главной панели. При вызове `CReBar::GetReBarCtrl`, он возвращает ссылку на `CReBarCtrl` таким образом можно использовать любой набор функций-членов. В разделе [CReBar](../mfc/reference/crebar-class.md) сведения о построении и создании главной панели с помощью **CReBar**.  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

