---
title: Добавление элементов управления вручную | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efe510c4376255c24470a799b5dde17021894bf0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342479"
---
# <a name="adding-controls-by-hand"></a>Добавление элементов управления вручную
Вы можете либо [Добавление элементов управления в диалоговое окно редактора](../mfc/using-the-dialog-editor-to-add-controls.md) или добавить их вручную, с помощью кода.  
  
 Самостоятельно создать объект элемента управления обычно будет внедрять C++ элемент управления в диалоговом окне C++ или фреймового окна объекта. Как и многие другие объекты в структуре элементы управления требуют двух этапов построения. Необходимо вызвать элемент управления **создать** функции-члена в ходе создания родительского диалогового окна рамки окна. Для диалоговых окон, обычно это делается [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)и для окна фрейма в [OnCreate](../mfc/reference/cwnd-class.md#oncreate).  
  
 В следующем примере показано, как можно объявить `CEdit` объекта в объявлении класса диалоговое окно производного класса, а затем вызвать **создать** функции-члена `OnInitDialog`. Поскольку `CEdit` объект объявлен как внедренный объект, он автоматически создается, когда создается объект диалогового окна, но по-прежнему должны инициализироваться с собственным **создать** функции-члена.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]  
  
 Следующие `OnInitDialog` функция задает прямоугольник, затем вызывает метод **создать** Создание управления редактированием Windows и присоединить ее к неинициализированным `CEdit` объекта.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]  
  
 После создания объекта редактирования, элемент управления можно задать фокус ввода, вызвав `SetFocus` функции-члена. Наконец, возвращается 0 из `OnInitDialog` для отображения Установка фокуса. Если возвращается ненулевое значение, диалоговое окно диспетчера устанавливает фокус на первый элемент управления в списке элементов диалогового окна. В большинстве случаев может потребоваться добавление элементов управления в диалоговые окна с помощью редактора диалоговых окон.  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)

