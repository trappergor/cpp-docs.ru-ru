---
title: "Класс CMFCHeaderCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCHeaderCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCHeaderCtrl class
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
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
ms.openlocfilehash: c49ee61b6441e79a0c3c4c1aa133b4bce1578103
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class
`CMFCHeaderCtrl` Класс поддерживает несколько столбцов сортировки в заголовок элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Создает объект `CMFCHeaderCtrl`.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Включает или отключает *несколько столбцов сортировки* режим для текущего элемента управления заголовка.|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Указывает столбец не отсортирован, или сортируется в порядке возрастания или убывания.|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Возвращает отсчитываемый от нуля индекс первого столбца сортировки в элементе управления заголовка.|  
|`CMFCHeaderCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|Указывает, сортируются ли в элементе управления заголовка любого столбца в порядке возрастания.|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Указывает, является ли родительского окна текущего элемента управления заголовка диалоговое окно.|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Указывает, является ли текущий элемент управления заголовка в *несколько столбцов сортировки* режим.|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет указанный столбец из списка столбцов сортировки.|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Задает порядок сортировки элементов заданного столбца в элементе управления заголовка.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Вызывается платформой для рисования элемента управления заголовка столбца.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Вызывается платформой для рисования стрелки сортировки.|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Вызывается платформой для заливки фона элемента управления заголовка столбца.|  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCHeaderCtrl` класс и включение *несколько столбцов сортировки* режим для текущего элемента управления заголовка.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#24;](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>Примечания  
 `CMFCHeaderCtrl` Класс Рисует стрелку сортировки в заголовок столбца элемента управления для указания, что столбец отсортирован. Используйте *несколько столбцов сортировки* режиме, если набор столбцов в список родительского элемента управления ( [CMFCListCtrl класса](../../mfc/reference/cmfclistctrl-class.md)) могут быть отсортированы в то же время.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxheaderctrl.h  
  
##  <a name="a-namecmfcheaderctrla--cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a>CMFCHeaderCtrl::CMFCHeaderCtrl  
 Создает объект `CMFCHeaderCtrl`.  
  
```  
CMFCHeaderCtrl::CMFCHeaderCtrl()  
```  
  
### <a name="remarks"></a>Примечания  
 Этот конструктор инициализирует следующие переменные-члены с указанными значениями.  
  
|Переменная-член|Значение|  
|---------------------|-----------|  
|`m_bIsMousePressed`|`FALSE`|  
|`m_bMultipleSort`|`FALSE`|  
|`m_bAscending`|`TRUE`|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|`FALSE`|  
|`m_bIsDlgControl`|`FALSE`|  
|`m_hFont`|`NULL`|  
  
##  <a name="a-nameenablemultiplesorta--cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCHeaderCtrl::EnableMultipleSort  
 Включает или отключает *несколько столбцов сортировки* режим для текущего элемента управления заголовка.  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить режим сортировки нескольких столбцов; `FALSE` отключить режим сортировки нескольких столбцов и удалить все столбцы из списка отсортированных столбцов. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы включить или отключить режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировку, если элемент управления заголовка находится в режим сортировки нескольких столбцов.  
  
##  <a name="a-namegetcolumnstatea--cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a>CMFCHeaderCtrl::GetColumnState  
 Указывает столбец не отсортирован, или сортируется в порядке возрастания или убывания.  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Отсчитываемый от нуля индекс столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающие состояние сортировки указанного столбца. В следующей таблице перечислены возможные значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|-1|Отсортирован в порядке убывания.|  
|0|Не отсортирован.|  
|1|Сортировка по возрастанию.|  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetsortcolumna--cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a>CMFCHeaderCtrl::GetSortColumn  
 Возвращает отсчитываемый от нуля индекс первого столбца сортировки в элементе управления заголовка.  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сортировки столбца или значение -1, если отсортированный столбец не найден.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления заголовка находится в *несколько столбцов сортировки* режиме и компиляции приложения в режиме отладки, этот метод подтверждает и рекомендующее использовать [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) метод вместо. Если элемент управления заголовка находится в режим сортировки нескольких столбцов и компиляции приложения в режиме розничной торговли, этот метод возвращает значение -1.  
  
##  <a name="a-nameisascendinga--cmfcheaderctrlisascending"></a><a name="isascending"></a>CMFCHeaderCtrl::IsAscending  
 Указывает, сортируются ли в элементе управления заголовка любого столбца в порядке возрастания.  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если любой столбец в элементе управления заголовка сортируется по возрастанию. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Значение, которое возвращает этот метод используется для отображения стрелку соответствующие сортировки в элементе управления заголовка. Используйте [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) метод для указания порядка сортировки.  
  
##  <a name="a-nameisdialogcontrola--cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>CMFCHeaderCtrl::IsDialogControl  
 Указывает, является ли родительского окна текущего элемента управления заголовка диалоговое окно.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительское окно текущего элемента управления заголовка диалогового окна; в противном случае — `FALSE`.  
  
##  <a name="a-nameismultiplesorta--cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCHeaderCtrl::IsMultipleSort  
 Указывает, является ли текущий элемент управления заголовка в *несколько столбцов сортировки* режим.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включен режим сортировки нескольких столбцов. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) метод, чтобы включить или отключить режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировку, если элемент управления заголовка находится в режим сортировки нескольких столбцов.  
  
##  <a name="a-nameondrawitema--cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a>CMFCHeaderCtrl::OnDrawItem  
 Вызывается платформой для рисования элемента управления заголовка столбца.  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `iItem`  
 Отсчитываемый от нуля индекс элемента для рисования.  
  
 [in] `rect`  
 Ограничивающий прямоугольник для рисования элемента.  
  
 [in] `bIsPressed`  
 `TRUE`для рисования элемента в нажатом состоянии; в противном случае — `FALSE`.  
  
 [in] `bIsHighlighted`  
 `TRUE`для рисования элемента в выделенный состоянии; в противном случае — `FALSE`.  
  
##  <a name="a-nameondrawsortarrowa--cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a>CMFCHeaderCtrl::OnDrawSortArrow  
 Вызывается платформой для рисования стрелки сортировки.  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectArrow`  
 Ограничивающий прямоугольник стрелку сортировки.  
  
##  <a name="a-nameonfillbackgrounda--cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCHeaderCtrl::OnFillBackground  
 Вызывается платформой для заливки фона элемента управления заголовка столбца.  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremovesortcolumna--cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCHeaderCtrl::RemoveSortColumn  
 Удаляет указанный столбец из списка столбцов сортировки.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Отсчитываемый от нуля индекс столбца для удаления.  
  
##  <a name="a-namesetsortcolumna--cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCHeaderCtrl::SetSortColumn  
 Задает порядок сортировки элементов заданного столбца в элементе управления заголовка.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iColumn`  
 Отсчитываемый от нуля индекс заголовка столбца элемента управления. Если этот параметр меньше нуля, этот метод удаляет все столбцы из списка столбцов сортировки.  
  
 [in] `bAscending`  
 Указывает порядок сортировки столбца, `iColumn` указывает параметр. `TRUE`Чтобы задать в возрастающем порядке; `FALSE` для установки в порядке убывания. Значение по умолчанию — `TRUE`.  
  
 [in] `bAdd`  
 `TRUE`Чтобы установить порядок сортировки столбца, `iColumn` указывает параметр.  
  
 Если текущий элемент управления заголовка находится в *несколько столбцов сортировки* режим, этот метод добавляет указанный столбец в список столбцов для сортировки. Используйте [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) Чтобы задать режим сортировки нескольких столбцов.  
  
 Если установлен режим сортировки нескольких столбцов, этот метод компилируется в режиме отладки, этот метод подтверждает. Если установлен режим сортировки нескольких столбцов, этот метод компилируется в режиме розничной торговли, этот метод сначала удаляет все столбцы из списка столбцов сортировки и затем добавляет указанный столбец в список.  
  
 `FALSE`Сначала удалите все столбцы в списке столбцов для сортировки и затем добавить указанный столбец в список. Значение по умолчанию — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать порядок сортировки столбца. При необходимости этот метод добавляет столбец в список столбцов для сортировки. Заголовок элемента управления использует порядок сортировки, чтобы нарисовать стрелку сортировки, указывающую вверх или вниз.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

