---
title: Класс CMFCCaptionButton
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 2020f6cb2f0feec28996f69791899c648600b600
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301055"
---
# <a name="cmfccaptionbutton-class"></a>Класс CMFCCaptionButton

`CMFCCaptionButton` Класс реализует кнопку, которая отображается в заголовке окна для закрепляемой области или окна области. Как правило, платформа создает кнопки заголовка автоматически.

## <a name="syntax"></a>Синтаксис

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|name|Описание:|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Создает объект CMFCCaptionButton.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|Возвращает команду, представленный кнопки.|
|[CMFCCaptionButton::GetIconID](#geticonid)|Возвращает идентификатор образа, связанный с кнопкой.|
|[CMFCCaptionButton::GetRect](#getrect)|Возвращает прямоугольник, занимаемый кнопки.|
|[CMFCCaptionButton::GetSize](#getsize)|Возвращает ширину и высоту кнопки.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Указывает, задано ли для мини-размер высоте строки заголовка.|
|[CMFCCaptionButton::Move](#move)|Задает место рисования кнопки и Показать состояние окна.|
|[CMFCCaptionButton::OnDraw](#ondraw)|Рисует кнопки заголовка.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Задает размер мини-заголовке.|

## <a name="remarks"></a>Примечания

Можно наследовать класс от [класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) и использовать защищенный метод `AddButton`для добавления в заголовке мини-рамки окна.

CPaneFrameWnd.h определяет идентификаторы команд для двух типов в заголовке:

- AFX_CAPTION_BTN_PIN отображает кнопку ПИН-код при закрепляемой области поддерживает режим автоматического скрытия.

- AFX_CAPTION_BTN_CLOSE, который отображает **закрыть** кнопку, может быть закрыто или скрыта область.

## <a name="example"></a>Пример

В следующем примере демонстрируется создание `CMFCCaptionButton` и задайте размер мини-заголовке.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcaptionbutton.h

##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton

Создает объект `CMFCCaptionButton`.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*nHit*<br/>
[in] Команда, связанная с кнопкой.

*bLeftAlign*<br/>
[in] Указывает, выравнивается ли кнопка слева.

В следующей таблице перечислены возможные значения для *nHit* параметра.

|Значение|Команда|
|-----------|-------------|
|AFX_HTCLOSE|Кнопка "Закрыть".|
|HTMINBUTTON|Кнопка свертывания.|
|HTMAXBUTTON|Кнопка развертывания окна.|
|AFX_HTLEFTBUTTON|Кнопка со стрелкой влево.|
|AFX_HTRIGHTBUTTON|Кнопка со стрелкой вправо.|
|AFX_HTMENU|Вниз стрелку кнопки меню.|
|HTNOWHERE|Значение по умолчанию; представляет ни одной команды.|

### <a name="remarks"></a>Примечания

По умолчанию в заголовке не связан с командой.

В заголовке выравниваются, либо на вправо или влево.

##  <a name="gethit"></a>  CMFCCaptionButton::GetHit

Возвращает команду, представленный кнопки.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Возвращаемое значение

Команда, представленный кнопки.

В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Команда|
|-----------|-------------|
|AFX_HTCLOSE|Кнопка "Закрыть".|
|HTMINBUTTON|Кнопка свертывания.|
|HTMAXBUTTON|Кнопка развертывания окна.|
|AFX_HTLEFTBUTTON|Кнопка со стрелкой влево.|
|AFX_HTRIGHTBUTTON|Кнопка со стрелкой вправо.|
|AFX_HTMENU|Вниз стрелку кнопки меню.|
|HTNOWHERE|Значение по умолчанию; представляет ни одной команды.|

##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID

Возвращает идентификатор образа, связанный с кнопкой.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Параметры

*bHorz*<br/>
[in] Значение TRUE для образа стрелку влево или вправо идентификаторы; Значение FALSE для вверх или вниз изображение стрелки идентификаторы.

*bMaximized*<br/>
[in] Значение TRUE, если для идентификатора развертывания образа; Значение FALSE для идентификатора свернуть образа.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор образа.

### <a name="remarks"></a>Примечания

Параметры укажите идентификаторы изображения для свернуть или развернуть в заголовке.

##  <a name="getrect"></a>  CMFCCaptionButton::GetRect

Возвращает прямоугольник, занимаемый кнопки.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, представляющий расположение кнопки.

### <a name="remarks"></a>Примечания

Если кнопка не видна, возвращаемый размер равен 0.

##  <a name="getsize"></a>  CMFCCaptionButton::GetSize

Возвращает ширину и высоту кнопки.

```
static CSize GetSize();
```

### <a name="return-value"></a>Возвращаемое значение

Внешние размеры кнопки.

### <a name="remarks"></a>Примечания

Возвращаемый размер включает кнопки поля и границы.

##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton

Указывает, задано ли для мини-размер высоте строки заголовка.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если заголовок мини-размер. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="move"></a>  CMFCCaptionButton::Move

Задает место рисования кнопки и Показать состояние окна.

```
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*ptTo*<br/>
[in] Новое расположение.

*bHide*<br/>
[in] Необходимость отображения кнопки.

##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw

Рисует кнопки заголовка.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства для кнопки.

*bActive*<br/>
[in] Следует ли рисовать изображения active кнопки.

*bHorz*<br/>
[in] Зарезервировано для использования в производном классе.

*bMaximized*<br/>
[in] Следует ли рисовать изображение кнопки в развернутом состоянии.

*bDisabled*<br/>
[in] Следует ли рисовать включена кнопка изображения.

### <a name="remarks"></a>Примечания

*BMaximized* параметр используется, когда кнопка находится развернуть или свернуть.

##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton

Задает размер мини-заголовке.

```
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
[in] Значение TRUE для высоты мини-заголовок панели; Значение FALSE означает, что для высоты панели заголовка по умолчанию.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
