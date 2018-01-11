---
title: "Класс CMFCRibbonButtonsGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45851ea66e324f57cb7df3daaa99eb8a1b8b9311
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonbuttonsgroup-class"></a>Класс CMFCRibbonButtonsGroup
`CMFCRibbonButtonsGroup` Позволяет организовать набор кнопок ленты в группе. Все кнопки в группе располагаются непосредственно рядом с друг с другом по горизонтали и заключены в границу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Создает объект `CMFCRibbonButtonsGroup`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Добавляет кнопку в группу.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Добавляет список кнопок в группу.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Возвращает указатель на кнопку, расположенную по указанному индексу.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Возвращает число кнопок в группе.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Возвращает размер изображения обычных образов в группе ленты (переопределяет [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты (переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображениям значков панели инструментов.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Рисует соответствующий образ для указанной кнопки, в зависимости от того, является ли кнопки Обычный, выделенной или отключен.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Назначение изображения для группы.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Задает родительский объект `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объект и все кнопки в нем (переопределяет [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Примечания  
 Группы является производным от [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) и может обрабатываться как единая сущность. Группы можно размещать на любой панели или во всплывающее меню.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCRibbonButtonsGroup` класса. В примере показано `CMFCRibbonButtonsGroup` объекта, назначьте изображения кнопок ленты в группу и добавить кнопку к группе кнопок ленты. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
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
 Указатель на кнопку, чтобы добавить.  
  
##  <a name="addbuttons"></a>CMFCRibbonButtonsGroup::AddButtons  
 Добавляет список кнопок в группу.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstButtons`  
 Список указателей на состояние кнопок, которые вы хотите добавить.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Создает объект `CMFCRibbonButtonsGroup`.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Определяет кнопку, чтобы добавить только что созданный `CMFCRibbonButtonsGroup` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton  
 Возвращает указатель на кнопку, расположенную по указанному индексу.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `i`  
 Отсчитываемый от нуля индекс кнопки для возврата.  
  
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
 Получает размер изображения источника из защищенных `CMFCToolBarImages` член `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер образа источника изображений панели инструментов, в том случае, если они присутствуют, или `CSize` равно нулю, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize  
 Извлекает максимально возможный размер элемента группы ленты.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства в группу ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages  
 Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображениям значков панели инструментов.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если защищенный `CMFCToolBarImages` член `m_Images` не содержит все рисунки или значение FALSE, если.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage  
 Рисует соответствующий образ для указанной кнопки, в зависимости от того, является ли кнопки Обычный, выделенной или отключен.  
  
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
 Прямоугольник, в которой рисуется изображение.  
  
 [in] `pButton`  
 Кнопка, для которой должно быть нарисовано изображение.  
  
 [in] `nImageIndex`  
 Индекс изображения для отрисовки на кнопке (в один из массивов три изображения для кнопок обычный, выделенной или отключен).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll  
 Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages  
 Назначает изображения группе кнопок ленты.  
  
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
>  Наиболее часто используемыми изображениями, изображений, отображаемых при наведении указателя мыши на кнопку. Отключенные это образы, отображаются, когда кнопка отключена.  
  
##  <a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory  
 Задает родительский объект `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объект и все кнопки в ней.  
  
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
