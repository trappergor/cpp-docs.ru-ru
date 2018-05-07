---
title: Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef036c1d619bf85e21edafbd20f20cc27c7c12d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE
Задает режим рисования, который позволяет изменить изображение в диалоговом окне редактора изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum IMAGE_EDIT_MODE  
{  
    IMAGE_EDIT_MODE_PEN = 0,  
    IMAGE_EDIT_MODE_FILL, 
    IMAGE_EDIT_MODE_LINE, 
    IMAGE_EDIT_MODE_RECT, 
    IMAGE_EDIT_MODE_ELLIPSE, 
    IMAGE_EDIT_MODE_COLOR 
};  
```  
  
## <a name="members"></a>Участники  
  
|||  
|-|-|  
|Имя|Описание|  
|`IMAGE_EDIT_MODE_PEN`|Используется для отрисовки отдельных пикселей.|  
|`IMAGE_EDIT_MODE_FILL`|Используется для заполнения всех смежных областей, содержащих цвет в текущем положении курсора.|  
|`IMAGE_EDIT_MODE_LINE`|Используется для рисования линии.|  
|`IMAGE_EDIT_MODE_RECT`|Используется для отрисовки прямоугольника.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Используется, чтобы нарисовать эллипс.|  
|`IMAGE_EDIT_MODE_COLOR`|Используется для задания текущего цвета на цвет в текущем положении курсора.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCImagePaintArea` И `CMFCImageEditorDialog` это перечисление используется классами для текущего режима отображения. Режим рисования и текущего цвета используются для изменения области рисунка в диалоговом окне редактора изображений. Дополнительные сведения о `CMFCImagePaintArea` и `CMFCImageEditorDialog`, в разделе [класса CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md) и [CMFCImageEditorDialog класса](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 При выборе цвета из образа с помощью `IMAGE_EDIT_MODE_COLOR` режим рисования, платформа задает текущий режим рисования `IMAGE_EDIT_MODE_PEN`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximagepaintarea.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
