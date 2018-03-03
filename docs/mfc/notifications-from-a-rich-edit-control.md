---
title: "Уведомления из Rich Edit управления | Документы Microsoft"
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
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>Уведомления из элемента управления "Rich Edit"
Отчет, событиях, влияющих на форматированного элемента управления edit сообщения уведомления ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Они могут обрабатываться родительского окна или с помощью отражения сообщение в сложных изменения самого элемента управления. Элементы управления rich edit поддерживают все сообщения уведомления, элементы управления редактирования, а также некоторые дополнительные шаблоны. Можно определить, какие сообщения уведомления элемента управления rich edit отправляет родительского окна, установив его «маску события».  
  
 Чтобы настроить элемент управления rich edit маску события, используйте [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) функции-члена. Можно получить текущую маску события для редактирования форматированного текста элемента управления с помощью [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) функции-члена.  
  
 Ниже перечислены несколько конкретных уведомлений и их использование:  
  
-   **EN_MSGFILTER** обработки **EN_MSGFILTER** уведомлений позволяет класса, либо широкий набор функций редактирования элемента управления или родительского окна, отфильтровать все сочетания и входных данных для элемента управления с помощью мыши. Обработчик можно предотвратить обработку сообщений клавиатуры или мыши или можете изменить сообщение, изменив указанного [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) структуры.  
  
-   **EN_PROTECTED** обработки **EN_PROTECTED** сообщение уведомления, чтобы определить, когда пользователь пытается изменить защищенный текст. Чтобы пометить диапазон текста как защищенный, можно задать эффект защищенного символа. Дополнительные сведения см. в разделе [форматирование знаков в элементами управления Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN_DROPFILES** можно разрешить пользователю удалять файлы в элементе управления rich edit, обрабатывая **EN_DROPFILES** сообщение уведомления. Указанный [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) структура содержит сведения о файлах в процессе удаления.  
  
-   **EN_SELCHANGE** приложение может обнаружить при изменении текущего выделения, обрабатывая **EN_SELCHANGE** сообщение уведомления. Указывает сообщение уведомления [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) структуру, содержащую сведения о новое выделение.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

