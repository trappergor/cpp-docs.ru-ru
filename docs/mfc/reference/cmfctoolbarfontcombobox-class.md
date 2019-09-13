---
title: Класс Кмфктулбарфонткомбобокс
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 7e19fc9257c1fe986ff09a8bbc86bf2fb55af7ee
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504742"
---
# <a name="cmfctoolbarfontcombobox-class"></a>Класс Кмфктулбарфонткомбобокс

Кнопка на панели инструментов, содержащая элемент управления "поле со списком", позволяющий пользователю выбрать шрифт из списка системных шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфктулбарфонткомбобокс:: Кмфктулбарфонткомбобокс](#cmfctoolbarfontcombobox)|Создает объект `CMFCToolBarFontComboBox`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфктулбарфонткомбобокс:: Жетфонтдеск](#getfontdesc)|Возвращает указатель на `CMFCFontInfo` объект для указанного индекса в поле со списком.|
|[Кмфктулбарфонткомбобокс:: Сетфонт](#setfont)|Выбирает шрифт в поле со списком шрифтов в соответствии с именем шрифта или префиксом и кодировкой шрифта.|

### <a name="data-members"></a>Элементы данных

[Кмфктулбарфонткомбобокс:: m_nFontHeight](#m_nfontheight)<br/>
Высота символов в поле со списком шрифтов.

## <a name="remarks"></a>Примечания

Чтобы добавить на панель инструментов кнопку с полем со списком шрифтов, выполните следующие действия.

1. Зарезервируйте идентификатор фиктивного ресурса для кнопки на родительском ресурсе панели инструментов.

1. `CMFCToolBarFontComboBox` Создайте объект.

1. В обработчике сообщений, который обрабатывает сообщение AFX_WM_RESETTOOLBAR, замените исходную кнопку новой кнопкой со списком с помощью [CMFCToolBar:: реплацебуттон](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

1. Синхронизируйте шрифт, выбранный в поле со списком, со шрифтом в документе с помощью метода [кмфктулбарфонткомбобокс:: сетфонт](#setfont) .

Чтобы синхронизировать шрифт документа с шрифтом, выбранным в поле со списком, используйте метод [кмфктулбарфонткомбобокс:: жетфонтдеск](#getfontdesc) для получения атрибутов выбранного шрифта и используйте эти атрибуты для создания объекта [класса кфонт](../../mfc/reference/cfont-class.md) .

Кнопка поля со списком шрифтов вызывает функцию Win32 [EnumFontFamiliesEx](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) , чтобы определить шрифты экрана и принтера, доступные системе.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[кмфктулбаркомбобоксбуттон](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[кмфктулбарфонткомбобокс](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкстулбарфонткомбобокс. h

##  <a name="cmfctoolbarfontcombobox"></a>Кмфктулбарфонткомбобокс:: Кмфктулбарфонткомбобокс

Конструирует объект [кмфктулбарфонткомбобокс](../../mfc/reference/cmfctoolbarfontcombobox-class.md) .

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
окне Идентификатор команды поля со списком.

*иимаже*<br/>
окне Отсчитываемый от нуля индекс изображения панели инструментов. Изображение находится в объекте [класса кмфктулбаримажес](../../mfc/reference/cmfctoolbarimages-class.md) , который обслуживает класс класса [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) .

*нфонттипе*<br/>
окне Типы шрифтов, содержащихся в поле со списком. Этот параметр может быть сочетанием (Boolean или) следующих значений:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*Тип nChar*<br/>
окне Если задано значение DEFAULT_CHARSET, поле со списком содержит все шрифты с уникальными именами во всех наборах символов. (При наличии двух шрифтов с одинаковым именем поле со списком содержит один из них.) Если задано допустимое значение кодировки, поле со списком содержит только шрифты из указанной кодировки. Список возможных наборов символов см. в разделе [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) .

*двстиле*<br/>
окне Стиль поля со списком. (см. раздел [стили полей со списком](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*ивидс*<br/>
окне Ширина (в пикселях) элемента управления "поле ввода".

*нпитчандфамили*<br/>
окне Если задано значение DEFAULT_PITCH, поле со списком содержит шрифты, независимо от их высоты. Если задано значение FIXED_PITCH или VARIABLE_PITCH, поле со списком содержит только шрифты с таким типом. Фильтрация на основе семейства шрифтов в настоящее время не поддерживается.

*плстфонтсекстернал*<br/>
заполняет Указатель на объект [класса коблист](../../mfc/reference/coblist-class.md) , в котором хранятся доступные шрифты.

### <a name="remarks"></a>Примечания

Обычно объекты хранят список доступных шрифтов в одном общем `CObList` объекте. `CMFCToolBarFontComboBox` Если вы используете вторую перегрузку конструктора и предоставляете допустимый указатель на *плстфонтсекстернал*, этот `CMFCToolBarFontComboBox` объект будет заполнять то `CObList` , что *плстфонтсекстернал* указывает на доступные шрифты.

### <a name="example"></a>Пример

В следующем примере показано, как создать `CMFCToolBarFontComboBox` объект. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

##  <a name="getfontdesc"></a>Кмфктулбарфонткомбобокс:: Жетфонтдеск

Возвращает указатель на `CMFCFontInfo` объект для указанного индекса в поле со списком.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Параметры

*ииндекс*<br/>
окне Задает отсчитываемый от нуля индекс элемента поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CMFCFontInfo` . Если *ииндекс* не указывает допустимый индекс элемента, возвращается значение null.

##  <a name="m_nfontheight"></a>Кмфктулбарфонткомбобокс:: m_nFontHeight

Задает высоту (в пикселях) символов в поле со списком шрифтов, если поле со списком имеет стиль рисования владельцем.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Примечания

`m_nFontHeight` Если переменная равна 0, то высота вычисляется автоматически в соответствии со шрифтом поля со списком по умолчанию. Высота включает как восхождение символов над базовой линией, так и спуск символов под базовым планом.

##  <a name="setfont"></a>Кмфктулбарфонткомбобокс:: Сетфонт

Выбирает шрифт в поле со списком шрифтов в соответствии с именем и кодировкой шрифта, указанными в параметрах.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
окне Указывает имя или префикс шрифта.

*Тип nChar*<br/>
окне Задает кодировку.

*бексакт*<br/>
окне Указывает, содержит ли *лпсзнаме* имя шрифта или префикс шрифта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если шрифт был выбран успешно. в противном случае — 0.

### <a name="remarks"></a>Примечания

Если *бексакт* имеет значение true, этот метод выбирает шрифт, который точно соответствует имени, указанному как *лпсзнаме*. Если *бексакт* имеет значение false, этот метод выбирает шрифт, который начинается с текста, указанного как *лпсзнаме* , и использует кодировку, указанную в качестве типа данных *nchar*. Если для параметра *nchar* задано значение DEFAULT_CHARSET, набор символов будет проигнорирован и для выбора шрифта будет использоваться только *лпсзнаме* .

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar:: Реплацебуттон](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
