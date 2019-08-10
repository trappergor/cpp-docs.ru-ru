---
title: Класс Кмфкриббонлинкктрл
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: 12a83e45176f7fc6020da1f0d0ee5923ef0f466c
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866173"
---
# <a name="cmfcribbonlinkctrl-class"></a>Класс Кмфкриббонлинкктрл

Реализует гиперссылку, которая расположена на ленте. Гиперссылка при щелчке открывает веб-страницу.
Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкриббонлинкктрл:: Кмфкриббонлинкктрл](#cmfcribbonlinkctrl)|Создает и инициализирует объект `CMFCRibbonLinkCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкриббонлинкктрл:: CopyFrom](#copyfrom)|(Переопределяет `CMFCRibbonButton::CopyFrom`.)|
|[Кмфкриббонлинкктрл:: Жеткомпактсизе](#getcompactsize)|(Переопределяет [CMFCRibbonButton:: жеткомпактсизе](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[Кмфкриббонлинкктрл::.](#getlink)|Возвращает значение гиперссылки.|
|[Кмфкриббонлинкктрл:: Жетрегуларсизе](#getregularsize)|(Переопределяет [CMFCRibbonButton:: жетрегуларсизе](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[Кмфкриббонлинкктрл:: Жеттултиптекст](#gettooltiptext)|(Переопределяет [CMFCRibbonButton:: жеттултиптекст](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext).)|
|[Кмфкриббонлинкктрл:: Исдравтултипимаже](#isdrawtooltipimage)|(Переопределяет `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[Кмфкриббонлинкктрл:: OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[Кмфкриббонлинкктрл:: Ондравменуимаже](#ondrawmenuimage)|(Переопределяет [метод CMFCRibbonBaseElement:: ондравменуимаже](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[Кмфкриббонлинкктрл:: OnMouseMove](#onmousemove)|(Переопределяет `CMFCRibbonButton::OnMouseMove`.)|
|[Кмфкриббонлинкктрл:: Онсетикон](#onseticon)||
|[Кмфкриббонлинкктрл:: Опенлинк](#openlink)|Открывает веб-страницу, указанную в гиперссылке.|
|[Кмфкриббонлинкктрл:: Сетлинк](#setlink)|Задает значение гиперссылки.|

## <a name="remarks"></a>Примечания

После создания гиперссылки добавьте ее на панель, вызвав [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[Метод CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Кмфкриббонлинкктрл](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксриббонлинкктрл. h

##  <a name="cmfcribbonlinkctrl"></a>Кмфкриббонлинкктрл:: Кмфкриббонлинкктрл

Создает и инициализирует объект [кмфкриббонлинкктрл](../../mfc/reference/cmfcribbonlinkctrl-class.md) .

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
окне Указывает идентификатор команды, которая выполняется при нажатии на элемент управления Link.

*lpszText*<br/>
окне Задает метку, отображаемую на элементе управления ссылки.

*лпсзлинк*<br/>
окне Задает гиперссылку, связанную с элементом управления "ссылка".

### <a name="example"></a>Пример

В следующем примере показано, как использовать конструктор `CMFCRibbonLinkCtrl` класса. Этот фрагмент кода является частью [примера мини-приложений ленты](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

##  <a name="copyfrom"></a>Кмфкриббонлинкктрл:: CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Параметры

окне *src*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getcompactsize"></a>Кмфкриббонлинкктрл:: Жеткомпактсизе

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

окне *основной контроллер домена*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getlink"></a>Кмфкриббонлинкктрл::.

Возвращает значение гиперссылки.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение гиперссылки.

### <a name="remarks"></a>Примечания

##  <a name="getregularsize"></a>Кмфкриббонлинкктрл:: Жетрегуларсизе

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

окне *основной контроллер домена*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="gettooltiptext"></a>Кмфкриббонлинкктрл:: Жеттултиптекст

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondrawmenuimage"></a>Кмфкриббонлинкктрл:: Ондравменуимаже

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Параметры

окне *CDC&#42;*<br/>
окне *Крект*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isdrawtooltipimage"></a>Кмфкриббонлинкктрл:: Исдравтултипимаже

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondraw"></a>Кмфкриббонлинкктрл:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

окне *основной контроллер домена*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onmousemove"></a>Кмфкриббонлинкктрл:: OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Параметры

окне *точка*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onseticon"></a>Кмфкриббонлинкктрл:: Онсетикон

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>Примечания

##  <a name="openlink"></a>Кмфкриббонлинкктрл:: Опенлинк

Открывает веб-страницу, указанную в гиперссылке.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если связанная веб-страница успешно открыта. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Открывает веб-страницу, используя гиперссылку, связанную с `CMFCRibbonLinkCtrl` объектом.

##  <a name="setlink"></a>Кмфкриббонлинкктрл:: Сетлинк

Задает значение гиперссылки.

```
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>Параметры

*лпсзлинк*<br/>
окне Задает текст гиперссылки.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
