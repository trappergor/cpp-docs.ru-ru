---
title: Уведомления из форматированного текста элемента управления Edit | Документация Майкрософт
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
ms.openlocfilehash: a64abf4312460384ddfa78fa2220cfb88bf664c7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195075"
---
# <a name="notifications-from-a-rich-edit-control"></a>Уведомления из элемента управления "Rich Edit"
Уведомление сообщений отчета, события, затрагивающие форматированного текста элемента управления edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Они могут обрабатываться родительским окном или с помощью отражения сообщение в широкий набор функций изменения самого элемента управления. Элементы управления rich edit поддерживают все сообщения уведомления, элементы управления редактирования, а также несколько дополнительных обозревателей. Можно определить, какие сообщения уведомления элементе управления rich edit отправляет своему родительскому окну, задав его «маска событий».  
  
 Чтобы задать маску события для элемента управления редактирования форматированного текста, используйте [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) функция-член. Вы можете получить текущую маску события для элемента управления редактирования форматированного текста с помощью [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) функция-член.  
  
 Ниже перечислены несколько специальных уведомлений и методах их использования:  
  
-   EN_MSGFILTER обработка уведомлений EN_MSGFILTER позволяет классу, либо, управления форматированным редактированием или его родительского окна, фильтровать все клавиатура и мышь к элементу управления. Обработчик можно предотвратить обработку сообщений клавиатуры или мыши, или можно изменить сообщение, изменив указанного [MSGFILTER](/windows/desktop/api/richedit/ns-richedit-_msgfilter) структуры.  
  
-   EN_PROTECTED обрабатывать сообщения уведомления EN_PROTECTED, чтобы определить, когда пользователь пытается изменить защищенный текст. Чтобы пометить диапазон текста, как защищенный, можно задать эффект защищенного символа. Дополнительные сведения см. в разделе [форматирования символов в элементами управления Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   EN_DROPFILES позволяет пользователю удалять файлы в элементе управления rich edit, обрабатывая EN_DROPFILES сообщения уведомления. Указанный [ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles) структура содержит сведения о файлах в процессе удаления.  
  
-   EN_SELCHANGE приложение может обнаружить при изменении текущего выделения, обрабатывая сообщения уведомления EN_SELCHANGE. Указывает сообщение уведомления [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange) структуру, содержащую сведения о нового выделения.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

