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
ms.openlocfilehash: 928728093ff6e2150578c4ba48f2d8081620a48d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931148"
---
# <a name="notifications-from-a-rich-edit-control"></a>Уведомления из элемента управления "Rich Edit"
Отчет, событиях, влияющих на форматированного элемента управления edit сообщения уведомления ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Они могут обрабатываться родительского окна или с помощью отражения сообщение в сложных изменения самого элемента управления. Элементы управления rich edit поддерживают все сообщения уведомления, элементы управления редактирования, а также некоторые дополнительные шаблоны. Можно определить, какие сообщения уведомления элемента управления rich edit отправляет родительского окна, установив его «маску события».  
  
 Чтобы настроить элемент управления rich edit маску события, используйте [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) функции-члена. Можно получить текущую маску события для редактирования форматированного текста элемента управления с помощью [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) функции-члена.  
  
 Ниже перечислены несколько конкретных уведомлений и их использование:  
  
-   EN_MSGFILTER обработка уведомления EN_MSGFILTER позволяет класса, либо, управления rich edit или родительского окна, отфильтровать все клавиатуры и мыши входных данных для элемента управления. Обработчик можно предотвратить обработку сообщений клавиатуры или мыши или можете изменить сообщение, изменив указанного [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) структуры.  
  
-   EN_PROTECTED обрабатывать сообщения уведомления EN_PROTECTED определить, когда пользователь пытается изменить защищенный текст. Чтобы пометить диапазон текста как защищенный, можно задать эффект защищенного символа. Дополнительные сведения см. в разделе [форматирование знаков в элементами управления Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   EN_DROPFILES позволяет пользователю удалять файлы в элементе управления rich edit, обрабатывая EN_DROPFILES сообщения уведомления. Указанный [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) структура содержит сведения о файлах в процессе удаления.  
  
-   EN_SELCHANGE приложения можно обнаружить, когда при обработке сообщения уведомления EN_SELCHANGE изменении текущего выделения. Указывает сообщение уведомления [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) структуру, содержащую сведения о новое выделение.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

