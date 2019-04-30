---
title: Класс CMFCCaptionBar
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: c6385cb6bd3eec3ce5fefe0475d771c774777820
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403845"
---
# <a name="cmfccaptionbar-class"></a>Класс CMFCCaptionBar

Объект `CMFCCaptionBar` объект является панель элементов управления, который может отображать три элемента: кнопка, текстовую метку и растровое изображение. Она может содержать только один элемент каждого типа одновременно. Можно выровнять каждый элемент по левому или правому краю элемента управления или по центру. Также можно применить плоский или трехмерный стиль к верхним и нижним границам заголовка окна.

## <a name="syntax"></a>Синтаксис

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCCaptionBar::Create](#create)|Создает элемент управления панели заголовка и присоединяет его к `CMFCCaptionBar` объекта.|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Указывает, могут ли другой области динамически вставлены между заголовок и его родительского фрейма. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCCaptionBar::EnableButton](#enablebutton)|Включает или отключает кнопку в заголовке окна.|
|[CMFCCaptionBar::GetAlignment](#getalignment)|Возвращает выравнивание указанного элемента.|
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Возвращает размер границы заголовка окна.|
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Возвращает ограничивающий прямоугольник, кнопки в заголовке окна.|
|[CMFCCaptionBar::GetMargin](#getmargin)|Возвращает расстояние между границей заголовка панели элементов и границей элемента управления панели заголовка.|
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Указывает, является ли заголовок в режиме строки сообщения.|
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Удаляет растрового изображения из строки заголовка.|
|[CMFCCaptionBar::RemoveButton](#removebutton)|Удаление кнопки в строке заголовка.|
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Удаление значка из строки заголовка.|
|[CMFCCaptionBar::RemoveText](#removetext)|Удаляет текстовую метку из строки заголовка.|
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Задает растровое изображение для строки заголовка.|
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Задает размер границы заголовка окна.|
|[CMFCCaptionBar::SetButton](#setbutton)|Задает кнопку для строки заголовка.|
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Указывает, является ли кнопка остается нажатой.|
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Задает всплывающую подсказку для кнопки.|
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Задает стиль границы заголовка окна.|
|[CMFCCaptionBar::SetIcon](#seticon)|Задает значок для строки заголовка.|
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Задает всплывающую подсказку для изображения строки заголовка.|
|[CMFCCaptionBar::SetMargin](#setmargin)|Задает расстояние между краем элемент строку заголовка и границей элемента управления панели заголовка.|
|[CMFCCaptionBar::SetText](#settext)|Задает текстовую метку для строки заголовка.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Вызывается платформой для заливки фона заголовка окна.|
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Вызывается платформой для рисования границы заголовка окна.|
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Вызывается платформой для отрисовки кнопки панели заголовка.|
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Вызвано структурой для прорисовки изображения панели заголовка.|
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Вызывается платформой для отрисовки текста строки заголовка.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Цвет фона заголовка окна.|
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Цвет границы заголовка окна.|
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Цвет текста строки заголовка.|

## <a name="remarks"></a>Примечания

Чтобы создать заголовок окна, выполните следующие действия.

1. Создать `CMFCCaptionBar` объекта. Как правило необходимо добавить заголовок в класс окна фрейма.

1. Вызовите [CMFCCaptionBar::Create](#create) метод для создания элемента управления панель заголовка и присоединить его к `CMFCCaptionBar` объекта.

1. Вызовите [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), и [CMFCCaptionBar::SetBitmap](#setbitmap)для задания заголовка панели элементов.

Когда элемент button, необходимо назначить идентификатор команды для кнопки. Когда пользователь нажимает кнопку, заголовок направляет сообщения WM_COMMAND, имеющих этот идентификатор родительского фрейма окна.

Заголовок также может работать в режиме строки сообщения, который эмулирует панели сообщений, которое отображается в приложениях Microsoft Office 2007. В режиме строки сообщения заголовок отображает точечный рисунок, сообщение, а также кнопки (который обычно открывает диалоговое окно.) Точечный рисунок можно назначить всплывающей подсказки.

Чтобы включить режим полосы сообщение, вызовите [CMFCCaptionBar::Create](#create) и четвертый параметр (bIsMessageBarMode) значение TRUE.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCCaptionBar` . В примере показано создание элемента управления панели заголовка, задать трехмерной границы заголовка окна, задайте расстояние в пикселях между краем заголовка панели элементов и границей элемента управления панели заголовка, кнопки для строки заголовка , примените всплывающую подсказку для кнопки, задать текстовую метку для строки заголовка, растровое изображение для строки заголовка и подсказку для изображения в строке заголовка. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcaptionbar.h

##  <a name="create"></a>  CMFCCaptionBar::Create

Создает элемент управления панели заголовка и присоединяет его к `CMFCCaptionBar` объекта.

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Сочетание логического или стили полосы заголовок.

*pParentWnd*<br/>
Родительское окно элемента управления панели заголовка.

*uID*<br/>
Идентификатор элемента управления панели заголовка.

*nHeight*<br/>
Высота в пикселях элемент управления панели заголовка. Если он имеет значение 1, высота рассчитывается в соответствии с высоту значок, текст и кнопки, которая отображает элемент управления панели заголовка.

*bIsMessageBarMode*<br/>
Значение TRUE, если в строке заголовка находится в режиме строки сообщения; Значение FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент управления панели заголовка создан успешно; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

При создании `CMFCCaptionBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызывать `Create` метод, который создает элемент управления Windows и присоединяет его к `CMFCCaptionBar` объекта.

##  <a name="doesallowdyninsertbefore"></a>  CMFCCaptionBar::DoesAllowDynInsertBefore

Указывает, могут ли другой области динамически вставлены между заголовок и его родительского фрейма.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение FALSE, если это не переопределено.

### <a name="remarks"></a>Примечания

##  <a name="enablebutton"></a>  CMFCCaptionBar::EnableButton

Включает или отключает кнопку в заголовке окна.

```
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE, чтобы включить кнопку, FALSE, чтобы отключить кнопку.

##  <a name="getalignment"></a>  CMFCCaptionBar::GetAlignment

Возвращает выравнивание указанного элемента.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Параметры

*Elem*<br/>
[in] Элемент Панель подписи, для которого требуется извлечь выравнивания.

### <a name="return-value"></a>Возвращаемое значение

Выравнивание элемента, например кнопки, растрового изображения, текста или значка.

### <a name="remarks"></a>Примечания

Выравнивание элемента может принимать одно из следующих значений:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="getbordersize"></a>  CMFCCaptionBar::GetBorderSize

Возвращает размер границы заголовка окна.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер в пикселях для границы.

##  <a name="getbuttonrect"></a>  CMFCCaptionBar::GetButtonRect

Возвращает ограничивающий прямоугольник, кнопки в заголовке окна.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CRect` , содержащий координаты ограничивающего прямоугольника кнопки в заголовке окна.

##  <a name="getmargin"></a>  CMFCCaptionBar::GetMargin

Возвращает расстояние между границей заголовка панели элементов и границей элемента управления панели заголовка.

```
int GetMargin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расстояние в пикселях между краем заголовка панели элементов и границей элемента управления панели заголовка.

##  <a name="ismessagebarmode"></a>  CMFCCaptionBar::IsMessageBarMode

Указывает, является ли заголовок в режиме строки сообщения.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в строке заголовка находится в режиме строки сообщения; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

В режиме строки сообщения заголовок отображает изображение с всплывающей подсказки, текст сообщения и кнопки.

##  <a name="m_clrbarbackground"></a>  CMFCCaptionBar::m_clrBarBackground

Цвет фона заголовка окна.

```
COLORREF m_clrBarBackground
```

##  <a name="m_clrbarborder"></a>  CMFCCaptionBar::m_clrBarBorder

Цвет границы заголовка окна.

```
COLORREF m_clrBarBorder
```

##  <a name="m_clrbartext"></a>  CMFCCaptionBar::m_clrBarText

Цвет текста строки заголовка.

```
COLORREF m_clrBarText
```

##  <a name="ondrawbackground"></a>  CMFCCaptionBar::OnDrawBackground

Вызывается платформой для заливки фона заголовка окна.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства заголовка окна.

*rect*<br/>
[in] Ограничивающий прямоугольник для заливки.

### <a name="remarks"></a>Примечания

`OnDrawBackground` Метод вызывается, когда заполнить фон заголовка окна. Реализация по умолчанию заполняет фоновом режиме, используя [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) цвет.

Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид строки заголовка.

##  <a name="ondrawborder"></a>  CMFCCaptionBar::OnDrawBorder

Вызывается платформой для рисования границы заголовка окна.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, который используется для отображения границ.

*rect*<br/>
[in] Ограничивающий прямоугольник.

### <a name="remarks"></a>Примечания

По умолчанию границы со стилем плоскими.

Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид границы строки заголовка.

##  <a name="ondrawbutton"></a>  CMFCCaptionBar::OnDrawButton

Вызывается платформой для отрисовки кнопки панели заголовка.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства, который используется для отображения кнопки.

*rect*<br/>
[in] Ограничивающий прямоугольник кнопки.

*strButton*<br/>
[in] Текстовая подпись кнопки.

*bEnabled*<br/>
[in] Значение TRUE, если кнопка доступна; Значение FALSE в противном случае.

### <a name="remarks"></a>Примечания

Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид кнопки в строке заголовка.

##  <a name="ondrawimage"></a>  CMFCCaptionBar::OnDrawImage

Вызвано структурой для прорисовки изображения панели заголовка.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства, который используется для отображения изображения.

*rect*<br/>
[in] Указывает ограничивающий прямоугольник изображения.

### <a name="remarks"></a>Примечания

Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид изображения.

##  <a name="ondrawtext"></a>  CMFCCaptionBar::OnDrawText

Вызывается платформой для отрисовки текста строки заголовка.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства, который используется для отображения кнопки.

*rect*<br/>
[in] Ограничивающий прямоугольник текста.

*strText*<br/>
[in] Текстовая строка для отображения.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отображается текст с помощью `CDC::DrawText` и [CMFCCaptionBar::m_clrBarText](#m_clrbartext) цвет.

Переопределите этот метод в `CMFCCaptionBar` производного класса, чтобы настроить внешний вид текста в строке заголовка.

##  <a name="removebitmap"></a>  CMFCCaptionBar::RemoveBitmap

Удаляет растрового изображения из строки заголовка.

```
void RemoveBitmap();
```

##  <a name="removebutton"></a>  CMFCCaptionBar::RemoveButton

Удаление кнопки в строке заголовка.

```
void RemoveButton();
```

### <a name="remarks"></a>Примечания

Расположение заголовка панели элементов настраиваются автоматически.

##  <a name="removeicon"></a>  CMFCCaptionBar::RemoveIcon

Удаление значка из строки заголовка.

```
void RemoveIcon();
```

##  <a name="removetext"></a>  CMFCCaptionBar::RemoveText

Удаляет текстовую метку из строки заголовка.

```
void RemoveText();
```

##  <a name="setbitmap"></a>  CMFCCaptionBar::SetBitmap

Задает растровое изображение для строки заголовка.

```
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
[in] Дескриптор к растровому изображению для задания.

*clrTransparent*<br/>
[in] Значение RGB, указывающий прозрачный цвет точечного рисунка.

*bStretch*<br/>
[in] Значение TRUE, если точечный рисунок растягивается в том случае, если он не помещается в образ, ограничивающий прямоугольник. В противном случае растровое изображение не растягивается.

*bmpAlignment*<br/>
[in] Выравнивание растрового изображения.

### <a name="remarks"></a>Примечания

Этот метод позволяет задать точечный рисунок в строке заголовка.

Предыдущий точечного рисунка будет удален автоматически. Если заголовок отображается значок, поскольку вы присвоили [CMFCCaptionBar::SetIcon](#seticon) метод, растровое изображение не будет отображаться, если не удалить значок путем вызова [CMFCCaptionBar::RemoveIcon](#removeicon).

Растровое изображение выравнивается, заданные *bmpAlignment* параметра.  Этот параметр может принимать одно из следующих значений `BarElementAlignment`:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="setbordersize"></a>  CMFCCaptionBar::SetBorderSize

Задает размер границы заголовка окна.

```
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Параметры

*nSize*<br/>
[in] Новый размер в точках границы панели заголовка.

##  <a name="setbutton"></a>  CMFCCaptionBar::SetButton

Задает кнопку для строки заголовка.

```
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
Команда надпись на этой кнопке.

*uiCmdUI*<br/>
Идентификатор кнопки команды.

*btnAlignmnet*<br/>
Выравнивание кнопки.

*bHasDropDownArrow*<br/>
Значение TRUE, если кнопка отображает стрелку раскрывающегося списка, и FALSE в противном случае.

##  <a name="setbuttonpressed"></a>  CMFCCaptionBar::SetButtonPressed

Указывает, является ли кнопка остается нажатой.

```
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Параметры

*bPresed*<br/>
Значение TRUE, если кнопки сохраняет в нажатом состоянии, значение FALSE в противном случае.

##  <a name="setbuttontooltip"></a>  CMFCCaptionBar::SetButtonToolTip

Задает всплывающую подсказку для кнопки.

```
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Параметры

*lpszToolTip*<br/>
[in] Заголовок подсказки.

*lpszDescription*<br/>
[in] Описание подсказки.

##  <a name="setflatborder"></a>  CMFCCaptionBar::SetFlatBorder

Задает стиль границы заголовка окна.

```
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Параметры

*bFlat*<br/>
[in] Значение TRUE, если граница заголовка является плоской. Значение FALSE, если граница является 3D.

##  <a name="seticon"></a>  CMFCCaptionBar::SetIcon

Задает значок для строки заголовка.

```
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*hIcon*<br/>
[in] Дескриптор значка для задания.

*iconAlignment*<br/>
[in] Выравнивание значка.

### <a name="remarks"></a>Примечания

Заголовки отображаются значки или растровые изображения. См. в разделе [CMFCCaptionBar::SetBitmap](#setbitmap) чтобы узнать, как отобразить точечный рисунок. Если задать значок и растровое изображение, значок отображается всегда. Вызовите [CMFCCaptionBar::RemoveIcon](#removeicon) Удаление значка из строки заголовка.

Значок, выровненный по *iconAlignment* параметра. Он может иметь одно из следующих `BarElementAlignment` значения:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="setimagetooltip"></a>  CMFCCaptionBar::SetImageToolTip

Задает подсказку для изображения в строке заголовка.

```
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Параметры

*lpszToolTip*<br/>
[in] Текст всплывающей подсказки.

*lpszDescription*<br/>
[in] Описание подсказки.

##  <a name="setmargin"></a>  CMFCCaptionBar::SetMargin

Задает расстояние между краем элемент строку заголовка и границей элемента управления панели заголовка.

```
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Параметры

*nMargin*<br/>
[in] Расстояние в пикселях между краем заголовка панели элементов и границей элемента управления панели заголовка.

##  <a name="settext"></a>  CMFCCaptionBar::SetText

Задает текстовую метку для строки заголовка.

```
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Параметры

*strText*<br/>
[in] Текстовая строка для установки.

*textAlignment*<br/>
[in] Выравнивание текста.

### <a name="remarks"></a>Примечания

Текстовая подпись выравнивается, заданные *textAlignment* параметра. Он может иметь одно из следующих `BarElementAlignment` значения:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
