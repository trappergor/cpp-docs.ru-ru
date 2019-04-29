---
title: Класс CMFCRibbonProgressBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: 7c16217378cb8825ca4605687770de177e720c1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391118"
---
# <a name="cmfcribbonprogressbar-class"></a>Класс CMFCRibbonProgressBar

Реализует элемент управления, который визуально показывает ход выполнения длительных операций.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Создает и инициализирует объект `CMFCRibbonProgressBar`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|Возвращает текущий ход выполнения.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Возвращает максимальное значение текущего диапазона.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Возвращает минимальное значение текущего диапазона.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Указывает, работает ли индикатор хода выполнения в режиме бесконечного.|
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Задает индикатор хода выполнения работы в режиме бесконечного.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|Задает текущий ход выполнения.|
|[CMFCRibbonProgressBar::SetRange](#setrange)|Задает минимальное и максимальное значения.|

## <a name="remarks"></a>Примечания

Объект `CMFCRibbonProgressBar` может работать в двух режимах: обычные и бесконечной. В обычном режиме индикатора выполнения заполняется слева направо и останавливается при достижении максимального значения. В режиме бесконечного индикатор хода выполнения несколько раз заполняется с минимального значения максимальному значению. Бесконечный режим можно использовать для указания, что операция является постоянной, но, что время выполнения неизвестно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonProgressBar` . В примере как задать индикатор хода выполнения для работы в бесконечную режиме (где время завершения операции неизвестно), установите минимальное и максимальное значения для индикатора выполнения и установить текущее положение индикатора выполнения. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonProgressBar.h

##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar

Создает и инициализирует [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) объекта.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Указывает идентификатор команды для индикатора ленты.

*nWidth*<br/>
[in] Задает ширину в пикселях индикатора хода выполнения на ленте.

*nHeight*<br/>
[in] Указывает высоту в пикселях индикатора хода выполнения на ленте.

##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos

Возвращает текущую позицию индикатора хода выполнения.

```
int GetPos () const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее текущее положение индикатора выполнения.

### <a name="remarks"></a>Примечания

Диапазон задаваемое должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.

##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax

Возвращает текущий индикатор максимальное значение.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное значение текущего диапазона.

### <a name="remarks"></a>Примечания

##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin

Возвращает текущий индикатор минимальное значение диапазона.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальное значение текущего диапазона.

##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode

Указывает, работает ли индикатор хода выполнения в режиме бесконечного.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если индикатор хода выполнения в режиме бесконечного; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В бесконечный режиме индикатор заполняет несколько раз с минимального значения до максимального значения. Бесконечный режим можно использовать для указания, что операция является постоянной, но, что время выполнения неизвестно.

##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode

Задает индикатор хода выполнения работы в режиме бесконечного.

```
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
[in] Значение TRUE, чтобы указать, что индикатор хода выполнения в режиме бесконечного; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Как правило Если индикатор хода выполнения в режиме бесконечного, он сообщает пользователю, что операция является постоянной, но, что время выполнения неизвестно. Таким образом индикатор хода выполнения заполняет многократно от минимального значения до максимального значения.

##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos

Задает текущую позицию индикатора хода выполнения.

```
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
[in] Задает позицию, к которой имеет значение индикатора выполнения.

*bRedraw*<br/>
[in] Указывает, должны быть перерисованы индикатор хода выполнения.

### <a name="remarks"></a>Примечания

Диапазон задаваемое должен быть в диапазоне, определяемом [CMFCRibbonProgressBar::SetRange](#setrange) метод.

##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange

Задает минимальное и максимальное значения для индикатора выполнения.

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
[in] Задает минимальное значение диапазона.

*Nмакс.*<br/>
[in] Указывает максимальное значение диапазона.

### <a name="remarks"></a>Примечания

Используйте этот метод для определения диапазона индикатора хода выполнения, задав минимальное и максимальное значения.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
