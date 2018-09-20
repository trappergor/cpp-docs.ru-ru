---
title: Класс CMFCRibbonStatusBarPane | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d0cd2be2e07cc59041634a0c9f7ed2fc2c2e47d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412851"
---
# <a name="cmfcribbonstatusbarpane-class"></a>Класс CMFCRibbonStatusBarPane

`CMFCRibbonStatusBarPane` Класс реализует элемент ленты, который можно добавить в строку состояния ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Создает и инициализирует объект `CMFCRibbonStatusBarPane`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Возвращает строку, определяющую самая длинная текстовая строка, который может быть отображен в области без усечения.|
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Возвращает текущее значение параметра Выравнивание текста.|
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Определяет, является ли анимация выполняется.|
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Определяет, находится ли область в расширенной области строки состояния ленты.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Переопределяет [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Переопределяет [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Определяет самая длинная текстовая строка, который может быть отображен в области без усечения.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Назначает области списка изображений, который может использоваться для анимации.|
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Задает выравнивание текста.|
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Запускает анимацию, присвоенный области.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Останавливает анимацию, которая назначается на панель. .|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Вызывается платформой при остановке анимации, присвоенный области.|

## <a name="example"></a>Пример

В следующем примере демонстрируется использование различных методов класса `CMFCRibbonStatusBarPane`. В примере показано `CMFCRibbonStatusBarPane` объекта, задать выравнивание текста метки элемента панели строки состояния, определения длинного текста, который может отображаться в панели строки состояния без усечения, подключения к панели строки состояния, можно использовать для списка изображений Анимация и начала анимации.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonstatusbarpane.h

##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Создайте объект панели в строке состояния.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
[in] Указывает идентификатор команды панели.

*lpszText*<br/>
[in] Задает текстовую строку для отображения на панели.

*bIsStatic*<br/>
[in] Значение TRUE, если панель состояния не может быть выделены или выбрать, щелкнув его.

*hIcon*<br/>
[in] Указывает дескриптор для значка для отображения в области.

*lpszAlmostLargeText*<br/>
[in] Указывает самая длинная текстовая строка, который может быть отображен на область.

*hBmpAnimationList*<br/>
[in] Указывает дескриптор к списку изображений, который используется для анимации.

*cxAnimation*<br/>
[in] Ширина в пикселях значка в списке изображений, который используется для анимации.

*clrTrnsp*<br/>
[in] Указывает прозрачный цвет изображения в списке изображений, которые используются для анимации.

*uiAnimationListResID*<br/>
[in] Указывает идентификатор ресурса из списка изображений, который используется для анимации.

##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText

Получает самая длинная текстовую строку, которая может отображать панель строки состояния.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Возвращаемое значение

Самая длинная текстовая строка, которая может отображать панель строки состояния.

##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign

Возвращает текущее значение параметра Выравнивание текста метки элемента панели строки состояния.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее выравнивание текста может принимать одно из следующих:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation

Определяет, является ли анимация выполняется.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если анимация выполняется; Значение FALSE в противном случае.

##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended

Определите, находится ли область в расширенной области строки состояния ленты.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в расширенной области в строке состояния области. Значение FALSE в противном случае.

##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Параметры

[in] *CDC**

### <a name="remarks"></a>Примечания

##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation

Этот метод вызывается платформой при завершении анимации, присвоенный области.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Примечания

`StopAnimation` вызовы методов `OnFinishAnimation` метод, который можно использовать для очистки данных при завершении анимации.

##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText

Определите самую длинную строку текста, который может быть отображен в панели строки состояния без усечения.

```
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Параметры

*lpszAlmostLargeText*<br/>
[in] Указывает максимальной длины, которые могут отображаться на панели строки состояния без усечения.

### <a name="remarks"></a>Примечания

Библиотека вычисляет размер текста, *lpszAlmostLargeText* указывает и соответствующим образом изменяет размер панели. Текст усекается, если он по-прежнему не умещается в области.

##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList

Присоединяет панели строки состояния списка изображений, который может использоваться для анимации.

```
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>Параметры

*hBmpAnimationList*<br/>
[in] Указывает дескриптор к списку изображений.

*cxAnimation*<br/>
[in] Задает ширину в пикселях кадра, в списке изображений.

*clrTransp*<br/>
[in] Указывает прозрачный цвет из списка изображений.

*uiAnimationListResID*<br/>
[in] Указывает идентификатор ресурса для списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если список изображений успешно подключен к панель строки состояния; Значение FALSE в противном случае.

##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign

Задает выравнивание текста метки элемента панели строки состояния.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Параметры

*nAlign*<br/>
[in] Задает выравнивание текста.

### <a name="remarks"></a>Примечания

*nAlign* может иметь одно из следующих значений:

- TA_LEFT: выравнивание по левому краю

- TA_CENTER: выравнивание по центру

- TA_RIGHT: выравнивание по правому краю

##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation

Запускает анимацию, назначаемый области.

```
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Параметры

*nFrameDelay*<br/>
[in] Указывает частоту кадров анимации, в миллисекундах.

*nDuration*<br/>
[in] Задает промежуток времени для воспроизведения анимации, в миллисекундах. Используйте значение -1 для бесконечный цикл.

### <a name="remarks"></a>Примечания

Необходимо указать дескриптор списка изображений, перед вызовом метода `StartAnimation` с помощью `SetAnimationList`.

##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation

Останавливает анимацию, которое было назначено панель строки состояния.

```
void StopAnimation();
```

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Класс CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)
