---
title: Стили элемента управления панель инструментов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1958c83ef5a0eec5f3c7f5873451edd3839146be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373199"
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


