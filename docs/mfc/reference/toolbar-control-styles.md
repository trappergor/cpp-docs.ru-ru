---
title: "Стили элемента управления панель инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d81be893ce84da24b3a30518219ee1f6fd10057
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-control-styles"></a>Стили элемента управления панели инструментов
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) имеет набор стилей флагов, определяющих внешний вид и поведение кнопки. Сочетание этих флагов можно задать путем вызова [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). В этом разделе перечислены значения флагов стилей и их значений.  
  
## <a name="property-values"></a>Значения свойств  
 Следующие значения определить тип, представляющий элемент управления кнопки:  
  
 TBBS_BUTTON  
 Стандартная pushbutton (по умолчанию).  
  
 TBBS_CHECKBOX  
 Флажок.  
  
 TBBS_CHECKGROUP  
 Начало группы флажков.  
  
 TBBS_GROUP  
 Начало группе кнопок.  
  
 TBBS_SEPARATOR  
 Разделитель.  
  
 Следующие значения представляют текущее состояние элемента управления:  
  
 TBBS_CHECKED  
 Будет установлен флажок.  
  
 TBBS_DISABLED  
 Элемент управления отключен.  
  
 TBBS_INDETERMINATE  
 Флажок находится в неопределенном состоянии.  
  
 TBBS_PRESSED  
 Нажата кнопка.  
  
 Следующее значение изменяется макет кнопки на панели инструментов.  
  
 TBBS_BREAK  
 Помещает элемент без разделения столбцов в новой строке или в новом столбце.  
  
## <a name="remarks"></a>Примечания  
 Стиль текущего хранится в [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Не задано новое значение `m_nStyle` напрямую, так как некоторые производные классы дополнительной обработки при вызове `SetStyles`.  
  
 Диспетчер визуальных определяет внешний вид кнопок в каждом состоянии. В разделе [диспетчер визуализации](../../mfc/visualization-manager.md) для получения дополнительной информации.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Диспетчер визуализации](../../mfc/visualization-manager.md)


