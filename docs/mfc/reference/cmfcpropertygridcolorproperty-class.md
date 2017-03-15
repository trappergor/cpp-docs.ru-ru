---
title: "Класс CMFCPropertyGridColorProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty class
- CMFCPropertyGridColorProperty::OnClickButton method
- CMFCPropertyGridColorProperty::FormatProperty method
- CMFCPropertyGridColorProperty::OnDrawValue method
- CMFCPropertyGridColorProperty::OnUpdateValue method
- CMFCPropertyGridColorProperty::OnEdit method
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: 33
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
ms.openlocfilehash: 7069e35a44dbb0dbd4ad8d5d2b9156ccfbc15c76
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridcolorproperty-class"></a>Класс CMFCPropertyGridColorProperty
Класс `CMFCPropertyGridColorProperty` поддерживает элемент управления списка свойств, открывающий диалоговое окно выбора цвета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Создает объект `CMFCPropertyGridColorProperty`.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Позволяет *автоматического* кнопку на диалоговое окно выбора цвета. (Обозначенные стандартной кнопки автоматического **автоматическое**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Позволяет *других* кнопку на диалоговое окно выбора цвета. (Стандартный других кнопка обозначается **Дополнительные цвета... **.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Возвращает текущий цвет свойства.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Вызывается платформой для отображения значения свойства. (Переопределяет [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Вызывается платформой непосредственно перед изменением значения свойства пользователем. (Переопределяет [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Вызывается платформой при присвоении изменяемому свойству нового значения. (Переопределяет [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Задает новый цвет свойства.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов в текущей таблице свойств цвета.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Задает изменяемому свойству исходное значение.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CMFCPropertyGridColorProperty` поддерживает свойство цвета, которое можно добавить в элемент управления "список свойств". Дополнительные сведения см. в разделе [CMFCPropertyGridCtrl класса](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание объекта класса `CMFCPropertyGridColorProperty` и его настройка с помощью различных методов класса `CMFCPropertyGridColorProperty`. В коде показывается, как можно задействовать кнопки автоматического выбора и выбора другого цвета, а также выполняется назначение цвета и количества столбцов. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#13;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="a-namecmfcpropertygridcolorpropertya--cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 Создает объект `CMFCPropertyGridColorProperty`.  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strName`  
 Имя свойства.  
  
 [in] `color`  
 Значение цвета свойства.  
  
 [in] `pPalette`  
 Указатель на палитру цветов. Значение по умолчанию — `NULL`.  
  
 [in] `lpszDescr`  
 Описание свойства. Значение по умолчанию — `NULL`.  
  
 [in] `dwData`  
 Данные конкретного приложения, такие как целое число или указатель на другие данные, связанные со свойством. Значение по умолчанию — 0.  
  
##  <a name="a-nameenableautomaticbuttona--cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton  
 Позволяет *автоматического* кнопку на диалоговое окно выбора цвета. (Обозначенные стандартной кнопки автоматического **автоматическое**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текст метки кнопки «автоматический».  
  
 [in] `colorAutomatic`  
 Значение цвета RGB цвета автоматически (по умолчанию).  
  
 [in] `bEnable`  
 `TRUE`Чтобы включить автоматическое кнопки. в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenableotherbuttona--cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton  
 Позволяет *других* кнопку на диалоговое окно выбора цвета. (Стандартный других кнопка обозначается **Дополнительные цвета... **.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszLabel`  
 Текст метки, другие кнопки.  
  
 [in] `bAltColorDlg`  
 `TRUE`для отображения `CMFCColorDialog` диалоговым окном. `FALSE` для отображения диалогового окна выбора стандартный цвет. Значение по умолчанию — `TRUE`.  
  
 [in] `bEnable`  
 `TRUE`для отображения кнопки. в противном случае — `FALSE`.  Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcolora--cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor  
 Возвращает текущий цвет свойства.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetcolora--cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor  
 Задает новый цвет свойства.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetcolumnsnumbera--cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber  
 Задает число столбцов в текущей таблице свойств цвета.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nColumnsNumber`  
 Предпочтительный число столбцов в сетке свойств цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает значение `m_nColumnsNumber` защищенного члена данных.  
  
##  <a name="a-namesetoriginalvaluea--cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue  
 Задает изменяемому свойству исходное значение.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `varValue`  
 Значение.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) метод, чтобы восстановить исходное значение измененного свойства.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

