---
title: Класс CMFCFontComboBox | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8583e7efe46ba5bae2b55e6f8cb5bdad7c7385b8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071944"
---
# <a name="cmfcfontcombobox-class"></a>Класс CMFCFontComboBox

`CMFCFontComboBox` Класс создает поле со списком, содержащее список шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Создает объект `CMFCFontComboBox`.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Вызывается платформой для определения относительной позиции нового элемента в отсортированном списке текущего элемента управления поля со списком шрифтов. (Переопределяет [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Вызывается платформой для рисования заданного элемента в элементе управления текущего поля со списком шрифта. (Переопределяет [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Извлекает сведения о выбранный шрифт.|
|`CMFCFontComboBox::MeasureItem`|Вызывается платформой для информирования Windows из измерений в списке в текущий шрифт поле со списком. (Переопределяет [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Выбирает шрифт, который соответствует заданному условию, из поля со списком шрифта.|
|[CMFCFontComboBox::Setup](#setup)|Инициализирует список элементов в поле со списком шрифта.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Указывает платформу какой шрифт, используемый для рисования метки элемента в поле со списком текущего шрифта.|

## <a name="remarks"></a>Примечания

Чтобы использовать `CMFCFontComboBox` в диалоговом окне, добавьте `CMFCFontComboBox` переменной класса диалогового окна. Затем в `OnInitDialog` метод класса диалогового окна, вызов [CMFCFontComboBox::Setup](#setup) метод для инициализации списка элементов в элементе управления поля со списком.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxfontcombobox.h

##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox

Создает объект `CMFCFontComboBox`.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

Извлекает сведения о выбранный шрифт.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md) , описывающий шрифта. Он может иметь значение NULL, если не выбран в поле со списком.

### <a name="remarks"></a>Примечания

##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont

Указывает платформу какой шрифт, используемый для рисования метки элемента в поле со списком текущего шрифта.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Примечания

Значение TRUE для направления средой используется тот же шрифт для рисования каждой подписи этого элемента. Значение FALSE для направления структурой для прорисовки каждой подписи с помощью шрифта, имя которого совпадает с метки этого элемента. По умолчанию значение этого члена равно FALSE.

##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont

Выбирает шрифт, который соответствует заданному условию, из поля со списком шрифта.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Параметры

*параметре pDesc*<br/>
[in] Указывает объект описания шрифта.

*lpszName*<br/>
[in] Задает имя шрифта.

*nCharSet*<br/>
[in] Задает набор символов. Значение по умолчанию — DEFAULT_CHARSET. Дополнительные сведения см. в разделе `lfCharSet` членом [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) структуры.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент в поле со списком шрифтов на соответствующий объект описания указанного шрифта или имя шрифта и charset; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод можно используйте для выбора и прокрутку до элемента в поле со списком шрифтов, соответствующий заданного шрифта.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `SelectFont` метод в `CMFCFontComboBox` класса. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>  CMFCFontComboBox::Setup

Инициализирует список элементов в поле со списком шрифта.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Параметры

*nFontType*<br/>
[in] Указывает тип шрифта. Значение по умолчанию — битовую комбинацию (OR) флагов значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.

*nCharSet*<br/>
[in] Указывает кодировку шрифта. Значение по умолчанию — DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
[in] Указывает шрифт шаг и семейство. Значение по умолчанию — DEFAULT_PITCH.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если поле со списком шрифта был инициализирован успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод инициализирует поле со списком шрифтов, перечисление установленных шрифтов, соответствующих заданным параметрам и вставки этих имен шрифтов в поле со списком шрифта.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `Setup` метод в `CMFCFontComboBox` класса. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)
