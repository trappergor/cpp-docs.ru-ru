---
title: "Класс CMFCListCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCListCtrl class
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a4c67b2d7ea2a5356f7c053403edf414319a928
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclistctrl-class"></a>Класс CMFCListCtrl
`CMFCListCtrl` Класс расширяет функциональные возможности [CListCtrl-класс](../../mfc/reference/clistctrl-class.md) класс, поддерживая функциональные возможности управления расширенного заголовок [CMFCHeaderCtrl класса](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Позволяет помечать отсортированный столбец с другой цвет фона.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Включает несколько режима сортировки.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Возвращает ссылку на подчеркнутый заголовка элемента управления.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Проверяет, является элемент управления списком в режиме множественного сортировки.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Вызывается инфраструктурой при его необходимо сравнить два элемента управления списка.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Вызывается платформой, когда он должен определить цвет фона отдельной ячейки.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Вызывается платформой, когда он должен получить шрифт для ячейки, в котором производится рисование.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Вызывается платформой, когда он должен определить цвет текста отдельной ячейке.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет столбец сортировки из списка отсортированных столбцов.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Задает текущий столбец сортировки и порядок сортировки.|  
|[CMFCListCtrl::Sort](#sort)|Сортировка списка элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCListCtrl`предлагает два расширения [CListCtrl-класс](../../mfc/reference/clistctrl-class.md) класса. Во-первых это указывает сортировку по столбцам доступна, автоматически нарисовав стрелку сортировки в заголовке. Во-вторых он поддерживает сортировку по нескольким столбцам, в то же время данные.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCListCtrl` класса. В примере для создания элемента управления списком, Вставка столбцов, вставлять элементы, задайте текст элемента, а шрифта элемента управления списком. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#25;](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#26;](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxlistctrl.h  
  
##  <a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn  
 Помечает отсортированных столбцов с другой цвет фона.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMark`  
 Логический параметр, который определяет, следует ли включить цвет фона.  
  
 [in] `bRedraw`  
 Логический параметр, который определяет, нужно ли немедленно перерисовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
 `EnableMarkSortedColumn`использует метод `CDrawingManager::PixelAlpha` для расчета цвета, которые используются для сортировки столбцов. Выбрать цвет основан регулярного фонового цвета.  
  
##  <a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort  
 Обеспечивает сортировку по нескольким столбцам строки данных в элементе управления списком.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логическое значение, указывающее, следует ли включить режим сортировки нескольких столбцов.  
  
### <a name="remarks"></a>Примечания  
 При использовании сортировки на основе нескольких столбцов, столбцы имеют иерархию. Строки данных будут отсортированы сначала по столбцу первичного. Затем все эквивалентные значения сортируются по каждого последующего столбца на основе приоритета.  
  
##  <a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl  
 Возвращает ссылку на элемент управления заголовка.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на базовый [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Заголовок элемента управления для элемента управления списка — это окно, содержащее заголовки столбцов. Обычно располагается непосредственно над столбцами.  
  
##  <a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort  
 Проверяет ли элемент управления списком в настоящее время поддерживает сортировку по нескольким столбцам.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент управления списка поддерживает несколько сортировки; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Когда [CMFCListCtrl класс](../../mfc/reference/cmfclistctrl-class.md) поддерживает несколько сортировку, пользователь может сортировать данные в элементе управления списком по нескольким столбцам. Чтобы включить несколько сортировки, вызовите [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems  
 Платформа вызывает этот метод, когда он сравнивает два элемента.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lParam1`  
 Первый элемент для сравнения.  
  
 [in] `lParam2`  
 Второй элемент для сравнения.  
  
 [in] `iColumn`  
 Индекс столбца, сортировка этот метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, указывающее относительную позицию двух элементов. Отрицательное значение указывает, что первый элемент должен предшествовать второй, положительное значение указывает, что первый элемент должен следовать второй и ноль означает, что два элемента равны.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию всегда возвращает значение 0. Необходимо переопределить эту функцию, чтобы указать алгоритм сортировки.  
  
##  <a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor  
 Платформа вызывает этот метод, когда он должен определить цвет фона отдельной ячейки.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRow`  
 Строка ячейки.  
  
 [in] `nColumn`  
 Столбец ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `COLOREF` значение, указывающее цвет фона для ячейки.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `OnGetCellBkColor` не используют предоставленных входных параметров и вместо этого просто вызывает `GetBkColor`. Таким образом по умолчанию весь список управления будет иметь тот же цвет фона. Можно переопределить `OnGetCellBkColor` в производном классе, чтобы пометить отдельные ячейки с отдельным фоновым цветом.  
  
##  <a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont  
 Платформа вызывает этот метод, когда он получает шрифт для всех ячеек.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRow`  
 Строка ячейки.  
  
 [in] `nColumn`  
 Столбец ячейки.  
  
 [in] `dwData`  
 Определенные пользователем данные. Реализация по умолчанию этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор шрифт, используемый для текущей ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод возвращает `NULL`. Все ячейки в элементе управления списком имеют тот же шрифт. Переопределите этот метод, чтобы предоставить различные шрифты для различных ячеек.  
  
##  <a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor  
 Платформа вызывает этот метод, когда он должен определить цвет текста отдельной ячейке.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nRow`  
 Строка ячейки.  
  
 [in] `nColumn`  
 Столбец ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `COLOREF` значение, определяющее цвет текста ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывает метод `GetTextColor` вне зависимости от входных параметров. Полный список управления будет иметь тот же цвет текста. Можно переопределить `OnGetCellTextColor` в производном классе, чтобы пометить отдельные ячейки разделитель цветом.  
  
##  <a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn  
 Удаляет столбец сортировки из списка отсортированных столбцов.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Чтобы удалить столбец.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет столбец сортировки из заголовка элемента управления. Он вызывает [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn  
 Задает текущий столбец сортировки и порядок сортировки.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Столбец для сортировки.  
  
 [in] `bAscending`  
 Логическое значение, указывающее порядок сортировки.  
  
 [in] `bAdd`  
 Значение типа Boolean, указывает ли этот метод добавляет столбец, обозначенными `iColumn` в список столбцов для сортировки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод передает входные параметры управления заголовка с помощью метода [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>CMFCListCtrl::Sort  
 Сортировка списка элемента управления.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Столбец для сортировки.  
  
 [in] `bAscending`  
 Логическое значение, указывающее порядок сортировки.  
  
 [in] `bAdd`  
 Логическое значение, указывающее, является ли этот метод добавляет столбец, обозначенными `iColumn` в список столбцов для сортировки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)

