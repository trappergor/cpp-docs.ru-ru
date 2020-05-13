---
title: Класс CMFCRibbonSeparator
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: 41a958c78719f6aedf1cc02f8e3ff5a2dbbf0e1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368847"
---
# <a name="cmfcribbonseparator-class"></a>Класс CMFCRibbonSeparator

Реализует ленточный сепаратор.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonСепаратор:CMFCRibbonСепаратор](#cmfcribbonseparator)|Формирует объект `CMFCRibbonSeparator`.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonСепаратор:AddToListBox](#addtolistbox)|Добавляет сепаратор в список команд в поле **настраиваемых** **диалогов.** (Переопределяет [CMFCRibbonbaseElement:AddtolistBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonSeparator::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|

### <a name="protected-methods"></a>Защищенные методы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonСепаратор::CopyFrom](#copyfrom)|Метод копирования, который устанавливает переменные члена сепаратора от другого объекта.|
|[CMFCRibbonСепаратор::GetRegularSize](#getregularsize)|Возвращает размер сепаратора.|
|[CMFCRibbonСепаратор::Исепаратор](#isseparator)|Указывает, является ли это сепаратором.|
|[CMFCRibbonСепаратор::IsTabStop](#istabstop)|Указывает, является ли это остановкой вкладок.|
|[CMFCRibbonСепаратор:OnDraw](#ondraw)|Вызывается системой, чтобы нарисовать сепаратор либо на ленте или панели быстрого доступа.|
|[CMFCRibbonСепаратор:OnDrawOnList](#ondrawonlist)|Вызывается системой, чтобы нарисовать сепаратор в списке **команд.**|

## <a name="remarks"></a>Remarks

Ленточный сепаратор представляет собой вертикальную или горизонтальную линию, которая логически отделяет элементы ленты. Сепаратор можно нарисовать на элементе управления лентой, главном меню приложения, ленте и панели инструментов быстрого доступа.

Чтобы использовать сепаратор в приложении, постройте новый объект и добавьте его в основное меню приложения, как показано здесь:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

Позвоните [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) добавить сепараторы к ленточным панелям. Сепараторы распределяются и добавляются `AddSeparator` внутри методом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonСепаратор](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonСепаратор:AddToListBox

Добавляет сепаратор в список команд в поле **настраиваемых** **диалогов.**

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Параметры

*pWndListBox*<br/>
(в) Указатель на список **команд,** где добавляется сепаратор.

*bDeep*<br/>
(в) Игнорировать.

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс строки в поле списка, указанном *pWndListBox*.

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFCRibbonСепаратор:CMFCRibbonСепаратор

Формирует объект `CMFCRibbonSeparator`.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Параметры

*bIsHoriz*<br/>
(в) Если правда, сепаратор горизонтальный; если FALSE, сепаратор вертикальный.

### <a name="remarks"></a>Remarks

Горизонтальные сепараторы используются в меню приложений. Вертикальные сепараторы используются в панели инструментов.

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCRibbonSeparator` построить объект класса.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonСепаратор::CopyFrom

Метод копирования, который устанавливает переменные члена сепаратора от другого объекта.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Параметры

*Src*<br/>
(в) Элемент исходной ленты для копирования.

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonСепаратор::GetRegularSize

Возвращает размер сепаратора.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на содержимое устройства.

### <a name="return-value"></a>Возвращаемое значение

Размер сепаратора на данном контексте устройства.

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFCRibbonСепаратор::Исепаратор

Указывает, является ли это сепаратором.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда правда для этого класса.

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFCRibbonСепаратор::IsTabStop

Указывает, является ли это остановкой вкладок.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда FALSE для этого класса.

### <a name="remarks"></a>Remarks

Ленточный сепаратор не является остановкой вкладок.

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCRibbonСепаратор:OnDraw

Вызывается системой, чтобы нарисовать сепаратор либо на ленте или панели быстрого доступа.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonСепаратор:OnDrawOnList

Вызывается системой, чтобы нарисовать сепаратор в списке **команд.**

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDC*|(в) Указатель на контекст устройства.|
|*strText*|(в) Текст отображается в списке.|
|*nTextOffset*|(в) Расстояние между текстом и левой стороной ограничивающего прямоугольника.|
|*rect*|(в) Определяет прямоугольник.|
|*bIsSelected*|(в) Игнорировать.|
|*bНазалион*|(в) Игнорировать.|

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
