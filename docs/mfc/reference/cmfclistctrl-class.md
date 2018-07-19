---
title: Класс CMFCListCtrl | Документация Майкрософт
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
ms.openlocfilehash: 04eccb2d1472afb1c04daac8ab23c2ce6fe97c58
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851449"
---
# <a name="cmfclistctrl-class"></a>Класс CMFCListCtrl
`CMFCListCtrl` Класс расширяет функциональность [класс CListCtrl](../../mfc/reference/clistctrl-class.md) счет функциональные возможности элемента управления заголовка расширенной поддержки [класс CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Включает возможность пометить в столбце с другой цвет фона.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Включает несколько режим сортировки.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Возвращает ссылку на подчеркнутый заголовка элемента управления.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Проверяет, находится ли элемент управления списком в несколько режим сортировки.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Вызывается платформой, когда он должен сравнить два элемента управления списка.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Вызывается платформой, когда он должен определить цвет фона отдельной ячейке.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Вызывается платформой, когда он должен получить шрифт для изображаемого ячейки.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Вызывается платформой, когда он должен определить цвет текста в отдельной ячейке.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет столбец сортировки из списка отсортированных столбцов.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Задает текущий сортируемый столбец и порядок сортировки.|  
|[CMFCListCtrl::Sort](#sort)|Сортирует элемент управления списка.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCListCtrl` предоставляет два расширения [класс CListCtrl](../../mfc/reference/clistctrl-class.md) класса. Во-первых он указывает сортировку по столбцам доступна, автоматически нарисовав стрелка сортировки в заголовке. Во-вторых он поддерживает данные, сортировка по нескольким столбцам, в то же время.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCListCtrl` класса. В примере показано создание элемента управления списка, Вставка столбцов, вставлять элементы, задайте текст элемента и задание шрифта элемента управления списком. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
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
 Логический параметр, который определяет, следует ли немедленно перерисовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
 `EnableMarkSortedColumn` использует метод `CDrawingManager::PixelAlpha` для вычисления цвета, которые используются для сортировки столбцов. Выбрать цвет основан регулярных фоновый цвет.  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 Позволяет осуществлять сортировку по нескольким столбцам строки данных в элементе управления списком.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Логическое значение, указывающее, следует ли включить режим сортировки нескольких столбцов.  
  
### <a name="remarks"></a>Примечания  
 Если включить сортировку на основе нескольких столбцов, столбцы имеют иерархию. Строки данных будут отсортированы сначала по столбцу первичного. Затем все эквивалентные значения сортируются по каждый следующий столбец, на основе приоритета.  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 Возвращает ссылку на элемент управления заголовка.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на базовый [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления заголовка для элемента управления списка — это окно, содержащее заголовки столбцов. Обычно она располагается непосредственно над столбцами.  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 Проверяет ли элемент управления списка в настоящее время поддерживает сортировку по нескольким столбцам.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент управления списка поддерживает несколько сортировки; Значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Когда [класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md) поддерживает несколько сортировку, пользователь может сортировать данные в элементе управления списком по нескольким столбцам. Чтобы включить несколько сортировку, вызовите [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
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
 Индекс столбца, который этот метод является сортировка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, определяющее относительное положение двух элементов. Отрицательное значение указывает, что первый элемент должен находиться перед второй, положительное значение указывает, что первый элемент необходимо следовать второй и нулевое значение означает, что два элемента эквивалентны.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию всегда возвращает значение 0. Необходимо переопределить эту функцию, чтобы указать алгоритм сортировки.  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 Платформа вызывает этот метод, когда он должен определить цвет фона ячейки в отдельных.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nRow*  
 Строка рассматриваемой ячейки.  
  
 [in] *nColumn*  
 Столбец ячейки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 COLOREF значение, указывающее цвет фона ячейки.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию `OnGetCellBkColor` не использует предоставленных входных параметров и вместо этого просто вызывает `GetBkColor`. Таким образом по умолчанию элемент управления весь список будет иметь тот же цвет фона. Можно переопределить `OnGetCellBkColor` в производном классе, чтобы пометить отдельные ячейки с отдельным фоновым цветом.  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 Этот метод вызывается платформой, когда он получает шрифта в отдельную ячейку.  
  
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
 Определяемые пользователем данные. Реализация по умолчанию этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор шрифт, используемый для текущей ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод возвращает значение NULL. Все ячейки в элементе управления списка имеют тот же шрифт. Переопределите этот метод, чтобы предоставить различные шрифты для различных ячеек.  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 Платформа вызывает этот метод, когда он должен определить цвет текста ячейки в отдельных.  
  
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
 COLOREF значение, указывающее цвет текста ячейки.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывает `GetTextColor` вне зависимости от входных параметров. Весь список элемент управления будет иметь тот же цвет текста. Можно переопределить `OnGetCellTextColor` в производном классе для пометки отдельных ячеек цветом разделитель.  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 Удаляет столбец сортировки из списка отсортированных столбцов.  
  
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
 Логическое значение, указывающее, является ли этот метод добавляет столбец, указанный параметром *iColumn* в список столбцов сортировки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод передает входные параметры для управления заголовка с помощью метода [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 Сортирует элемент управления списка.  
  
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
 Логическое значение, указывающее, является ли этот метод добавляет столбец, указанный параметром *iColumn* в список столбцов сортировки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
