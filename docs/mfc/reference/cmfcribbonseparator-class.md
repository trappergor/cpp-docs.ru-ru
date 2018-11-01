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
ms.openlocfilehash: 05ac8b26cb6b6e7d8e622ecbaac1d4a81bfd35e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565936"
---
# <a name="cmfcribbonseparator-class"></a>Класс CMFCRibbonSeparator

Реализует разделителя ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Создает объект `CMFCRibbonSeparator`.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Добавляет разделитель для **команды** в списке **Настройка** диалоговое окно. (Переопределяет [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonSeparator::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|

### <a name="protected-methods"></a>Защищенные методы

|||
|-|-|
|Имя|Описание|
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Метод копирования, который задает разделитель элементов переменные из другого объекта.|
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Возвращает размер разделителя.|
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Указывает, является ли разделитель.|
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Указывает, является ли это позицией табуляции.|
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Вызывается системой для рисования разделителя на ленте или в панель быстрого доступа.|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Вызывается системой для рисования разделителя на **команды** списка.|

## <a name="remarks"></a>Примечания

Разделитель ленты — вертикальной или горизонтальной линией, что логически разделяет элементы ленты. Разделитель можно изображать на элемент управления ленты, в меню основного приложения, строки состояния ленты и панель быстрого доступа.

Необходимо использовать разделитель в приложении, создать новый объект и его добавления в меню основного приложения, как показано ниже:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```
Вызовите [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) разделители добавляемый панелей ленты. Разделители выделенных и добавлены внутренне `AddSeparator` метод.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbaseribbonelement.h

##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox

Добавляет разделитель для **команды** в списке **Настройка** диалоговое окно.

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Параметры

*pWndListBox*<br/>
[in] Указатель на **команды** списка, где добавляется разделитель.

*bDeep*<br/>
[in] Игнорируется.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс строки в поле со списком определяется *pWndListBox*.

##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator

Создает объект `CMFCRibbonSeparator`.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Параметры

*bIsHoriz*<br/>
[in] Значение TRUE, если разделитель является горизонтальной; Если значение равно FALSE, разделитель является вертикальным.

### <a name="remarks"></a>Примечания

Разделителей используются в меню приложения. Вертикальная разделители используются в панели инструментов.

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCRibbonSeparator` класса.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom

Метод копирования, который задает разделитель элементов переменные из другого объекта.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Исходный элемент ленты для копирования из.

##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize

Возвращает размер разделителя.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на содержимое устройства.

### <a name="return-value"></a>Возвращаемое значение

Размер разделителя в данном контексте.

##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator

Указывает, является ли разделитель.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE для этого класса.

##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop

Указывает, является ли это позицией табуляции.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда имеет значение FALSE для этого класса.

### <a name="remarks"></a>Примечания

Разделитель ленты не является позицией табуляции.

##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw

Вызывается системой для рисования разделителя на ленте или в панель быстрого доступа.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства.

##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList

Вызывается системой для рисования разделителя на **команды** списка.

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
|*pDC*|[in] Указатель на контекст устройства.|
|*strText*|[in] Текст, отображаемый в списке.|
|*nTextOffset*|[in] Расстояние между текстом и левой стороны обрамляющего прямоугольника.|
|*Rect*|[in] Указывает ограничивающий прямоугольник.|
|*bIsSelected*|[in] Игнорируется.|
|*bHighlighted*|[in] Игнорируется.|

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
