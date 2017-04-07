---
title: "Класс CMFCRibbonButtonsGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup class
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2d8909ca63bd1d9121e1126d46a08312521cc4ac
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbuttonsgroup-class"></a>Класс CMFCRibbonButtonsGroup
`CMFCRibbonButtonsGroup` Позволяет организовать набор кнопок ленты в группу. Все кнопки в группе располагаются непосредственно рядом с друг с другом по горизонтали и заключены в границу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Создает объект `CMFCRibbonButtonsGroup`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Добавляет кнопку в группу.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Добавляет список кнопок в группу.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Возвращает указатель на кнопку, расположенную по указанному индексу.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Возвращает число кнопок в группе.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Возвращает размер изображения обычных образов в группе ленты (переопределяет [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Возвращает обычный размер элемента ленты (переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображений на панели инструментов.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Рисует соответствующий образ для указанной кнопки в зависимости от того, является ли кнопки normal, выделенные или отключен.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Назначение изображения для группы.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Задает родительский объект `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объект и все кнопки в нем (переопределяет [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Примечания  
 Группы является производным от [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) и им можно управлять как единым целым. Группы можно разместить на любой панели или во всплывающее меню.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCRibbonButtonsGroup` класса. В примере показано `CMFCRibbonButtonsGroup` объекта, назначать изображения кнопок ленты в группу и добавьте кнопку в группу кнопок ленты. Этот фрагмент кода является частью [пример рисования клиента](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>CMFCRibbonButtonsGroup::AddButton  
 Добавляет кнопку в группу.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку для добавления.  
  
##  <a name="addbuttons"></a>CMFCRibbonButtonsGroup::AddButtons  
 Добавляет список кнопок в группу.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstButtons`  
 Список указателей на кнопок, которые требуется добавить.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Создает объект `CMFCRibbonButtonsGroup`.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указывает кнопку для добавления к вновь созданной `CMFCRibbonButtonsGroup` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton  
 Возвращает указатель на кнопку, расположенную по указанному индексу.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `i`  
 Отсчитываемый от нуля индекс элемента управления button для возврата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на кнопку, расположенную по указанному индексу. `NULL`Если указанный индекс находится вне диапазона.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount  
 Возвращает число кнопок в группе.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число кнопок в группе.  
  
##  <a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize  
 Получает размер исходного изображения из защищенных `CMFCToolBarImages` член `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает исходный размер изображения изображений панели инструментов, если они присутствуют, или `CSize` равно нулю, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize  
 Получает максимально возможный размер элемента группы ленты.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства в группу ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages  
 Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображений на панели инструментов.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если защищенный `CMFCToolBarImages` член `m_Images` содержит изображения, или значение FALSE, если не.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage  
 Рисует соответствующий образ для указанной кнопки в зависимости от того, является ли кнопки normal, выделенные или отключен.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства `CMFCRibbonButtonsGroup` объекта.  
  
 [in] `rectImage`  
 Прямоугольник, в котором должно быть нарисовано изображение.  
  
 [in] `pButton`  
 Кнопка, для которой должно быть нарисовано изображение.  
  
 [in] `nImageIndex`  
 Индекс изображения для отрисовки на кнопке (в один из массивов три изображения для кнопок normal, выделенные или отключен).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll  
 Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages  
 Назначает изображения группы кнопок ленты.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pImages`  
 Обычных образов.  
  
 [in] `pHotImages`  
 Наиболее часто используемыми изображениями.  
  
 [in] `pDisabledImages`  
 Отключенные изображения.  
  
### <a name="remarks"></a>Примечания  
 Вызовите `SetImages` перед добавлением кнопок в группу. Число образов, должен быть больше или равно числу кнопки для добавления в группу.  
  
> [!NOTE]
>  Наиболее часто используемыми изображениями, изображения, отображаемые при наведении указателя мыши на кнопку. Отключенные это образы, отображаются, когда кнопка отключена.  
  
##  <a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory  
 Задает родительский объект `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объект и все кнопки в нем.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Указатель на родительской категории, чтобы задать (групп с вкладками в элементы управления ленты, называются категории).  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

