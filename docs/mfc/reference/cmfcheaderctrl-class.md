---
title: Класс CMFCHeaderCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
dev_langs:
- C++
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97e0a81fc5e317f018924efd3d564d39618cb2b5
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850086"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class
`CMFCHeaderCtrl` Класс поддерживает несколько столбцов сортировки в заголовок элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Создает объект `CMFCHeaderCtrl`.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Включает или отключает *несколько столбцов сортировки* режим для текущего элемента управления заголовка.|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Указывает столбец не отсортирован, или сортируется в порядке возрастания или убывания.|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Возвращает отсчитываемый от нуля индекс первого отсортированного столбца в элементе управления заголовка.|  
|`CMFCHeaderCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|Указывает, сортируются ли любой столбец в элементе управления заголовка в порядке возрастания.|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Указывает, является ли родительское окно в текущем элементе управления заголовком диалоговое окно.|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Указывает, является ли текущий элемент управления заголовка в *несколько столбцов сортировки* режим.|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Удаляет указанный столбец из списка столбцов сортировки.|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Задает порядок сортировки элементов заданного столбца в элементе управления заголовка.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Вызывается платформой для отрисовки элемента управления заголовка столбца.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Вызывается платформой для отрисовки стрелки сортировки.|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Вызывается платформой для заливки фона элемента управления заголовка столбца.|  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта класса `CMFCHeaderCtrl` класс и включение *несколько столбцов сортировки* режим для текущего элемента управления заголовка.  
  
 [!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>Примечания  
 `CMFCHeaderCtrl` Класс Рисует стрелку сортировки по столбцу элемента управления заголовка, чтобы указать, что столбец отсортирован. Используйте *несколько столбцов сортировки* режим, если набор столбцов в список родительского элемента управления ( [класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)) могут быть отсортированы в то же время.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxheaderctrl.h  
  
##  <a name="cmfcheaderctrl"></a>  CMFCHeaderCtrl::CMFCHeaderCtrl  
 Создает объект `CMFCHeaderCtrl`.  
  
```  
CMFCHeaderCtrl::CMFCHeaderCtrl()  
```  
  
### <a name="remarks"></a>Примечания  
 Этот конструктор инициализирует следующие переменные-члены указанные значения:  
  
|Переменная-член|Значение|  
|---------------------|-----------|  
|`m_bIsMousePressed`|false|  
|`m_bMultipleSort`|false|  
|`m_bAscending`|true|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|false|  
|`m_bIsDlgControl`|FALSE|  
|`m_hFont`|NULL|  
  
##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort  
 Включает или отключает *несколько столбцов сортировки* режим для текущего элемента управления заголовка.  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *bEnable*  
 Значение TRUE, чтобы включить режим сортировки нескольких столбцов; Значение FALSE, чтобы отключить режим сортировки нескольких столбцов и удалите все столбцы из списка отсортированных столбцов. Значение по умолчанию — TRUE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет включить или отключить режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировку, если элемент управления заголовка в режим сортировки нескольких столбцов.  
  
##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState  
 Указывает столбец не отсортирован, или сортируется в порядке возрастания или убывания.  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Отсчитываемый от нуля индекс столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, состояние указанного столбца сортировки. В следующей таблице перечислены возможные значения:  
  
|Значение|Описание:|  
|-----------|-----------------|  
|-1|Отсортирован в порядке убывания.|  
|0|Не сортируются.|  
|1|Сортировка в порядке возрастания.|  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn  
 Возвращает отсчитываемый от нуля индекс первого отсортированного столбца в элементе управления заголовка.  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс столбца или -1, если отсортированный столбец не найден.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления заголовка в *несколько столбцов сортировки* режиме и используется приложение, скомпилированное в режиме отладки, этот метод утверждения и система предложит использовать [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) метод вместо этого. Если элемент управления заголовка находится в режим сортировки нескольких столбцов и скомпилировать приложение в режиме розничной торговли, этот метод возвращает значение -1.  
  
##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending  
 Указывает, сортируются ли любой столбец в элементе управления заголовка в порядке возрастания.  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если любой столбец в элементе управления заголовка сортируется по возрастанию; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Значение, которое возвращает этот метод используется для отображения стрелку соответствующие сортировки в верхнем колонтитуле элемента управления. Используйте [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) метод, чтобы задать порядок сортировки.  
  
##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl  
 Указывает, является ли родительское окно в текущем элементе управления заголовком диалоговое окно.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если родительское окно текущего элемента управления заголовка диалогового окна; в противном случае — значение FALSE.  
  
##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort  
 Указывает, является ли текущий элемент управления заголовка в *несколько столбцов сортировки* режим.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если включен режим сортировки нескольких столбцов; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) метод, чтобы включить или отключить режим сортировки нескольких столбцов. Два или более столбцов могут участвовать в сортировку, если элемент управления заголовка в режим сортировки нескольких столбцов.  
  
##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem  
 Вызывается платформой для отрисовки элемента управления заголовка столбца.  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *iItem*  
 Отсчитываемый от нуля индекс элемента для рисования.  
  
 [in] *rect*  
 Ограничивающий прямоугольник для рисования элемента.  
  
 [in] *bIsPressed*  
 Значение TRUE для рисования элемента в нажатом состоянии; в противном случае — значение FALSE.  
  
 [in] *bIsHighlighted*  
 Значение TRUE для рисования элемента в выделенный состоянии; в противном случае — значение FALSE.  
  
##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow  
 Вызывается платформой для отрисовки стрелки сортировки.  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rectArrow*  
 Ограничивающий прямоугольник стрелки сортировки.  
  
##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground  
 Вызывается платформой для заливки фона элемента управления заголовка столбца.  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn  
 Удаляет указанный столбец из списка столбцов сортировки.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Отсчитываемый от нуля индекс столбца для удаления.  
  
##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn  
 Задает порядок сортировки элементов заданного столбца в элементе управления заголовка.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *iColumn*  
 Отсчитываемый от нуля индекс заголовка столбца элемента управления. Если этот параметр меньше нуля, этот метод удаляет все столбцы из списка столбцов сортировки.  
  
 [in] *bAscending*  
 Указывает порядок сортировки столбца, *iColumn* указывает параметр. Значение TRUE, чтобы задать в возрастающем порядке; Значение FALSE, чтобы задать в порядке убывания. Значение по умолчанию — TRUE.  
  
 [in] *bAdd*  
 Значение true для порядка сортировки столбца, *iColumn* указывает параметр.  
  
 Если текущий элемент управления заголовка находится в *несколько столбцов сортировки* режиме, этот метод добавляет указанный столбец в список столбцов сортировки. Используйте [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) задать режим сортировки нескольких столбцов.  
  
 Если установлен режим сортировки нескольких столбцов, и этот метод компилируется в режиме отладки, этот метод утверждения. Если установлен режим сортировки нескольких столбцов, этот метод компилируется в режиме розничной торговли, этот метод сначала удаляет все столбцы из списка столбцов сортировки и затем добавляет указанный столбец в список.  
  
 Значение FALSE, чтобы сначала удалить все столбцы из списка столбцов сортировки и затем добавить указанный столбец в список. Значение по умолчанию — FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет установить порядок сортировки столбца. При необходимости этот метод добавляет столбец к списку столбцов сортировки. Элемент управления заголовка использует порядок сортировки для отрисовки стрелки сортировки, указывающую вверх или вниз.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)
