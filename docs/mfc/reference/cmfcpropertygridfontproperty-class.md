---
title: Класс Кмфкпропертигридфонтпроперти
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
ms.openlocfilehash: a3c5b806482a97d64a9ffab92877781cb8778b6b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505115"
---
# <a name="cmfcpropertygridfontproperty-class"></a>Класс Кмфкпропертигридфонтпроперти

`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления "список свойств", открывающий диалоговое окно выбора шрифта.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкпропертигридфонтпроперти:: Кмфкпропертигридфонтпроперти](#cmfcpropertygridfontproperty)|Создает объект `CMFCPropertyGridFontProperty`.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [кмфкпропертигридпроперти:: форматпроперти](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[Кмфкпропертигридфонтпроперти:: "Color"](#getcolor)|Извлекает цвет шрифта, который выбирает пользователь в диалоговом окне Шрифт.|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Извлекает шрифт, который пользователь выбирает в диалоговом окне Шрифт.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [кмфкпропертигридпроперти:: онкликкбуттон](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кмфкпропертигридпроперти](../../mfc/reference/cmfcpropertygridproperty-class.md)

[кмфкпропертигридфонтпроперти](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспропертигридктрл. h

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
окне Имя свойства.

*возврата*<br/>
окне Логическая структура шрифта, указывающая атрибуты шрифта.

*двфонтдиалогфлагс*<br/>
окне Стили, которые применяются к диалоговому окну Шрифт, которое отображается при нажатии кнопки раскрывающегося списка значение свойства. Значение по умолчанию — это побитовое сочетание (или) CF_EFFECTS и CF_SCREENFONTS. Дополнительные сведения см. в описании параметра flags [структуры CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw).

*лпсздескр*<br/>
окне Описание свойства Font. Значение по умолчанию — NULL.

*двдата*<br/>
окне Данные конкретного приложения, такие как целое число или указатель на другие данные, связанные со свойством. Значение по умолчанию — 0.

*color*<br/>
окне Цвет шрифта. Значением по умолчанию является цвет по умолчанию.

### <a name="remarks"></a>Примечания

`CMFCPropertyGridFontProperty` Объект представляет свойство Font в элементе управления шрифта сетки свойств.

### <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCPropertyGridFontProperty` класса. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor

Извлекает цвет шрифта, который выбирает пользователь в диалоговом окне Шрифт.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющее выбранный цвет шрифта.

### <a name="remarks"></a>Примечания

##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont

Извлекает шрифт, который пользователь выбирает в диалоговом окне Шрифт.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) , описывающую выбранный шрифт.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
