---
title: Класс Кмфклистктрл
ms.date: 07/30/2019
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 599a00af28ee5b8effbabbe5b334022ceb49f91a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682348"
---
# <a name="cmfclistctrl-class"></a>Класс Кмфклистктрл

Класс расширяет функциональные возможности класса [класса CListCtrl](../../mfc/reference/clistctrl-class.md) , поддерживая функциональные возможности расширенного управления заголовком [класса кмфчеадерктрл.](../../mfc/reference/cmfcheaderctrl-class.md) `CMFCListCtrl`

## <a name="syntax"></a>Синтаксис

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфклистктрл:: Енаблемарксортедколумн](#enablemarksortedcolumn)|Позволяет помечать отсортированный столбец другим цветом фона.|
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Включает режим множественного сортировки.|
|[Кмфклистктрл:: Жесеадерктрл](#getheaderctrl)|Возвращает ссылку на подчеркнутый элемент управления заголовка.|
|[Кмфклистктрл:: Исмултиплесорт](#ismultiplesort)|Проверяет, находится ли элемент управления "список" в режиме множественного сортировки.|
|[Кмфклистктрл:: Онкомпареитемс](#oncompareitems)|Вызывается структурой при необходимости сравнения двух элементов управления "список".|
|[Кмфклистктрл:: Онжетцеллбкколор](#ongetcellbkcolor)|Вызывается платформой, когда он должен определить цвет фона отдельной ячейки.|
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Вызывается структурой, когда необходимо получить шрифт для рисуемой ячейки.|
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Вызывается платформой, когда он должен определить цвет текста отдельной ячейки.|
|[Кмфклистктрл:: Ремовесортколумн](#removesortcolumn)|Удаляет столбец сортировки из списка отсортированных столбцов.|
|[Кмфклистктрл:: Сетсортколумн](#setsortcolumn)|Задает текущий отсортированный столбец и порядок сортировки.|
|[Кмфклистктрл:: Sort](#sort)|Сортирует элемент управления "список".|

## <a name="remarks"></a>Примечания

`CMFCListCtrl`предлагает два улучшения класса класса [CListCtrl](../../mfc/reference/clistctrl-class.md) . Во-первых, это означает, что сортировка столбцов является доступным параметром путем автоматического рисования стрелки сортировки в заголовке. Во вторых, он поддерживает сортировку данных в нескольких столбцах одновременно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCListCtrl` . В примере показано, как создать элемент управления списка, Вставить столбцы, вставить элементы, задать текст элемента и задать шрифт элемента управления "список". Этот фрагмент кода является частью демонстрационного [примера Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[кмфклистктрл](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкслистктрл. h

##  <a name="enablemarksortedcolumn"></a>Кмфклистктрл:: Енаблемарксортедколумн

Помечает отсортированные столбцы другим цветом фона.

```
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*бмарк*<br/>
окне Логический параметр, определяющий, следует ли включить другой цвет фона.

*bRedraw*<br/>
окне Логический параметр, который определяет, следует ли немедленно перерисовывать элемент управления.

### <a name="remarks"></a>Примечания

`EnableMarkSortedColumn`использует метод `CDrawingManager::PixelAlpha` для вычисления цвета, используемого для отсортированных столбцов. Выбранный цвет основан на стандартном цвете фона.

##  <a name="enablemultiplesort"></a>Кмфклистктрл:: Енаблемултиплесорт

Позволяет сортировать строки данных в элементе управления "список" по нескольким столбцам.

```
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Логическое значение, указывающее, следует ли включить режим сортировки нескольких столбцов.

### <a name="remarks"></a>Примечания

При включении сортировки на основе нескольких столбцов столбцы имеют иерархию. Строки данных сначала будут отсортированы по первичному столбцу. Затем все эквивалентные значения сортируются по каждому последующему столбцу на основе приоритета.

##  <a name="getheaderctrl"></a>Кмфклистктрл:: Жесеадерктрл

Возвращает ссылку на элемент управления "заголовок".

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый объект [кмфчеадерктрл](../../mfc/reference/cmfcheaderctrl-class.md) .

### <a name="remarks"></a>Примечания

Элементом управления "заголовок" элемента управления "список" является окно, содержащее заголовки столбцов. Обычно он располагается непосредственно над столбцами.

##  <a name="ismultiplesort"></a>Кмфклистктрл:: Исмултиплесорт

Проверяет, поддерживает ли элемент управления "список" сортировку по нескольким столбцам.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент управления "список" поддерживает множественную сортировку; В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если [класс кмфклистктрл](../../mfc/reference/cmfclistctrl-class.md) поддерживает множественную сортировку, пользователь может сортировать данные в элементе управления "список" по нескольким столбцам. Чтобы включить множественную сортировку, вызовите [кмфклистктрл:: енаблемултиплесорт](#enablemultiplesort).

##  <a name="oncompareitems"></a>Кмфклистктрл:: Онкомпареитемс

Платформа вызывает этот метод при сравнении двух элементов.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Параметры

*lParam1*<br/>
окне Первый сравниваемый элемент.

*lParam2*<br/>
окне Второй сравниваемый элемент.

*иколумн*<br/>
окне Индекс столбца, по которому сортируется этот метод.

### <a name="return-value"></a>Возвращаемое значение

Целое число, указывающее относительное расположение двух элементов. Отрицательное значение указывает, что первый элемент должен предшествовать второму, положительное значение указывает, что первый элемент должен следовать за вторым, а ноль означает, что два элемента эквивалентны.

### <a name="remarks"></a>Примечания

Реализация по умолчанию всегда возвращает значение 0. Переопределите эту функцию, чтобы предоставить собственный алгоритм сортировки.

##  <a name="ongetcellbkcolor"></a>Кмфклистктрл:: Онжетцеллбкколор

Платформа вызывает этот метод, когда он должен определить цвет фона отдельной ячейки.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Параметры

*нров*<br/>
окне Строка рассматриваемой ячейки.

*нколумн*<br/>
окне Столбец рассматриваемой ячейки.

### <a name="return-value"></a>Возвращаемое значение

Значение КОЛОРЕФ, указывающее цвет фона ячейки.

### <a name="remarks"></a>Примечания

Реализация `OnGetCellBkColor` по умолчанию не использует указанные входные параметры, а вместо этого просто `GetBkColor`вызывает. Таким образом, по умолчанию весь элемент управления "список" будет иметь тот же цвет фона. Можно переопределить `OnGetCellBkColor` в производном классе, чтобы пометить отдельные ячейки отдельным цветом фона.

##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont

Платформа вызывает этот метод, когда получает шрифт для отдельной ячейки.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>Параметры

*нров*<br/>
окне Строка рассматриваемой ячейки.

*нколумн*<br/>
окне Столбец рассматриваемой ячейки.

*двдата*<br/>
окне Определяемые пользователем данные. Реализация по умолчанию не использует этот параметр.

### <a name="return-value"></a>Возвращаемое значение

Маркер для шрифта, используемого для текущей ячейки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод возвращает значение NULL. Все ячейки в элементе управления "список" имеют одинаковый шрифт. Переопределите этот метод, чтобы предоставить различные шрифты для разных ячеек.

##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor

Платформа вызывает этот метод, когда он должен определить цвет текста отдельной ячейки.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Параметры

*нров*<br/>
окне Строка рассматриваемой ячейки.

*нколумн*<br/>
окне Столбец рассматриваемой ячейки.

### <a name="return-value"></a>Возвращаемое значение

Значение КОЛОРЕФ, указывающее цвет текста ячейки.

### <a name="remarks"></a>Примечания

По умолчанию этот метод вызывает `GetTextColor` независимо от входных параметров. Весь элемент управления "список" будет иметь тот же цвет текста. Можно переопределить `OnGetCellTextColor` в производном классе, чтобы пометить отдельные ячейки отдельным цветом текста.

##  <a name="removesortcolumn"></a>Кмфклистктрл:: Ремовесортколумн

Удаляет столбец сортировки из списка отсортированных столбцов.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Параметры

*иколумн*<br/>
окне Удаляемый столбец.

### <a name="remarks"></a>Примечания

Этот метод удаляет столбец сортировки из элемента управления "заголовок". Он вызывает [кмфчеадерктрл:: ремовесортколумн](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).

##  <a name="setsortcolumn"></a>Кмфклистктрл:: Сетсортколумн

Задает текущий отсортированный столбец и порядок сортировки.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Параметры

*иколумн*<br/>
окне Столбец для сортировки.

*басцендинг*<br/>
окне Логическое значение, указывающее порядок сортировки.

*бадд*<br/>
окне Логическое значение, указывающее, добавляет ли метод столбец, указанный параметром *иколумн* , в список столбцов сортировки.

### <a name="remarks"></a>Примечания

Этот метод передает входные параметры в элемент управления заголовка с помощью метода [кмфчеадерктрл:: сетсортколумн](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).

##  <a name="sort"></a>Кмфклистктрл:: Sort

Сортирует элемент управления "список".

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Параметры

*иколумн*<br/>
окне Столбец для сортировки.

*басцендинг*<br/>
окне Логическое значение, указывающее порядок сортировки.

*бадд*<br/>
окне Логическое значение, указывающее, добавляет ли этот метод столбец, указанный параметром *иколумн* , в список столбцов сортировки.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
