---
title: Класс CMFCImagePaintArea | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 449d79119b15e814485f3b7e0c3eb7472d314d19
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852488"
---
# <a name="cmfcimagepaintarea-class"></a>Класс CMFCImagePaintArea
Предоставляет область картинки, которая позволяет изменять образ в диалоговом окне редактора изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Создает объект `CMFCImagePaintArea`.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCImagePaintArea::GetMode](#getmode)|Извлекает текущий режим рисования.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Задает растровое изображение для области рисунка.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Задает текущий цвет рисования.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Задает текущий режим рисования.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс не предназначен для использования непосредственно из программного кода.  
  
 Инфраструктура использует этот класс для отображения области рисунка в диалоговом окне редактора изображений. Дополнительные сведения о диалоговом окне редактора изображений, см. в разделе [класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта класса `CMFCImagePaintArea` класса, задайте текущего рисования цвета, задавать текущий режим рисования и задавать растрового изображения для области рисунка.  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea  
 Создает объект `CMFCImagePaintArea`.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *pParentDlg*|Указатель на диалоговое окно, которое является родительским для редактора изображений.|  
  
##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode  
 Извлекает текущий режим рисования.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.  
  
##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap  
 Задает растровое изображение для области рисунка.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *pBitmap*|Новый растрового изображения для отображения.|  
  
### <a name="remarks"></a>Примечания  
 Если *pBitmap* имеет значение NULL, этот метод задает размер области рисования, изменяемые в ноль. В противном случае он устанавливает размер области рисования, изменяемые размер предоставленного растрового изображения.  
  
##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor  
 Задает текущий цвет рисования.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *цвет*|Новый цвет рисования.|  
  
### <a name="remarks"></a>Примечания  
 При выборе цвета в строке палитры изображения редактора или палитра цветов, платформа вызывает этот метод, чтобы обновить текущий цвет рисования. Черный цвет рисования (COLORREF значение 0).  
  
 Цвета для всех режимов отображения, за исключением IMAGE_EDIT_MODE_COLOR используется диалоговое окно редактора изображений. Дополнительные сведения о режимы, см. в разделе [перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode  
 Задает текущий режим рисования.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *режим*|[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
