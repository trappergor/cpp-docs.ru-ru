---
title: Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE | Документация Майкрософт
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
ms.openlocfilehash: b87b0c8c179e2982c450d244c50ea89dad2a596a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848610"
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>Перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE
Задает режим рисования, который позволяет изменять образ в диалоговом окне редактора изображений.  
  
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
|Имя|Описание:|  
|IMAGE_EDIT_MODE_PEN|Используется для рисования отдельных пикселей.|  
|IMAGE_EDIT_MODE_FILL|Используется для заполнения всех смежных областях, которые содержат цвет в текущем положении курсора.|  
|IMAGE_EDIT_MODE_LINE|Используется для рисования строки.|  
|IMAGE_EDIT_MODE_RECT|Используется для рисования прямоугольника.|  
|IMAGE_EDIT_MODE_ELLIPSE|Используется для рисования эллипса.|  
|IMAGE_EDIT_MODE_COLOR|Используется для задания текущего цвета на цвет в текущем положении курсора.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCImagePaintArea` И `CMFCImageEditorDialog` это перечисление используется классами для текущего режима рисования. Режим рисования и текущего цвета используются для изменения области рисунка в диалоговом окне редактора изображений. Дополнительные сведения о `CMFCImagePaintArea` и `CMFCImageEditorDialog`, см. в разделе [класс CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md) и [класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 При выборе цвета из изображения, используя режим рисования IMAGE_EDIT_MODE_COLOR платформа присваивает текущий режим рисования для IMAGE_EDIT_MODE_PEN.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximagepaintarea.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
