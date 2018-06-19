---
title: Уведомления из Rich Edit управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c678af3444ef408a0a9c50e972942d67e2d3cf1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353857"
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

