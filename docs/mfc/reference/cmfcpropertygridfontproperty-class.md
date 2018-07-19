---
title: Класс CMFCPropertyGridFontProperty | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ea43fefabe43bec8a5bf9b00404491a405e5416
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852985"
---
# <a name="cmfcpropertygridfontproperty-class"></a>Класс CMFCPropertyGridFontProperty
`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, который открывает диалоговое окно выбора шрифта.  
  
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
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Возвращает цвет шрифта, выбранного пользователем в диалоговом окне шрифта.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Получает шрифт, который пользователь выбирает в диалоговом окне шрифта.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
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
 [in] *strName*  
 Имя свойства.  
  
 [in] *lf*  
 Структура логического шрифта, которая определяет атрибуты шрифта.  
  
 [in] *dwFontDialogFlags*  
 Стили, которые применяются в диалоговом окне шрифта, который отображается при нажатии кнопки раскрывающегося списка значение свойства. Значение по умолчанию — битовую комбинацию (OR) флагов CF_EFFECTS и CF_SCREENFONTS. Дополнительные сведения см. в разделе *флаги* параметр [структуры CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] *lpszDescr*  
 Описание свойства шрифта. Значение по умолчанию имеет значение NULL.  
  
 [in] *dwData*  
 Данные приложения, такие как целое число или указатель с другими данными, который связан со свойством. Значение по умолчанию — 0.  
  
 [in] *цвет*  
 Цвет шрифта. Значением по умолчанию является цвет по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCPropertyGridFontProperty` объект представляет свойство font в элементе управления шрифта сетки свойств.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как построить объект `CMFCPropertyGridFontProperty` класса. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor  
 Возвращает цвет шрифта, выбранного пользователем в диалоговом окне шрифта.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB, представляющее цвет выбранного шрифта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont  
 Получает шрифт, который пользователь выбирает в диалоговом окне шрифта.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуру, которая описывает шрифт.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
