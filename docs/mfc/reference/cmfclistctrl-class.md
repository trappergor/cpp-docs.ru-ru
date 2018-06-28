---
title: Класс CMFCListCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00933a392486064fac7c9a526d8b0c096703460c
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037740"
---
# <a name="cmfclistctrl-class"></a>Класс CMFCListCtrl
`CMFCListCtrl` Класс расширяет функциональность [CListCtrl-класс](../../mfc/reference/clistctrl-class.md) класса путем поддержки функциональные возможности управления Дополнительно заголовок [CMFCHeaderCtrl класса](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Дает возможность пометить отсортированный столбец с другой цвет фона.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Включает несколько режим сортировки.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Возвращает ссылку на подчеркнутый заголовка элемента управления.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Проверяет, является ли элемент управления списка в нескольких режим сортировки.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Вызывается платформой, когда он должен сравнить два элемента управления списка.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Вызывается платформой, когда он должен определить цвет фона отдельной ячейки.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Вызывается платформой, когда он должен получить шрифт для ячейки, в которых выводится.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Вызывается платформой, когда он должен определить цвет текста отдельной ячейки.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет столбец сортировки из списка отсортированными столбцами.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Задает текущий сортируемый столбец и порядок сортировки.|  
|[CMFCListCtrl::Sort](#sort)|Сортирует управления "список".|  
  
## <a name="remarks"></a>Примечания  
 `CMFCListCtrl` предоставляет два расширения [CListCtrl-класс](../../mfc/reference/clistctrl-class.md) класса. Во-первых он указывает на сортировку по столбцам доступный параметр, автоматически нарисовав стрелки сортировки в заголовке. Во-вторых она поддерживает данных сортировку по нескольким столбцам, в то же время.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCListCtrl` класса. В примере показано создания элемента управления списком, вставлять столбцы, вставлять элементы, задать текст элемента и задать шрифт элемента управления списком. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxlistctrl.h  
  
##  <a name="enablemarksortedcolumn"></a>  CMFCListCtrl::EnableMarkSortedColumn  
 Помечает отсортированными столбцами с другой цвет фона.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bMark*  
 Логический параметр, который определяет, следует ли включить другой цвет фона.  
  
 [in] *bRedraw*  
 Логического параметра, который определяет, нужно ли немедленно перерисовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
 `EnableMarkSortedColumn` использует метод `CDrawingManager::PixelAlpha` для вычисления цвета, которые используются для сортировки столбцов. Выбрать цвет создается на основе регулярного фоновый цвет.  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 Позволяет осуществлять сортировку по нескольким столбцам строки данных в элементе управления списком.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Логическое значение, указывающее, следует ли включить режим сортировки нескольких столбцов.  
  
### <a name="remarks"></a>Примечания  
 Если включить сортировку по нескольким столбцам, столбцы имеют иерархию. Строки данных будут сначала сортируется по столбцу первичного. Затем все эквивалентные значения сортируются по каждого последующего столбца на основе приоритета.  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 Возвращает ссылку на элемент управления заголовка.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на базовый [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Заголовок элемента управления для элемента управления list — это окно, содержащее заголовки столбцов. Обычно располагается непосредственно над столбцами.  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 Проверяет ли элемент управления списком в настоящее время поддерживает сортировку по нескольким столбцам.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если элемент управления списка поддерживает несколько сортировки; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Когда [CMFCListCtrl класс](../../mfc/reference/cmfclistctrl-class.md) поддерживает несколько сортировку, пользователь может сортировать данные в элементе управления списком по нескольким столбцам. Чтобы включить несколько сортировки, вызовите [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems  
 Этот метод вызывается платформой при сравнении двух элементов.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lParam1*  
 Первый элемент для сравнения.  
  
 [in] *lParam2*  
 Второй элемент для сравнения.  
  
 [in] *iColumn*  
 Индекс столбца, этот метод выполняет сортировку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, указывающее относительную позицию двух элементов. Отрицательное значение указывает, что первый элемент должен находиться перед второй, положительное значение указывает, что первый элемент должен следовать за секунду и ноль означает, что два элемента эквивалентны.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию всегда возвращает 0. Необходимо переопределить эту функцию для предоставления алгоритма сортировки.  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 Платформа вызывает этот метод, когда он должен определить цвет фона отдельной ячейки.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRow`  
 Строка рассматриваемой ячейки.  
  
 [in] `nColumn`  
 Столбец ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `COLOREF` значение, указывающее цвет фона для ячейки.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `OnGetCellBkColor` не используют предоставленных входных параметров и вместо этого просто вызывает `GetBkColor`. Таким образом по умолчанию элемент управления списка будет иметь тот же цвет фона. Можно переопределить `OnGetCellBkColor` в производном классе для пометки отдельных ячеек отдельным фоновым цветом.  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 Платформа вызывает этот метод, когда он получает шрифта для всех ячеек.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRow*  
 Строка рассматриваемой ячейки.  
  
 [in] *nColumn*  
 Столбец ячейки.  
  
 [in] *dwData*  
 Определенные пользователем данные. Реализация по умолчанию этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор шрифт, используемый для текущей ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод возвращает `NULL`. Все ячейки в элементе управления списком имеют тот же шрифт. Переопределите этот метод для предоставления различных шрифтов для различных ячеек.  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 Платформа вызывает этот метод, когда он должен определить цвет текста отдельной ячейки.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRow*  
 Строка рассматриваемой ячейки.  
  
 [in] *nColumn*  
 Столбец ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `COLOREF` значение, определяющее цвет текста ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывает метод `GetTextColor` независимо от того, входные параметры. Элемент управления списка будут иметь один и тот же цвет текста. Можно переопределить `OnGetCellTextColor` в производном классе для пометки отдельных ячеек разделитель цветом.  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 Удаляет столбец сортировки из списка отсортированными столбцами.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Чтобы удалить столбец.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет столбец сортировки из заголовка элемента управления. Он вызывает [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn  
 Задает текущий сортируемый столбец и порядок сортировки.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Столбец для сортировки.  
  
 [in] *bAscending*  
 Логическое значение, указывающее порядок сортировки.  
  
 [in] *bAdd*  
 Логическое значение, указывающее, добавляет ли метод столбце, обозначенном *iColumn* в список столбцов для сортировки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод передает входные параметры для управления заголовка с помощью метода [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 Сортирует управления "список".  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Столбец для сортировки.  
  
 [in] *bAscending*  
 Логическое значение, указывающее порядок сортировки.  
  
 [in] *bAdd*  
 Логическое значение, указывающее, является ли этот метод добавляет столбец, обозначенном *iColumn* в список столбцов для сортировки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
