---
title: "Класс CMFCPropertyGridFontProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty::OnClickButton method
- CMFCPropertyGridFontProperty class
- CMFCPropertyGridFontProperty::FormatProperty method
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
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
ms.openlocfilehash: 05d1db7e7de2ee72244e885d8a083ac3cda20142
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfontproperty-class"></a>Класс CMFCPropertyGridFontProperty
`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, открывается диалоговое окно выбора шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Создает объект `CMFCPropertyGridFontProperty`.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Получает цвет шрифта, выбранного пользователем в диалоговом окне шрифта.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Получает шрифт, пользователем из диалогового окна шрифта.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="a-namecmfcpropertygridfontpropertya--cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 Создает объект `CMFCPropertyGridFontProperty`.  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strName`  
 Имя свойства.  
  
 [in] `lf`  
 Структура шрифте, определяет атрибуты шрифта.  
  
 [in] `dwFontDialogFlags`  
 Стили, примененные в диалоговом окне шрифт, который отображается при нажатии кнопки раскрывающегося списка значение свойства. Значение по умолчанию — побитовое сочетание (или) CF_EFFECTS и CF_SCREENFONTS. Дополнительные сведения см. в разделе `Flags` параметр [структуры CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] `lpszDescr`  
 Описание свойства шрифта. Значение по умолчанию — `NULL`.  
  
 [in] `dwData`  
 Данные конкретного приложения, такие как целое число или указатель на другие данные, связанные со свойством. Значение по умолчанию — 0.  
  
 [in] `color`  
 Цвет шрифта. Значением по умолчанию является цвет по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCPropertyGridFontProperty` объект представляет свойство шрифта в шрифта элемента управления сетки свойств.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется способ создания объекта `CMFCPropertyGridFontProperty` класса. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#26;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="a-namegetcolora--cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 Получает цвет шрифта, выбранного пользователем в диалоговом окне шрифта.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение цвета, представляющий цвет выбранного шрифта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlogfonta--cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 Получает шрифт, пользователем из диалогового окна шрифта.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структура, описывающая выбранного шрифта.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

