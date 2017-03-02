---
title: "Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
- CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
- CMFCImagePaintArea.IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 15
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 364b33568e2a21a4649923f4478b5b2456b23747
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE
Задает режим рисования, который используется для изменения образа в диалоговое окно редактора изображений.  
  
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
  
## <a name="members"></a>Члены  
  
|||  
|-|-|  
|Имя|Описание|  
|`IMAGE_EDIT_MODE_PEN`|Используется для рисования отдельным точкам.|  
|`IMAGE_EDIT_MODE_FILL`|Используется для заполнения всех смежные области, содержащие цвет в текущем положении курсора.|  
|`IMAGE_EDIT_MODE_LINE`|Используется для рисования линии.|  
|`IMAGE_EDIT_MODE_RECT`|Используется, чтобы нарисовать прямоугольник.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Используется, чтобы нарисовать эллипс.|  
|`IMAGE_EDIT_MODE_COLOR`|Используется для задания текущего цвета на цвет в текущей позиции курсора.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCImagePaintArea` И `CMFCImageEditorDialog` это перечисление используется классами, чтобы задать режим рисования. Режим рисования и текущего цвета используются для изменения области рисунка в диалоговое окно редактора изображений. Дополнительные сведения о `CMFCImagePaintArea` и `CMFCImageEditorDialog`, в разделе [класса CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md) и [CMFCImageEditorDialog класса](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 При выборе цвета из образа с помощью `IMAGE_EDIT_MODE_COLOR` режим рисования, платформа задает текущий режим рисования `IMAGE_EDIT_MODE_PEN`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximagepaintarea.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

