---
title: "Класс CMFCImagePaintArea | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea class
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c16fd9605474e57f167646ddc9bc91d235d1cba5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintarea-class"></a>Класс CMFCImagePaintArea
Предоставляет область рисунка, который позволяет изменять образ в диалоговое окно редактора изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Создает объект `CMFCImagePaintArea`.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCImagePaintArea::GetMode](#getmode)|Получает текущий режим рисования.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Задает растровое изображение для области рисунка.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Задает текущий цвет рисования.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Задает текущий режим рисования.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс не предназначен для непосредственного использования в коде.  
  
 Платформа использует этот класс, чтобы отобразить область рисунка в диалоговое окно редактора изображений. Дополнительные сведения о диалоговом окне редактора изображений см. в разделе [CMFCImageEditorDialog класса](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCImagePaintArea` класса, установка текущего рисования цвета, текущий режим рисования и задать растровое изображение для области рисунка.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#37;](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 Создает объект `CMFCImagePaintArea`.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pParentDlg`|Указатель на диалоговое окно, являющийся родительским для редактора изображений.|  
  
##  <a name="getmode"></a>CMFCImagePaintArea::GetMode  
 Получает текущий режим рисования.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.  
  
##  <a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 Задает растровое изображение для области рисунка.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pBitmap`|Новый точечный рисунок для отображения.|  
  
### <a name="remarks"></a>Примечания  
 Если `pBitmap` — `NULL`, этот метод задает размер области рисования изменяемым до нуля. В противном случае он устанавливает размер области рисования изменяемые размер предоставленного растрового изображения.  
  
##  <a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 Задает текущий цвет рисования.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `color`|Новые цвета.|  
  
### <a name="remarks"></a>Примечания  
 При выборе цвета на панели палитры редактора изображений или палитра цветов, платформа вызывает этот метод для обновления текущего цвета. Черный цвет рисования ( `COLORREF` значение 0).  
  
 Цвета используется диалоговое окно редактора изображений для всех режимов отображения, за исключением `IMAGE_EDIT_MODE_COLOR`. Дополнительные сведения о графических режимов см. в разделе [перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>CMFCImagePaintArea::SetMode  
 Задает текущий режим рисования.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `mode`|[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

