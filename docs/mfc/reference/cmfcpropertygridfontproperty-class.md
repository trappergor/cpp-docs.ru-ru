---
title: "Класс CMFCPropertyGridFontProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 505f48bcfb867ae8444d8dbbee360bb04e23d8e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertygridfontproperty-class"></a>Класс CMFCPropertyGridFontProperty
`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, открывается диалоговое окно выбора шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Создает объект `CMFCPropertyGridFontProperty`.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Получает цвет шрифта, выбранного пользователем из диалогового окна шрифта.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Возвращает шрифт, пользователем из диалогового окна шрифта.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
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
 Стили, примененные в диалоговом окне шрифт, который отображается при нажатии кнопки раскрывающегося списка значение свойства. Значение по умолчанию — битовую комбинацию (OR) CF_EFFECTS и CF_SCREENFONTS. Дополнительные сведения см. в разделе `Flags` параметр [CHOOSEFONT структуры](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] `lpszDescr`  
 Описание свойства шрифта. Значение по умолчанию — `NULL`.  
  
 [in] `dwData`  
 Данные приложения, такие как целое число или указатель на другие данные, связанные со свойством. Значение по умолчанию — 0.  
  
 [in] `color`  
 Цвет шрифта. Значением по умолчанию является цвет по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCPropertyGridFontProperty` представляет свойства шрифта в шрифта элемента управления сетки свойств.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как создать объект `CMFCPropertyGridFontProperty` класса. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 Получает цвет шрифта, выбранного пользователем из диалогового окна шрифта.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 RGB-значение цвета, представляющий цвет выбранного шрифта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 Возвращает шрифт, пользователем из диалогового окна шрифта.  
  
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
