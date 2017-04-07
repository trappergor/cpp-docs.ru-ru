---
title: "Класс CMFCRibbonComboBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonComboBox class
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
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
ms.openlocfilehash: 747006ee66445eb312c22d658706e5fe81d2a958
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncombobox-class"></a>Класс CMFCRibbonComboBox
`CMFCRibbonComboBox` Класс реализует поле со списком, можно добавить на панель ленты, панель ленты или во всплывающее меню ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Создает объект CMFCRibbonComboBox.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Добавляет уникальный элемент списка.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Удаляет указанный элемент из списка.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Указывает ли поле списка можно изменить размер, он станет.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Возвращает количество элементов в списке.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Возвращает индекс текущего выделенного элемента в поле со списком.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Возвращает высоту окна списка, при удалении списка.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Возвращает размер поля со списком, отображаемый в промежуточный режим.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Возвращает строку, связанную с элементом с заданным индексом в списке.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Возвращает данные, связанные с элементом с заданным индексом в списке.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Указывает, содержит ли элемент управления поля ввода.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Указывает, можно ли изменять размер списка.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Вызывается платформой, когда пользователь выбирает элемент в списке.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Удаляет все элементы из списка и очищает поля ввода.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Выбирает элемент в списке.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Задает высоту окна списка, при перетаскивании.|  
  
## <a name="remarks"></a>Примечания  
 Поле со списком лента состоит из списка, в сочетании с меткой, которая может быть изменена пользователем или статическая метка. Требуется указать тип при создании поле со списком на ленте.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCRibbonComboBox` , добавить элемент в поле со списком, выберите элемент в поле со списком и добавьте поле со списком на панель.  
  
 [!code-cpp[NVC_MFC_RibbonApp&11;](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncombobox.h  
  
##  <a name="additem"></a>CMFCRibbonComboBox::AddItem  
 Добавляет уникальный элемент списка.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszItem`  
 Строка добавляемый элемент.  
  
 [in] `dwData`  
 Данные, связанные с элементом, для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс добавленных элементов.  
  
##  <a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox  
 Создает объект `CMFCRibbonComboBox`.  
  
```  
public:  
CMFCRibbonComboBox(
    UINT nID,  
    BOOL bHasEditBox=TRUE,  
    Int nWidth=-1,  
    LPCTSTR lpszLabel=NULL,  
    Int nImage=-1);

protected:  
CMFCRibbonComboBox();
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор поле со списком.  
  
 [in] `bHasEditBox`  
 `TRUE`Если требуется, чтобы поле ввода элемента управления; `FALSE` в противном случае.  
  
 [in] `nWidth`  
 Ширина поля со списком в точках; или -1 для ширины по умолчанию.  
  
 [in] `lpszLabel`  
 Метка отображаемое поле со списком.  
  
 [in] `nImage`  
 Индекс небольшое изображение в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Ширина по умолчанию составляет 108 пикселей.  
  
##  <a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem  
 Удаляет указанный элемент из списка.  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс удаляемого элемента.  
  
 [in] `dwData`  
 Данные, связанные с удаляемого элемента.  
  
 [in] `lpszText`  
 Строка удаляемого элемента. Если есть несколько элементов с одинаковыми строками, удаляется первый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанный элемент был удален; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabledropdownlistresize"></a>CMFCRibbonComboBox::EnableDropDownListResize  
 Указывает ли поле списка можно изменить размер, он станет.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить изменение размера; `FALSE` отключение изменения размеров.  
  
### <a name="remarks"></a>Примечания  
 При изменении размера списка изменится размер элементов, отображаемых на ней.  
  
##  <a name="finditem"></a>CMFCRibbonComboBox::FindItem  
 Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
 Строка элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента; или -1, если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcount"></a>CMFCRibbonComboBox::GetCount  
 Возвращает количество элементов в списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке, или 0, если список не содержит элементов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel  
 Возвращает индекс текущего выделенного элемента в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента в поле со списком; или -1, если элемент не выбран.  
  
##  <a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight  
 Возвращает высоту окна списка, при удалении списка.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях списка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize  
 Возвращает размер поля со списком, отображаемый в промежуточный режим.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый размер основан на размер поля со списком при отображении небольших изображений.  
  
##  <a name="getitem"></a>CMFCRibbonComboBox::GetItem  
 Возвращает строку, связанную с элементом с заданным индексом в списке.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, связанную с элементом; в противном случае — `NULL` недопустимый параметр индекса или если параметр индекса равен -1 и нет элемента, выбранного в поле со списком.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData  
 Возвращает данные, связанные с элементом с заданным индексом в списке.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом; или 0, если элемент не существует или если параметр индекса равен -1 и отсутствует элемент, выбранный в поле со списком.  
  
##  <a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox  
 Указывает, содержит ли элемент управления поля ввода.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент управления содержит текстовое поле; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isresizedropdownlist"></a>CMFCRibbonComboBox::IsResizeDropDownList  
 Указывает, можно ли изменять размер списка.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в списке может быть изменен; в противном случае `FALSE`. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Примечания  
 Можно включить список изменение размера поля с помощью [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) метод.  
  
##  <a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem  
 Вызывается платформой, когда пользователь выбирает элемент в списке.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nItem`  
 Индекс выбранного элемента.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если необходимо обработать Выбор ввода пользователя.  
  
##  <a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems  
 Удаляет все элементы из списка и очищает поля ввода.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitem"></a>CMFCRibbonComboBox::SelectItem  
 Выбирает элемент в списке.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIndex`  
 Отсчитываемый от нуля индекс элемента в списке.  
  
 [in] `dwData`  
 Данные, связанные с элементом в списке.  
  
 [in] `lpszText`  
 Строка элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight  
 Задает высоту окна списка, при перетаскивании.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHeight`  
 Высота в пикселях списка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию высота — 150 пикселей.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

