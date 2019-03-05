---
title: Класс CMFCPropertyGridFontProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: 2ab4f43b2b12dff88148097e2961f235669aaa62
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295673"
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

*strName*<br/>
[in] Имя свойства.

*LF*<br/>
[in] Структура логического шрифта, которая определяет атрибуты шрифта.

*dwFontDialogFlags*<br/>
[in] Стили, которые применяются в диалоговом окне шрифта, который отображается при нажатии кнопки раскрывающегося списка значение свойства. Значение по умолчанию — битовую комбинацию (OR) флагов CF_EFFECTS и CF_SCREENFONTS. Дополнительные сведения см. в разделе *флаги* параметр [структуры CHOOSEFONT](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta).

*lpszDescr*<br/>
[in] Описание свойства шрифта. Значение по умолчанию имеет значение NULL.

*dwData*<br/>
[in] Данные приложения, такие как целое число или указатель с другими данными, который связан со свойством. Значение по умолчанию — 0.

*color*<br/>
[in] Цвет шрифта. Значением по умолчанию является цвет по умолчанию.

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

Указатель на [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структуру, которая описывает шрифт.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
