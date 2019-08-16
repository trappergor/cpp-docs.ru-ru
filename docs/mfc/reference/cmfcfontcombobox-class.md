---
title: Класс CMFCFontComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: 69e8f81e7e01d0610f3cbf88ac1725a21d59838f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505301"
---
# <a name="cmfcfontcombobox-class"></a>Класс CMFCFontComboBox

`CMFCFontComboBox` Класс создает элемент управления "поле со списком", содержащий список шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCFontComboBox:: CMFCFontComboBox](#cmfcfontcombobox)|Создает объект `CMFCFontComboBox`.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Вызывается платформой для определения относительного положения нового элемента в поле упорядоченного списка элемента управления поля со списком текущего шрифта. (Переопределяет [CComboBox:: компареитем](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Вызывается платформой для рисования указанного элемента в элементе управления поля со списком текущего шрифта. (Переопределяет [CComboBox::D равитем](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Извлекает сведения о выбранном в данный момент шрифте.|
|`CMFCFontComboBox::MeasureItem`|Вызывается платформой для информирования окон по измерениям списка в элементе управления поля со списком текущего шрифта. (Переопределяет [CComboBox:: меасуреитем](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox:: Селектфонт](#selectfont)|Выбирает шрифт, соответствующий указанным критериям, из поля со списком шрифт.|
|[CMFCFontComboBox:: Setup](#setup)|Инициализирует список элементов в поле со списком шрифтов.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCFontComboBox:: m_bDrawUsingFont](#m_bdrawusingfont)|Указывает платформе, какой шрифт используется для рисования меток элементов в поле со списком текущего шрифта.|

## <a name="remarks"></a>Примечания

Чтобы использовать `CMFCFontComboBox` объект в диалоговом окне, `CMFCFontComboBox` добавьте переменную в класс диалогового окна. Затем в `OnInitDialog` методе класса диалогового окна вызовите метод [CMFCFontComboBox:: Setup](#setup) , чтобы инициализировать список элементов в элементе управления "поле со списком".

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксфонткомбобокс. h

##  <a name="cmfcfontcombobox"></a>CMFCFontComboBox:: CMFCFontComboBox

Создает объект `CMFCFontComboBox`.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

Извлекает сведения о выбранном в данный момент шрифте.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [класса кмфкфонтинфо](../../mfc/reference/cmfcfontinfo-class.md) , описывающий шрифт. Может иметь значение NULL, если в поле со списком не выбран шрифт.

### <a name="remarks"></a>Примечания

##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox:: m_bDrawUsingFont

Указывает платформе, какой шрифт используется для рисования меток элементов в поле со списком текущего шрифта.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Примечания

Присвойте этому элементу значение TRUE, чтобы платформа использовала тот же шрифт для рисования каждой метки элемента. Присвойте этому элементу значение FALSE, чтобы задать для платформы отрисовку каждой метки элемента с использованием шрифта, имя которого совпадает с именем метки. По умолчанию этот член имеет значение FALSE.

##  <a name="selectfont"></a>CMFCFontComboBox:: Селектфонт

Выбирает шрифт, соответствующий указанным критериям, из поля со списком шрифт.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Параметры

*пдеск*<br/>
окне Указывает на объект описания шрифта.

*лпсзнаме*<br/>
окне Задает имя шрифта.

*Тип nChar*<br/>
окне Задает кодировку. Значение по умолчанию — DEFAULT_CHARSET. Дополнительные сведения см. в `lfCharSet` описании члена структуры [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент в поле со списком шрифтов соответствует указанному объекту описания шрифта или имени шрифта и набору символов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для выбора и прокрутки элемента в поле со списком шрифтов, соответствующего указанному шрифту.

### <a name="example"></a>Пример

В следующем примере показано, `SelectFont` как использовать метод `CMFCFontComboBox` в классе. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>CMFCFontComboBox:: Setup

Инициализирует список элементов в поле со списком шрифтов.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Параметры

*нфонттипе*<br/>
окне Указывает тип шрифта. Значение по умолчанию — это побитовое сочетание (или) DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.

*Тип nChar*<br/>
окне Указывает набор символов шрифта. Значение по умолчанию — DEFAULT_CHARSET.

*нпитчандфамили*<br/>
окне Задает шаг и семейство шрифтов. Значение по умолчанию — DEFAULT_PITCH.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если поле со списком шрифтов было успешно инициализировано. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод инициализирует поле со списком шрифтов, перечисляя установленные шрифты, которые соответствуют указанным параметрам, и вставляя эти имена шрифтов в поле со списком шрифтов.

### <a name="example"></a>Пример

В следующем примере показано, `Setup` как использовать метод `CMFCFontComboBox` в классе. Этот пример является частью [примера новых элементов управления](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)
