---
title: "Стили элемента управления панели инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1c50009a50c5b80e007add9de679315df6aecea9
ms.lasthandoff: 02/24/2017

---
# <a name="toolbar-control-styles"></a>Стили элемента управления панели инструментов
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) имеет набор флагов стилей, которые определяют внешний вид и поведение кнопки. Сочетание этих флагов можно задать путем вызова [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). В этом разделе перечислены значения флагов стилей и их значения.  
  
## <a name="property-values"></a>Значения свойств  
 Следующие значения определить тип, представляющий элемент управления кнопки:  
  
 TBBS_BUTTON  
 Стандартная pushbutton (по умолчанию).  
  
 TBBS_CHECKBOX  
 Флажок.  
  
 TBBS_CHECKGROUP  
 Начало группы флажков.  
  
 TBBS_GROUP  
 Начало группы кнопок.  
  
 TBBS_SEPARATOR  
 Разделитель.  
  
 Следующие значения представляют текущее состояние элемента управления.  
  
 TBBS_CHECKED  
 Флажок установлен.  
  
 TBBS_DISABLED  
 Элемент управления отключен.  
  
 TBBS_INDETERMINATE  
 Флажок находится в неопределенном состоянии.  
  
 TBBS_PRESSED  
 Нажата кнопка.  
  
 Следующее значение изменяется макет кнопки на панели инструментов:  
  
 TBBS_BREAK  
 Помещает элемент на новой строке или в новом столбце без разделения столбцов.  
  
## <a name="remarks"></a>Примечания  
 Текущий стиль сохраняется в [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Не задано новое значение `m_nStyle` напрямую, поскольку несколько классов, производных дополнительной обработки при вызове `SetStyles`.  
  
 Диспетчер визуального представления определяет внешний вид кнопки в каждом состоянии. В разделе [диспетчер визуализации](../../mfc/visualization-manager.md) подробнее.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Диспетчер визуализации](../../mfc/visualization-manager.md)



