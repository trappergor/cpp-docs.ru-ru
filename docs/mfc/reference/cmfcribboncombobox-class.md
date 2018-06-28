---
title: Класс CMFCRibbonComboBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5894f1fc9bd901bef6e830250f4e1f8e9bdd335
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040758"
---
# <a name="cmfcribboncombobox-class"></a>Класс CMFCRibbonComboBox
`CMFCRibbonComboBox` Класс реализует поле со списком, можно добавить на панель ленты, панель ленты или во всплывающее меню ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Участники  
  
### <a name="constructors"></a>Конструкторы  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Создает объект CMFCRibbonComboBox.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Добавляет уникальный элемент списка.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Удаляет указанный элемент из списка.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Указывает ли он станет списка можно изменить размер.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Возвращает количество элементов в списке.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Возвращает индекс элемента, выбранного в поле со списком.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Возвращает высоту окна списка, при удалении списка.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Возвращает размер поля со списком, показанной в промежуточный режим.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Возвращает строку, связанную с элементом с заданным индексом в поле со списком.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Возвращает данные, связанные с элементом с заданным индексом в поле со списком.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Указывает, содержит ли элемент управления поля редактирования.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Указывает, можно ли изменить размер списка.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Вызывается платформой, когда пользователь выбирает элемент в списке.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Удаляет все элементы из списка и очищает поля ввода.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Выбирает элемент в списке.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Задает высоту окна списка, при его удалении.|  
  
## <a name="remarks"></a>Примечания  
 Поле со списком на ленте состоит из списка, в сочетании с статической метки или метки, которая может быть изменена пользователем. Необходимо указать тип при создании поле со списком на ленте.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCRibbonComboBox` класса, добавьте элемент в поле со списком, выберите элемент в поле со списком и добавить поле со списком на панель.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncombobox.h  
  
##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem  
 Добавляет уникальный элемент списка.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszItem*  
 Строка добавляемый элемент.  
  
 [in] *dwData*  
 Данные, связанные с элементом, для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс добавленный элемент.  
  
##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox  
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
 [in] *nID*  
 Идентификатор поле со списком.  
  
 [in] *bHasEditBox*  
 `TRUE` Если требуется, чтобы поле ввода элемента управления; `FALSE` в противном случае.  
  
 [in] *nWidth*  
 Ширина в пикселях; поле со списком или -1 для ширину по умолчанию.  
  
 [in] *lpszLabel*  
 Метка отображаемое поле со списком.  
  
 [in] *nImage*  
 Индекс мелкое изображение поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Ширина по умолчанию составляет 108 пикселей.  
  
##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem  
 Удаляет указанный элемент из списка.  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iIndex*  
 Отсчитываемый от нуля индекс удаляемого элемента.  
  
 [in] *dwData*  
 Данные, связанные с удаляемого элемента.  
  
 [in] *lpszText*  
 Строка удаляемого элемента. При наличии нескольких элементов с такой же строки, первый элемент удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если указанный элемент был удален; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize  
 Указывает ли он станет списка можно изменить размер.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 `TRUE` Чтобы включить изменение размера; `FALSE` отключение изменения размера.  
  
### <a name="remarks"></a>Примечания  
 При включении изменение размеров списка изменит размер элементов, которые в нем отображаются.  
  
##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem  
 Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszText*  
 Строка элемент в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента; или -1, если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount  
 Возвращает количество элементов в списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке, или 0, если список не содержит элементов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel  
 Возвращает индекс элемента, выбранного в поле со списком.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента в списке; или -1, если элемент не выбран.  
  
##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight  
 Возвращает высоту окна списка, при удалении списка.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях списка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize  
 Возвращает размер поля со списком, показанной в промежуточный режим.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства для поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый размер основан на размер поля со списком при отображении изображений небольшого размера.  
  
##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem  
 Возвращает строку, связанную с элементом с заданным индексом в поле со списком.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iIndex*  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, связанную с элементом; в противном случае `NULL` недопустимый параметр индекса или если параметр индекса равно -1 и нет элемента, выбранного в поле со списком.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData  
 Возвращает данные, связанные с элементом с заданным индексом в поле со списком.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iIndex*  
 Отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Данные, связанные с элементом; или 0, если элемент не существует или если параметр индекса равно -1 и отсутствует элемент, выбранный в поле со списком.  
  
##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox  
 Указывает, содержит ли элемент управления поля редактирования.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если элемент управления содержит текстовое поле; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList  
 Указывает, можно ли изменить размер списка.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если в списке могут быть изменены; в противном случае `FALSE`. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Примечания  
 Можно включить список поле изменения размера с помощью [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) метод.  
  
##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem  
 Вызывается платформой, когда пользователь выбирает элемент в списке.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nItem*  
 Индекс выбранного элемента.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если необходимо обработать Выбор ввода пользователя.  
  
##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems  
 Удаляет все элементы из списка и очищает поля ввода.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem  
 Выбирает элемент в списке.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iIndex*  
 Отсчитываемый от нуля индекс элемента в списке.  
  
 [in] *dwData*  
 Данные, связанные с элементом в списке.  
  
 [in] *lpszText*  
 Строка элемент в поле со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight  
 Задает высоту окна списка, при его удалении.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nHeight*  
 Высота в пикселях списка.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию высота — 150 пикселей.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)
