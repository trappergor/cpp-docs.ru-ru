---
title: Класс Кмфкриббонфонткомбобокс
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: 186c4bc3e1b26529ed0e000d2893e1b2d81c4304
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504955"
---
# <a name="cmfcribbonfontcombobox-class"></a>Класс Кмфкриббонфонткомбобокс

Реализует поле со списком, содержащее список шрифтов. Необходимо задать поле со списком на панели ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Деструктор.|

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкриббонфонткомбобокс:: Кмфкриббонфонткомбобокс](#cmfcribbonfontcombobox)|Создает и инициализирует объект `CMFCRibbonFontComboBox`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкриббонфонткомбобокс:: Буилдфонтс](#buildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|
|`CMFCRibbonFontComboBox::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[Кмфкриббонфонткомбобокс:: charset](#getcharset)|Возвращает указанный набор символов.|
|[Кмфкриббонфонткомбобокс:: Жетфонтдеск](#getfontdesc)||
|[Кмфкриббонфонткомбобокс:: Жетфонттипе](#getfonttype)|Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.|
|[Кмфкриббонфонткомбобокс:: Жетпитчандфамили](#getpitchandfamily)|Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.|
|`CMFCRibbonFontComboBox::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкриббонфонткомбобокс:: Ребуилдфонтс](#rebuildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких ранее заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|
|[Кмфкриббонфонткомбобокс:: Сетфонт](#setfont)|Выбирает указанный шрифт в поле со списком.|

## <a name="remarks"></a>Примечания

После создания `CMFCRibbonFontComboBox` объекта добавьте его на панель ленты, вызвав [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[кмфкриббонедит](../../mfc/reference/cmfcribbonedit-class.md)

[кмфкриббонкомбобокс](../../mfc/reference/cmfcribboncombobox-class.md)

[кмфкриббонфонткомбобокс](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксриббонкомбобокс. h

##  <a name="buildfonts"></a>Кмфкриббонфонткомбобокс:: Буилдфонтс

Заполняет поле со списком на ленте с помощью шрифтов.

```
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Параметры

*нфонттипе*<br/>
окне Указывает тип шрифта для добавляемых шрифтов.

*Тип nChar*<br/>
окне Задает набор символов добавляемых шрифтов.

*нпитчандфамили*<br/>
окне Задает шаг и семейство шрифтов для добавления.

##  <a name="cmfcribbonfontcombobox"></a>Кмфкриббонфонткомбобокс:: Кмфкриббонфонткомбобокс

Создает и инициализирует объект [кмфкриббонфонткомбобокс](../../mfc/reference/cmfcribbonfontcombobox-class.md) .

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
окне Идентификатор команды, которая выполняется, когда пользователь выбирает элемент из поля со списком.

*нфонттипе*<br/>
окне Указывает, какие типы шрифтов должны отображаться в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.

*Тип nChar*<br/>
окне Фильтрует шрифты в поле со списком, чтобы они принадлежали к указанной кодировке.

*нпитчандфамили*<br/>
окне Задает шаг и семейство шрифтов, отображаемых в поле со списком.

*нвидс*<br/>
окне Задает ширину (в пикселях) поля со списком.

### <a name="remarks"></a>Примечания

Дополнительные сведения о возможных значениях параметров *нфонттипе* см. в разделе [енумфонтфампрок](/previous-versions/dd162621\(v=vs.85\)) в документации по Windows SDK.

Дополнительные сведения о допустимых кодировках, которые можно присвоить параметру *nchar*, а также допустимые значения, которые могут быть назначены *нпитчандфамили*, см. в разделе [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) в документации по Windows SDK.

##  <a name="getfontdesc"></a>Кмфкриббонфонткомбобокс:: Жетфонтдеск

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Параметры

окне *ииндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="rebuildfonts"></a>Кмфкриббонфонткомбобокс:: Ребуилдфонтс

Заполняет поле со списком на ленте шрифтами ранее указанного типа шрифта, набора символов и числа и семейства.

```
void RebuildFonts();
```

### <a name="remarks"></a>Примечания

Можно указать тип шрифта, набор символов и высоту и семейство шрифтов для включения в поле со списком шрифтов ленты в [конструкторе](#cmfcribbonfontcombobox) для этого класса или путем вызова [Кмфкриббонфонткомбобокс:: буилдфонтс](#buildfonts).

##  <a name="setfont"></a>Кмфкриббонфонткомбобокс:: Сетфонт

Выбирает указанный шрифт в поле со списком.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Параметры

' Лпсзнаме * задает имя выбранного шрифта.

*Тип nChar*<br/>
Задает кодировку для выбранного шрифта.

*бексакт*<br/>
Значение TRUE, чтобы указать, что кодировка должна совпадать при выборе шрифта; Значение FALSE, чтобы указать, что кодировка может игнорироваться при выборе шрифта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанный шрифт найден и выбран. в противном случае — нуль.

### <a name="remarks"></a>Примечания

##  <a name="getcharset"></a>Кмфкриббонфонткомбобокс:: charset

Возвращает указанный набор символов.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Возвращаемое значение

Кодировка (см. раздел LOGFONT в документации по Windows SDK).

### <a name="remarks"></a>Примечания

##  <a name="getfonttype"></a>Кмфкриббонфонткомбобокс:: Жетфонттипе

Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.

```
int GetFontType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Типы шрифтов (см. раздел Енумфонтфампрок в документации по Windows SDK).

### <a name="remarks"></a>Примечания

##  <a name="getpitchandfamily"></a>Кмфкриббонфонткомбобокс:: Жетпитчандфамили

Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Возвращаемое значение

Шаг и семейство (см. раздел LOGFONT в документации по Windows SDK).

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)
