---
title: "CTreeCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeCtrl
- AFXCMN/CTreeCtrl
- AFXCMN/CTreeCtrl::CTreeCtrl
- AFXCMN/CTreeCtrl::Create
- AFXCMN/CTreeCtrl::CreateDragImage
- AFXCMN/CTreeCtrl::CreateEx
- AFXCMN/CTreeCtrl::DeleteAllItems
- AFXCMN/CTreeCtrl::DeleteItem
- AFXCMN/CTreeCtrl::EditLabel
- AFXCMN/CTreeCtrl::EndEditLabelNow
- AFXCMN/CTreeCtrl::EnsureVisible
- AFXCMN/CTreeCtrl::Expand
- AFXCMN/CTreeCtrl::GetBkColor
- AFXCMN/CTreeCtrl::GetCheck
- AFXCMN/CTreeCtrl::GetChildItem
- AFXCMN/CTreeCtrl::GetCount
- AFXCMN/CTreeCtrl::GetDropHilightItem
- AFXCMN/CTreeCtrl::GetEditControl
- AFXCMN/CTreeCtrl::GetExtendedStyle
- AFXCMN/CTreeCtrl::GetFirstVisibleItem
- AFXCMN/CTreeCtrl::GetImageList
- AFXCMN/CTreeCtrl::GetIndent
- AFXCMN/CTreeCtrl::GetInsertMarkColor
- AFXCMN/CTreeCtrl::GetItem
- AFXCMN/CTreeCtrl::GetItemData
- AFXCMN/CTreeCtrl::GetItemExpandedImageIndex
- AFXCMN/CTreeCtrl::GetItemHeight
- AFXCMN/CTreeCtrl::GetItemImage
- AFXCMN/CTreeCtrl::GetItemPartRect
- AFXCMN/CTreeCtrl::GetItemRect
- AFXCMN/CTreeCtrl::GetItemState
- AFXCMN/CTreeCtrl::GetItemStateEx
- AFXCMN/CTreeCtrl::GetItemText
- AFXCMN/CTreeCtrl::GetLastVisibleItem
- AFXCMN/CTreeCtrl::GetLineColor
- AFXCMN/CTreeCtrl::GetNextItem
- AFXCMN/CTreeCtrl::GetNextSiblingItem
- AFXCMN/CTreeCtrl::GetNextVisibleItem
- AFXCMN/CTreeCtrl::GetParentItem
- AFXCMN/CTreeCtrl::GetPrevSiblingItem
- AFXCMN/CTreeCtrl::GetPrevVisibleItem
- AFXCMN/CTreeCtrl::GetRootItem
- AFXCMN/CTreeCtrl::GetScrollTime
- AFXCMN/CTreeCtrl::GetSelectedCount
- AFXCMN/CTreeCtrl::GetSelectedItem
- AFXCMN/CTreeCtrl::GetTextColor
- AFXCMN/CTreeCtrl::GetToolTips
- AFXCMN/CTreeCtrl::GetVisibleCount
- AFXCMN/CTreeCtrl::HitTest
- AFXCMN/CTreeCtrl::InsertItem
- AFXCMN/CTreeCtrl::ItemHasChildren
- AFXCMN/CTreeCtrl::MapAccIdToItem
- AFXCMN/CTreeCtrl::MapItemToAccID
- AFXCMN/CTreeCtrl::Select
- AFXCMN/CTreeCtrl::SelectDropTarget
- AFXCMN/CTreeCtrl::SelectItem
- AFXCMN/CTreeCtrl::SelectSetFirstVisible
- AFXCMN/CTreeCtrl::SetAutoscrollInfo
- AFXCMN/CTreeCtrl::SetBkColor
- AFXCMN/CTreeCtrl::SetCheck
- AFXCMN/CTreeCtrl::SetExtendedStyle
- AFXCMN/CTreeCtrl::SetImageList
- AFXCMN/CTreeCtrl::SetIndent
- AFXCMN/CTreeCtrl::SetInsertMark
- AFXCMN/CTreeCtrl::SetInsertMarkColor
- AFXCMN/CTreeCtrl::SetItem
- AFXCMN/CTreeCtrl::SetItemData
- AFXCMN/CTreeCtrl::SetItemExpandedImageIndex
- AFXCMN/CTreeCtrl::SetItemHeight
- AFXCMN/CTreeCtrl::SetItemImage
- AFXCMN/CTreeCtrl::SetItemState
- AFXCMN/CTreeCtrl::SetItemStateEx
- AFXCMN/CTreeCtrl::SetItemText
- AFXCMN/CTreeCtrl::SetLineColor
- AFXCMN/CTreeCtrl::SetScrollTime
- AFXCMN/CTreeCtrl::SetTextColor
- AFXCMN/CTreeCtrl::SetToolTips
- AFXCMN/CTreeCtrl::ShowInfoTip
- AFXCMN/CTreeCtrl::SortChildren
- AFXCMN/CTreeCtrl::SortChildrenCB
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeCtrl class
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7de12878d76e423e552abada088ec7a485bb263e
ms.lasthandoff: 04/01/2017

---
# <a name="ctreectrl-class"></a>CTreeCtrl Class
Предоставляет функциональные возможности стандартного элемента управления "представление в виде дерева" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTreeCtrl::CTreeCtrl](#ctreectrl)|Создает объект `CTreeCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTreeCtrl::Create](#create)|Создает дерево и прикрепляет его к `CTreeCtrl` объекта.|  
|[CTreeCtrl::CreateDragImage](#createdragimage)|Создает растровое изображение перетаскивания для элемента представления указанного дерева.|  
|[CTreeCtrl::CreateEx](#createex)|Создает дерево с указанным расширенные стили Windows и прикрепляет его к `CTreeCtrl` объекта.|  
|[CTreeCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы в элементе управления древовидного представления.|  
|[CTreeCtrl::DeleteItem](#deleteitem)|Удаляет элемент в дерево.|  
|[CTreeCtrl::EditLabel](#editlabel)|Изменение указанного дерева представления элемента на месте.|  
|[CTreeCtrl::EndEditLabelNow](#endeditlabelnow)|Отменяет операцию изменения метки элемента представления дерева в текущий элемент управления представления дерева.|  
|[CTreeCtrl::EnsureVisible](#ensurevisible)|Гарантирует, что элемент дерева является видимым в его управления иерархического представления.|  
|[CTreeCtrl::Expand](#expand)|Разворачивает или сворачивает дочерние элементы элемента представления указанного дерева.|  
|[CTreeCtrl::GetBkColor](#getbkcolor)|Получает текущий цвет фона элемента управления.|  
|[CTreeCtrl::GetCheck](#getcheck)|Получает состояние проверки элемента управления дерева.|  
|[CTreeCtrl::GetChildItem](#getchilditem)|Извлекает дочерний элемент указанного дерева.|  
|[CTreeCtrl::GetCount](#getcount)|Возвращает число элементов дерева, связанный с элементом управления представления дерева.|  
|[CTreeCtrl::GetDropHilightItem](#getdrophilightitem)|Возвращает целевой объект операции перетаскивания и вставки.|  
|[CTreeCtrl::GetEditControl](#geteditcontrol)|Извлекает дескриптор элемента управления редактирования, используемый для изменения отображаемых элементов указанного дерева.|  
|[CTreeCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, используется текущий элемент управления представления дерева.|  
|[CTreeCtrl::GetFirstVisibleItem](#getfirstvisibleitem)|Извлекает первый видимый элемент элемент указанного дерева.|  
|[CTreeCtrl::GetImageList](#getimagelist)|Извлекает маркер из списка изображений, связанного с элементом управления представления дерева.|  
|[CTreeCtrl::GetIndent](#getindent)|Возвращает смещение (в пикселях) элемента представления дерева из своего родителя.|  
|[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Получает цвет, используемый для рисования метка вставки для представления дерева.|  
|[CTreeCtrl::GetItem](#getitem)|Извлекает атрибуты элемент указанного дерева.|  
|[CTreeCtrl::GetItemData](#getitemdata)|Возвращает 32-разрядное значение конкретного приложения, связанные с элементом.|  
|[CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)|Возвращает индекс изображения для отображения указанного элемента текущего элемента представления дерева в развернутом состоянии.|  
|[CTreeCtrl::GetItemHeight](#getitemheight)|Извлекает текущую высоту элементов представления дерева.|  
|[CTreeCtrl::GetItemImage](#getitemimage)|Извлекает изображения, связанные с элементом.|  
|[CTreeCtrl::GetItemPartRect](#getitempartrect)|Возвращает прямоугольник, ограничивающий указанную часть указанного элемента в текущем элемента представления дерева.|  
|[CTreeCtrl::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник элемента представления дерева.|  
|[CTreeCtrl::GetItemState](#getitemstate)|Возвращает состояние объекта.|  
|[CTreeCtrl::GetItemStateEx](#getitemstateex)|Извлекает расширенные состояние указанного элемента в текущем элемента представления дерева.|  
|[CTreeCtrl::GetItemText](#getitemtext)|Возвращает текст элемента.|  
|[CTreeCtrl::GetLastVisibleItem](#getlastvisibleitem)|Извлекает расширенные последнего элемента текущего элемента представления дерева.|  
|[CTreeCtrl::GetLineColor](#getlinecolor)|Получает текущий цвет линии для элемента управления иерархического представления.|  
|[CTreeCtrl::GetNextItem](#getnextitem)|Получает следующий элемент представления дерева, соответствующий указанной связи.|  
|[CTreeCtrl::GetNextSiblingItem](#getnextsiblingitem)|Возвращает следующий одноуровневый элемент указанного дерева.|  
|[CTreeCtrl::GetNextVisibleItem](#getnextvisibleitem)|Получает следующий элемент видимым элемента представления указанного дерева.|  
|[CTreeCtrl::GetParentItem](#getparentitem)|Получает родительский элемент указанного дерева.|  
|[CTreeCtrl::GetPrevSiblingItem](#getprevsiblingitem)|Возвращает предыдущий одноуровневый элемент указанного дерева.|  
|[CTreeCtrl::GetPrevVisibleItem](#getprevvisibleitem)|Возвращает предыдущий элемент видимым элемента представления указанного дерева.|  
|[CTreeCtrl::GetRootItem](#getrootitem)|Возвращает корневой элемент дерева указанного представления.|  
|[CTreeCtrl::GetScrollTime](#getscrolltime)|Получает время максимальное прокрутки для элемента управления иерархического представления.|  
|[CTreeCtrl::GetSelectedCount](#getselectedcount)|Возвращает число выбранных элементов в текущем элемента представления дерева.|  
|[CTreeCtrl::GetSelectedItem](#getselecteditem)|Извлекает элемент текущего выбранного дерева.|  
|[CTreeCtrl::GetTextColor](#gettextcolor)|Получает текущий цвет текста элемента управления.|  
|[CTreeCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор для дочернего элемента управления всплывающей подсказки, используемый дерево.|  
|[CTreeCtrl::GetVisibleCount](#getvisiblecount)|Возвращает число отображается дерево элементов, связанных с дерево.|  
|[CTreeCtrl::HitTest](#hittest)|Возвращает текущую позицию курсора, связанные с `CTreeCtrl` объекта.|  
|[CTreeCtrl::InsertItem](#insertitem)|Вставляет элемент в дерево.|  
|[CTreeCtrl::ItemHasChildren](#itemhaschildren)|Возвращает ненулевое значение, если указанный элемент содержит дочерние элементы.|  
|[CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)|Сопоставляет идентификатор указанного специальных возможностей дескриптор для элемента представления дерева в текущий элемент управления представления дерева.|  
|[CTreeCtrl::MapItemToAccID](#mapitemtoaccid)|Сопоставляет заданный дескриптор элемента представления дерева в текущий элемент управления представления дерева к идентификатору специальных возможностей.|  
|[CTreeCtrl::Select](#select)|Выбирает прокрутке и перерисовывает элемент указанного дерева.|  
|[CTreeCtrl::SelectDropTarget](#selectdroptarget)|Перерисовывает элемент дерева как целевой объект операции перетаскивания и вставки.|  
|[CTreeCtrl::SelectItem](#selectitem)|Выбирает элемент указанного дерева.|  
|[CTreeCtrl::SelectSetFirstVisible](#selectsetfirstvisible)|Выбирает элемент указанного дерева в качестве первой видимой позиции.|  
|[CTreeCtrl::SetAutoscrollInfo](#setautoscrollinfo)|Задает скорость автопрокрутки текущего элемента управления представления дерева.|  
|[CTreeCtrl::SetBkColor](#setbkcolor)|Задает цвет фона элемента управления.|  
|[CTreeCtrl::SetCheck](#setcheck)|Задает состояние проверки элемента управления дерева.|  
|[CTreeCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для текущего элемента представления дерева.|  
|[CTreeCtrl::SetImageList](#setimagelist)|Задает дескриптор списка изображений, связанного с элементом управления представления дерева.|  
|[CTreeCtrl::SetIndent](#setindent)|Задает смещение (в пикселях) элемента представления дерева из своего родителя.|  
|[CTreeCtrl::SetInsertMark](#setinsertmark)|Задает знак вставки в дерево.|  
|[CTreeCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Задает цвет, используемый для рисования метка вставки для представления дерева.|  
|[CTreeCtrl::SetItem](#setitem)|Задает атрибуты элемент указанного дерева.|  
|[CTreeCtrl::SetItemData](#setitemdata)|Задает 32-разрядное значение конкретного приложения, связанные с элементом.|  
|[CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)|Задает индекс изображения для отображения указанного элемента текущего элемента представления дерева в развернутом состоянии.|  
|[CTreeCtrl::SetItemHeight](#setitemheight)|Задает высоту дерева Просмотр элементов.|  
|[CTreeCtrl::SetItemImage](#setitemimage)|Связывает изображений с элементом.|  
|[CTreeCtrl::SetItemState](#setitemstate)|Задает состояние объекта.|  
|[CTreeCtrl::SetItemStateEx](#setitemstateex)|Задает расширенные состояние указанного элемента в текущий элемент управления представления дерева.|  
|[CTreeCtrl::SetItemText](#setitemtext)|Задает текст элемента.|  
|[CTreeCtrl::SetLineColor](#setlinecolor)|Задает текущий цвет линии для элемента управления иерархического представления.|  
|[CTreeCtrl::SetScrollTime](#setscrolltime)|Задает время максимальное прокрутки для элемента управления иерархического представления.|  
|[CTreeCtrl::SetTextColor](#settextcolor)|Задает цвет текста элемента управления.|  
|[CTreeCtrl::SetToolTips](#settooltips)|Задает дочернего элемента управления иерархического представления элементов управления ToolTip.|  
|[CTreeCtrl::ShowInfoTip](#showinfotip)|Отображает подсказку для указанного элемента в текущий элемент управления представления дерева.|  
|[CTreeCtrl::SortChildren](#sortchildren)|Сортирует потомков заданного родительского элемента.|  
|[CTreeCtrl::SortChildrenCB](#sortchildrencb)|Сортирует потомков заданного родительского элемента с помощью функции сортировки определяется приложением.|  
  
## <a name="remarks"></a>Примечания  
 «Дерево» — это окно, которое отображает иерархический список элементов, таких как заголовки в документе, записи в индекс, файлы и каталоги на диске. Каждый элемент состоит из метки и необязательное растровое изображение, а каждый элемент может иметь список элементов, связанных с ним. Щелкнув элемент, пользователь может разворачивать и сворачивать суб-элементов связанного списка.  
  
 Этот элемент управления (и, следовательно, `CTreeCtrl` класс) доступен только для программы, работающие под Windows 98 и Windows NT версии 4 и более поздних.  
  
 Дополнительные сведения об использовании `CTreeCtrl`, см.:  
  
- [Элементы управления](../../mfc/controls-mfc.md)  
  
- [Использование CTreeCtrl](../../mfc/using-ctreectrl.md)  
  
- [Ссылка на представление элемента управления дерева](http://msdn.microsoft.com/library/windows/desktop/bb759988) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Статья базы знаний Q222905: Практическое руководство: Отображает контекстное меню для CTreeCtrl  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="create"></a>CTreeCtrl::Create  
 При указании дерево в шаблон диалогового окна, или если вы используете [CTreeView](../../mfc/reference/ctreeview-class.md), дерево элемента управления создается автоматически при создании диалогового окна или представления.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления иерархического представления. Применение стилей окна, описанной в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)и любое сочетание [стили элемента управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760013) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение элемента управления иерархического представления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления иерархического представления, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать древовидный элемент управления как дочернего окна другие окна, используйте **создать** функции-члена. При создании элемента управления дерева с помощью **создать**, необходимо передать его **WS_VISIBLE**, помимо других стили древовидного представления.  
  
 Создании `CTreeCtrl` в два этапа. Первый вызов конструктора, затем вызовите **создать**, который создает дерева и прикрепляет его к `CTreeCtrl` объекта.  
  
 Чтобы создать дерево с расширенные стили окна, вызовите [CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_1.cpp)]  
  
##  <a name="createex"></a>CTreeCtrl::CreateEx  
 Эта функция вызывается для создания элемента управления (дочернего окна) и связать его с `CTreeCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль элемента управления иерархического представления. Применение стилей окна, описанной в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)и любое сочетание [стили элемента управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760013) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="createdragimage"></a>CTreeCtrl::CreateDragImage  
 Эта функция вызывается для создания перетаскивания растровое изображение для данного элемента в дерево, создать списка изображений для изображения добавить точечный рисунок в список изображений.  
  
```  
CImageList* CreateDragImage(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор перетаскивать элемент дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на список изображений, в которую был добавлен перетаскивания растрового изображения, в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Приложение использует функции списка изображений для отображения изображения, когда элемент перетаскивается.  
  
 `CImageList` Объект является окончательным и его следует удалить после завершения. Пример:  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #2](../../mfc/reference/codesnippet/cpp/ctreectrl-class_2.cpp)]  
  
##  <a name="ctreectrl"></a>CTreeCtrl::CTreeCtrl  
 Создает объект `CTreeCtrl`.  
  
```  
CTreeCtrl();
```  
  
##  <a name="deleteallitems"></a>CTreeCtrl::DeleteAllItems  
 Вызывайте эту функцию, чтобы удалить все элементы в элементе управления иерархического представления.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #3](../../mfc/reference/codesnippet/cpp/ctreectrl-class_3.cpp)]  
  
##  <a name="deleteitem"></a>CTreeCtrl::DeleteItem  
 Эта функция вызывается для удаления элемента из элемента управления иерархического представления.  
  
```  
BOOL DeleteItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева для удаления. Если *hitem* имеет **TVI_ROOT** значения, будут удалены все элементы в элементе управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #4](../../mfc/reference/codesnippet/cpp/ctreectrl-class_4.cpp)]  
  
##  <a name="editlabel"></a>CTreeCtrl::EditLabel  
 Вызывайте эту функцию можно начать изменение на месте текста указанного элемента.  
  
```  
CEdit* EditLabel(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева, который нужно изменить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения указатель `CEdit` объект, который используется для редактирования текста элемента; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Редактирование достигается, заменив текст элемента управления Правка однострочный, содержащий текст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_5.cpp)]  
  
##  <a name="endeditlabelnow"></a>CTreeCtrl::EndEditLabelNow  
 Завершает операцию изменения метки элемента представления дерева в текущий элемент управления представления дерева.  
  
```  
BOOL EndEditLabelNow(BOOL fCancelWithoutSave);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fCancelWithoutSave`|`true`Чтобы отменить изменения элемента представления дерева до завершения операции изменения или `false` хотите сохранить изменения элемента представления дерева до завершения операции.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_ENDEDITLABELNOW](http://msdn.microsoft.com/library/windows/desktop/bb773564) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ensurevisible"></a>CTreeCtrl::EnsureVisible  
 Вызывайте эту функцию, чтобы убедиться, что элемент дерева является видимым.  
  
```  
BOOL EnsureVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор сделан видимым элемент дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если система прокручивать элементов в элементе управления "дерево" Убедитесь, что указанный элемент. В противном случае возвращает значение **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 При необходимости, функция расширяется родительский элемент или прокручивает элементе управления иерархического представления, таким образом, чтобы она видна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #6](../../mfc/reference/codesnippet/cpp/ctreectrl-class_6.cpp)]  
  
##  <a name="expand"></a>CTreeCtrl::Expand  
 Вызывайте эту функцию, чтобы развернуть или свернуть список дочерних элементов, если имеется, сопоставленный с элементом заданного родительского объекта.  
  
```  
BOOL Expand(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор расширяемого элемента дерева.  
  
 `nCode`  
 Флаг, указывающий тип выполняемое действие. Этот флаг может принимать одно из следующих значений:  
  
- `TVE_COLLAPSE`Сворачивание списка.  
  
- `TVE_COLLAPSERESET`Сворачивание списка и удаляет дочерние элементы. **TVIS_EXPANDEDONCE** Сбросить флаг состояния. Этот флаг должен использоваться с `TVE_COLLAPSE` флаг.  
  
- `TVE_EXPAND`При развертывании списка.  
  
- `TVE_TOGGLE`Сворачивание списка, если он развернут в настоящее время или развернуть его, если он свернут в настоящее время.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
##  <a name="getbkcolor"></a>CTreeCtrl::GetBkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773570), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее цвет фона текущего окна для элемента управления. Если это значение равно -1, элемент управления использует системный цвет окон. В этом случае можно использовать `::GetSysColor(COLOR_WINDOW)` для получения текущего цвета системы, используя элемент управления.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="getcheck"></a>CTreeCtrl::GetCheck  
 Вызовите эту функцию-член для получения состояния флажка элемента.  
  
```  
BOOL GetCheck(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 **HTREEITEM** о том, какие для получения сведений о состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если установлен флажок элемента управления дерева; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getchilditem"></a>CTreeCtrl::GetChildItem  
 Вызов эту функцию для получения дерева просмотреть элемент, является дочерним элементом элемента, заданного параметром `hItem`.  
  
```  
HTREEITEM GetChildItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор дочернего элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #7](../../mfc/reference/codesnippet/cpp/ctreectrl-class_7.cpp)]  
  
##  <a name="getcount"></a>CTreeCtrl::GetCount  
 Вызывайте эту функцию для получения количества элементов в элементе управления древовидного представления.  
  
```  
UINT GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления иерархического представления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #8](../../mfc/reference/codesnippet/cpp/ctreectrl-class_8.cpp)]  
  
##  <a name="getdrophilightitem"></a>CTreeCtrl::GetDropHilightItem  
 Вызывайте эту функцию для извлечения элемента, который является целевым объектом операции перетаскивания и вставки.  
  
```  
HTREEITEM GetDropHilightItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента, сбрасывается в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #9](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="geteditcontrol"></a>CTreeCtrl::GetEditControl  
 Эта функция вызывается для получения дескриптора элемента управления, используемого для редактирования текста элемента представления дерева.  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поле редактирования, используемый для редактирования текста элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #10](../../mfc/reference/codesnippet/cpp/ctreectrl-class_10.cpp)]  
  
##  <a name="getextendedstyle"></a>CTreeCtrl::GetExtendedStyle  
 Извлекает расширенные стили, используется текущий элемент управления представления дерева.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое содержит битовую комбинацию (OR) текущего элемента управления представления дерева расширенных стилей. Дополнительные сведения см. в разделе [дерево управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773580) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getfirstvisibleitem"></a>CTreeCtrl::GetFirstVisibleItem  
 Эта функция вызывается для получения первый видимый элемент управления иерархического представления.  
  
```  
HTREEITEM GetFirstVisibleItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор первой видимой позиции; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getimagelist"></a>CTreeCtrl::GetImageList  
 Эта функция вызывается для получения дескриптора обычный или состояние список изображений, связанных с элементе управления иерархического представления.  
  
```  
CImageList* GetImageList(UINT nImageList) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nImageList`  
 Тип списка изображений для извлечения. Список изображений может принимать одно из следующих значений:  
  
- `TVSIL_NORMAL`Извлекает список обычный образ, который содержит выбранные и невыбранные образы для элемента представления дерева.  
  
- `TVSIL_STATE`Извлекает состояние образа списка, которая содержит изображения для элементов представления дерева, которые находятся в состоянии, определяемые пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент управления списка изображений, в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в дерево может иметь пару помещаются растровые изображения, связанные с ним. Одно изображение отображается в том случае, если элемент выбран, а другой отображается, если элемент не выбран. Например элемент можно отобразить открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Дополнительные сведения о списках изображений см. в разделе [CImageList](../../mfc/reference/cimagelist-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl № 11](../../mfc/reference/codesnippet/cpp/ctreectrl-class_11.cpp)]  
  
##  <a name="getindent"></a>CTreeCtrl::GetIndent  
 Эта функция вызывается для получения размер в пикселях, что дочерние элементы отображаются с отступом относительно родительские элементы.  
  
```  
UINT GetIndent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Величину отступа измеряется в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #12](../../mfc/reference/codesnippet/cpp/ctreectrl-class_12.cpp)]  
  
##  <a name="getinsertmarkcolor"></a>CTreeCtrl::GetInsertMarkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773590), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее текущий цвет метки вставки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #13](../../mfc/reference/codesnippet/cpp/ctreectrl-class_13.cpp)]  
  
##  <a name="getitem"></a>CTreeCtrl::GetItem  
 Эта функция вызывается для получения атрибутов элемента представления указанного дерева.  
  
```  
BOOL GetItem(TVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdata"></a>CTreeCtrl::GetItemData  
 Эта функция вызывается для получения 32-разрядное значение конкретного приложения, связанный с указанным элементом.  
  
```  
DWORD_PTR GetItemData(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, данные которого требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение конкретного приложения, связанные с элемента, заданного параметром `hItem`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #14](../../mfc/reference/codesnippet/cpp/ctreectrl-class_14.cpp)]  
  
##  <a name="getitemexpandedimageindex"></a>CTreeCtrl::GetItemExpandedImageIndex  
 Возвращает индекс изображения для отображения указанного элемента текущего элемента представления дерева в развернутом состоянии.  
  
```  
int GetItemExpandedImageIndex(HTREEITEM hItem)const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления представления дерева.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения для отображения указанного элемента в развернутом состоянии.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сообщения, которое возвращает [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структура, описывающая элемент управления представления дерева, а затем этот метод извлекает `iExpandedImage` элемент из этой структуры.  
  
##  <a name="getitemheight"></a>CTreeCtrl::GetItemHeight  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773599), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT GetItemHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #15](../../mfc/reference/codesnippet/cpp/ctreectrl-class_15.cpp)]  
  
##  <a name="getitemimage"></a>CTreeCtrl::GetItemImage  
 Каждый элемент в дерево может иметь пару помещаются растровые изображения, связанные с ним.  
  
```  
BOOL GetItemImage(
    HTREEITEM hItem,  
    int& nImage,  
    int& nSelectedImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, изображение для которой требуется получить.  
  
 `nImage`  
 Целое число, получающий индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Целое число, получающий индекс изображения выбранного элемента в список изображений элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 То изображения появляются слева от метки элемента. Одно изображение отображается в том случае, если элемент выбран, а другой отображается, если элемент не выбран. Например элемент можно отобразить открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Эта функция вызывается для получения индекс изображения элемента и его выбранного образа в пределах списка изображений элемента управления иерархического представления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl № 16](../../mfc/reference/codesnippet/cpp/ctreectrl-class_16.cpp)]  
  
##  <a name="getitempartrect"></a>CTreeCtrl::GetItemPartRect  
 Возвращает прямоугольник, ограничивающий указанную часть указанного элемента в текущем элемента представления дерева.  
  
```  
BOOL GetItemPartRect(
    HTREEITEM hItem,   
    int nPart,   
    LPRECT lpRect)const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления представления дерева.|  
|[in] `nPart`|Идентификатор элемента. Должно быть присвоено `TVGIPR_BUTTON`.|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. В случае успешной структуры получает координат прямоугольника, определяемого части `hItem` и `nPart`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник графики связывает каждого элемента управления дерева. При каждом нажатии точки в этот прямоугольник, элемент считается *попаданий*. Этот метод возвращает самый большой прямоугольник, таким образом, что при щелчке точки в прямоугольнике элемент, определенный с `hItem` попаданий параметра.  
  
 Этот метод отправляет `TVM_GETITEMPARTRECT` сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [TreeView_GetItemPartRect](http://msdn.microsoft.com/library/windows/desktop/bb773847) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода используется идентификатор специальных возможностей и [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) метод для получения дескриптора для корневого элемента представления дерева. Затем в примере используется дескриптор и [CTreeCtrl::GetItemPartRect](#getitempartrect) метод 3D прямоугольник вокруг элемента. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Мы использовали [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) способ сопоставления дерево корневой элемент с идентификатором, специальных возможностей.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="getitemrect"></a>CTreeCtrl::GetItemRect  
 Эта функция вызывается для получения прямоугольника, ограничивающего `hItem` и определить, является ли он видимым или нет.  
  
```  
BOOL GetItemRect(
    HTREEITEM hItem,  
    LPRECT lpRect,  
    BOOL bTextOnly) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента управления представления дерева.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающего прямоугольника. Координаты указываются относительно левого верхнего угла элемента управления иерархического представления.  
  
 *bTextOnly*  
 Если этот параметр имеет ненулевое значение, ограничивающий прямоугольник включает только текст элемента. В противном случае она включает всей строки, который занимает элемента в элементе управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если она видна, ограничивающий прямоугольник, содержащихся в `lpRect`. В противном случае — 0 с `lpRect` неинициализированным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl 17](../../mfc/reference/codesnippet/cpp/ctreectrl-class_19.cpp)]  
  
##  <a name="getitemstate"></a>CTreeCtrl::GetItemState  
 Возвращает состояние элемента, заданного параметром `hItem`.  
  
```  
UINT GetItemState(
    HTREEITEM hItem,  
    UINT nStateMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, состояние которой требуется получить.  
  
 `nStateMask`  
 Маска, определяющая один или несколько состояний, которые требуется получить. Дополнительные сведения о возможных значениях `nStateMask`, в описании **состояние** и **stateMask** члены [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** , содержащий значения, указанные в nStateMask побитовое или. Сведения о возможных значениях см. в разделе [CTreeCtrl::GetItem](#getitem). Чтобы найти значение для конкретного состояния, выполните побитовую операцию и значения состояния и возвращаемого значения, как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl 18](../../mfc/reference/codesnippet/cpp/ctreectrl-class_20.cpp)]  
  
##  <a name="getitemstateex"></a>CTreeCtrl::GetItemStateEx  
 Извлекает расширенные состояние указанного элемента в текущем элемента представления дерева.  
  
```  
UINT GetItemStateEx(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления представления дерева.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расширенные состояния элемента. Дополнительные сведения см. в разделе `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сообщения, которое возвращает [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуру, которая описывает элемент управления представления дерева и этот метод извлекает `uStateEx` элемент из этой структуры.  
  
##  <a name="getitemtext"></a>CTreeCtrl::GetItemText  
 Возвращает текст элемента, заданного параметром `hItem`.  
  
```  
CString GetItemText(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, текст которой требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий текст элемента.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetNextItem](#getnextitem).  
  
##  <a name="getlastvisibleitem"></a>CTreeCtrl::GetLastVisibleItem  
 Возвращает последний элемент неразвернутыми узла в текущий элемент управления представления дерева.  
  
```  
HTREEITEM GetLastVisibleItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор последнего элемента неразвернутыми узел, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETNEXTITEM](http://msdn.microsoft.com/library/windows/desktop/bb773622) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе `TVGN_LASTVISIBLE` флаг в `flag` параметр этого сообщения.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. В следующем примере используются один или несколько из этих переменных.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода Получает дескриптор последнего элемента узла неразвернутыми представление дерева, а затем выводит 3D прямоугольник вокруг элемента. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;6](../../mfc/reference/codesnippet/cpp/ctreectrl-class_21.cpp)]  
  
##  <a name="getlinecolor"></a>CTreeCtrl::GetLineColor  
 Эта функция-член реализует поведение сообщения win32 [TVM_GETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773619), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetLineColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет линии.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl 19](../../mfc/reference/codesnippet/cpp/ctreectrl-class_22.cpp)]  
  
##  <a name="getnextitem"></a>CTreeCtrl::GetNextItem  
 Вызов эту функцию для получения дерева просмотреть элемент, имеющий указанную связь, обозначенном `nCode` параметр в `hItem`.  
  
```  
HTREEITEM GetNextItem(
    HTREEITEM hItem,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
 `nCode`  
 Флаг, указывающий тип отношения для `hItem`. Этот флаг может принимать одно из следующих значений:  
  
- `TVGN_CARET`Получает текущий выбранный элемент.  
  
- `TVGN_CHILD`Возвращает первый дочерний элемент элемента, заданного по `hItem` параметр.  
  
- `TVGN_DROPHILITE`Возвращает элемент, который является целевым объектом операции перетаскивания и вставки.  
  
- `TVGN_FIRSTVISIBLE`Извлекает первый видимый элемент.  
  
- `TVGN_LASTVISIBLE`Извлекает расширенные последнего элемента в дереве. Это не получить последний элемент отображается в окне представления дерева.  
  
- `TVGN_NEXT`Получает следующий элемент того же уровня.  
  
- `TVGN_NEXTVISIBLE`Извлекает следующий видимый элемент, следующий указанный элемент.  
  
- `TVGN_PARENT`Извлекает родительское указанного элемента.  
  
- `TVGN_PREVIOUS`Возвращает предыдущий элемент того же уровня.  
  
- `TVGN_PREVIOUSVISIBLE`Извлекает первый видимый элемент, который предшествует указанного элемента.  
  
- `TVGN_ROOT`Возвращает первый дочерний элемент корневого элемента, частью которого является указанный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор следующего элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает **NULL** Если извлекаемого элемента является корневым узлом дерева. Например, если вы используете это сообщение с `TVGN_PARENT` флаг потомком первого уровня корневой узел дерева, возвратит сообщение **NULL**.  
  
### <a name="example"></a>Пример  
 Пример использования `GetNextItem` в цикле, в разделе [CTreeCtrl::DeleteItem](#deleteitem).  
  
 [!code-cpp[NVC_MFC_CTreeCtrl № 20](../../mfc/reference/codesnippet/cpp/ctreectrl-class_23.cpp)]  
  
##  <a name="getnextsiblingitem"></a>CTreeCtrl::GetNextSiblingItem  
 Эта функция вызывается для получения следующий одноуровневый элемент `hItem`.  
  
```  
HTREEITEM GetNextSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор к следующему элементу того же уровня. в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #21](../../mfc/reference/codesnippet/cpp/ctreectrl-class_24.cpp)]  
  
##  <a name="getnextvisibleitem"></a>CTreeCtrl::GetNextVisibleItem  
 Вызывайте эту функцию для извлечения следующего элемента видимой части `hItem`.  
  
```  
HTREEITEM GetNextVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор следующего видимого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getparentitem"></a>CTreeCtrl::GetParentItem  
 Эта функция вызывается для получения родительского элемента `hItem`.  
  
```  
HTREEITEM GetParentItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор родительского элемента; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает **NULL** Если родительский указанный элемент является корневым узлом дерева.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
##  <a name="getprevsiblingitem"></a>CTreeCtrl::GetPrevSiblingItem  
 Эта функция вызывается для получения предыдущий одноуровневый элемент `hItem`.  
  
```  
HTREEITEM GetPrevSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор предыдущего одноуровневого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #22](../../mfc/reference/codesnippet/cpp/ctreectrl-class_25.cpp)]  
  
##  <a name="getprevvisibleitem"></a>CTreeCtrl::GetPrevVisibleItem  
 Эта функция вызывается для получения предыдущей видимым элемент `hItem`.  
  
```  
HTREEITEM GetPrevVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор предыдущего видимого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #23](../../mfc/reference/codesnippet/cpp/ctreectrl-class_26.cpp)]  
  
##  <a name="getrootitem"></a>CTreeCtrl::GetRootItem  
 Эта функция вызывается для получения корневого элемента управления иерархического представления.  
  
```  
HTREEITEM GetRootItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор корневого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::EditLabel](#editlabel).  
  
##  <a name="getscrolltime"></a>CTreeCtrl::GetScrollTime  
 Вызовите эту функцию-член для получения времени максимальное прокрутки для элемента управления иерархического представления.  
  
```  
UINT GetScrollTime() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная прокрутка время в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения win32 [TVM_GETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773625), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getselectedcount"></a>CTreeCtrl::GetSelectedCount  
 Возвращает число выбранных элементов в текущем элемента представления дерева.  
  
```  
UINT GetSelectedCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число выбранных элементов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETSELECTEDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb773629) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getselecteditem"></a>CTreeCtrl::GetSelectedItem  
 Эта функция вызывается для получения текущего выделенного элемента управления иерархического представления.  
  
```  
HTREEITEM GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор выбранного элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #24](../../mfc/reference/codesnippet/cpp/ctreectrl-class_27.cpp)]  
  
##  <a name="gettextcolor"></a>CTreeCtrl::GetTextColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773633), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет текста. Если это значение равно -1, элемент управления использует системный цвет для цвета текста.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="gettooltips"></a>CTreeCtrl::GetToolTips  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773729), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, используемый в элементе управления иерархического представления. Если [создать](#create) функция-член использует стиль **TVS_NOTOOLTIPS**, подсказки не используются, и **NULL** возвращается.  
  
### <a name="remarks"></a>Примечания  
 Реализация MFC `GetToolTips` возвращает `CToolTipCtrl` объект, который используется в элементе управления иерархического представления, а не дескриптор для элемента управления всплывающей подсказки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #25](../../mfc/reference/codesnippet/cpp/ctreectrl-class_28.cpp)]  
  
##  <a name="getvisiblecount"></a>CTreeCtrl::GetVisibleCount  
 Вызывайте эту функцию, чтобы получить число видимых элементов в элементе управления древовидного представления.  
  
```  
UINT GetVisibleCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество видимых элементов в элементе управления иерархического представления; в противном случае - 1.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="hittest"></a>CTreeCtrl::HitTest  
 Вызывайте эту функцию, чтобы определить местоположение указанной точки относительно клиентской области элемента управления дерева.  
  
```  
HTREEITEM HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
  
HTREEITEM HitTest(TVHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Клиентские координаты точки для проверки.  
  
 `pFlags`  
 Указатель на целое число, который получает сведения о результатах проверки нажатия. Это может быть один или несколько значений в группе **флаги** элемента в разделе "Примечания".  
  
 `pHitTestInfo`  
 Адрес [TVHITTESTINFO будет СОДЕРЖАТЬ](http://msdn.microsoft.com/library/windows/desktop/bb773448) структуру, содержащую позиции нажатия и тестов, получает сведения о результатах проверки нажатия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента представления дерева, занимающий заданную точку или **NULL** Если ни один элемент занимает точке.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции `pt` параметр задает координаты точки для проверки. Функция возвращает дескриптор элемента в указанной точке или **NULL** Если ни один элемент занимает точке. Кроме того `pFlags` параметр содержит значение, указывающее местоположение указанной точки. Доступны следующие значения:  
  
|||  
|-|-|  
|Значение|Значение|  
|TVHT_ABOVE|Выше клиентской области.|  
|TVHT_BELOW|Ниже области клиента.|  
|TVHT_NOWHERE|В клиентской области, но находится ниже последнего элемента.|  
|TVHT_ONITEM|Растровое изображение или метку, связанную с элементом.|  
|TVHT_ONITEMBUTTON|На кнопке, связанные с элементом.|  
|TVHT_ONITEMICON|В растровое изображение, связанное с элементом.|  
|TVHT_ONITEMINDENT|В отступ, связанные с элементом.|  
|TVHT_ONITEMLABEL|Метки (string), связанные с элементом.|  
|TVHT_ONITEMRIGHT|В области справа от элемента.|  
|TVHT_ONITEMSTATEICON|Значок состояния для элемента представления дерева, находится в состоянии, определяемые пользователем.|  
|TVHT_TOLEFT|В левой части клиентской области.|  
|TVHT_TORIGHT|В правой части клиентской области.|  
|||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #26](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="insertitem"></a>CTreeCtrl::InsertItem  
 Эта функция вызывается для вставки нового элемента в элементе управления древовидного представления.  
  
```  
HTREEITEM InsertItem(LPTVINSERTSTRUCT lpInsertStruct);

 
HTREEITEM InsertItem(
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    HTREEITEM hParent,  
    HTREEITEM hInsertAfter);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);
```  
  
### <a name="parameters"></a>Параметры  
 *lpInsertStruct*  
 Указатель на `TVINSERTSTRUCT` , определяет атрибуты вставляемого элемента представления дерева.  
  
 `nMask`  
 Целое число, указывающее, какие атрибуты следует задать. В разделе `TVITEM` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpszItem`  
 Адрес строка, содержащая текст элемента.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в список изображений элемента управления иерархического представления.  
  
 `nState`  
 Задает значения для состояния элемента. Состояния элементов управления представления дерева см. в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список соответствующих состояний.  
  
 `nStateMask`  
 Указывает, какие состояния должны быть заданы. В разделе `TVITEM` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lParam`  
 32-разрядное значение конкретного приложения, связанный с элементом.  
  
 `hParent`  
 Дескриптор родительского вставленного элемента.  
  
 *hInsertAfter*  
 Дескриптор элементом, после которого вставляется новый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор нового элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 В примере ситуаций, в которых может потребоваться использовать каждой версии функции, при вставке элемента управления дерева.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #27](../../mfc/reference/codesnippet/cpp/ctreectrl-class_30.cpp)]  
  
##  <a name="itemhaschildren"></a>CTreeCtrl::ItemHasChildren  
 Эта функция позволяет определить, является ли заданный элемент дерева `hItem` есть дочерние элементы.  
  
```  
BOOL ItemHasChildren(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент дерева, заданные `hItem` есть дочерние элементы; 0, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если Да, можно использовать [CTreeCtrl::GetChildItem](#getchilditem) для получения этих дочерних элементов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetSelectedItem](#getselecteditem).  
  
##  <a name="mapaccidtoitem"></a>CTreeCtrl::MapAccIdToItem  
 Сопоставляет идентификатор указанного специальных возможностей дескриптор элемента представления дерева в текущий элемент управления представления дерева.  
  
```  
HTREEITEM MapAccIdToItem(UINT uAccId) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uAccId`|Идентификатор элемента в дерево элементов специальных возможностей.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для элемента представления дерева ( `HTREEITEM`), соответствующий `uAccId` параметра. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.  
  
### <a name="remarks"></a>Примечания  
 Специальные возможности — это приложения, помогающие людям с ограниченными возможностями использовать компьютеры. Используемый идентификатор специальных возможностей `IAccessible` интерфейс, чтобы уникальным образом указать элемент в окне. Дополнительные сведения об идентификаторах специальных возможностей поиска в разделе «Об активных специальных возможностей поддержки» на [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_MAPACCIDTOHTREEITEM](http://msdn.microsoft.com/library/windows/desktop/bb773734) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода используется идентификатор специальных возможностей и [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) метод для получения дескриптора для корневого элемента представления дерева. В этом примере дескриптор и [CTreeCtrl::GetItemPartRect](#getitempartrect) метод 3D прямоугольник вокруг элемента. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Мы использовали [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) способ сопоставления дерево корневой элемент с идентификатором, специальных возможностей.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="mapitemtoaccid"></a>CTreeCtrl::MapItemToAccID  
 Сопоставляет заданный дескриптор элемента представления дерева в текущий элемент управления представления дерева идентификатор специальных возможностей.  
  
```  
UINT MapItemToAccID(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента представления дерева в элементе управления. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор специальных возможностей, который соответствует `hItem` параметра.  
  
### <a name="remarks"></a>Примечания  
 Специальные возможности — это приложения, помогающие людям с ограниченными возможностями использовать компьютеры. Используемый идентификатор специальных возможностей `IAccessible` интерфейс, чтобы уникальным образом указать элемент в окне. Дополнительные сведения об идентификаторах специальных возможностей поиска в разделе «Об активных специальных возможностей поддержки» на [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_MAPHTREEITEMTOACCID](http://msdn.microsoft.com/library/windows/desktop/bb773735) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере Получает идентификатор элемента управления представления дерева. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Данный пример кода Получает уникальный идентификационный номер для страны или региона корневого узла.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctreectrl-class_31.cpp)]  
  
##  <a name="select"></a>CTreeCtrl::Select  
 Эта функция используется для выбора отображаемых элементов данного дерева, прокрутить элемент в представление или перерисовывает элемент в стиль, используемый для указания целевого объекта для операции перетаскивания и вставки.  
  
```  
BOOL Select(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
 `nCode`  
 Тип действия, выполняемого. Этот параметр может принимать одно из следующих значений:  
  
- `TVGN_CARET`Задает возможности выбора для данного элемента.  
  
- `TVGN_DROPHILITE`Перерисовывает заданного элемента в стиль, используемый для указания целевого объекта для операции перетаскивания и вставки.  
  
- `TVGN_FIRSTVISIBLE`Таким образом, чтобы данный элемент первой видимой позиции по вертикали прокручивает представлении в виде дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `nCode` содержит значение `TVGN_CARET`, родительское окно получает **TVN_SELCHANGING** и **TVN_SELCHANGED** сообщений уведомления. Кроме того Если указанный элемент является потомком свернутый родительский элемент, родительский список дочерних элементов расширяется для отображения указанного элемента. В этом случае родительское окно получает **TVN_ITEMEXPANDING** и **TVN_ITEMEXPANDED** сообщений уведомления.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::HitTest](#hittest).  
  
##  <a name="selectdroptarget"></a>CTreeCtrl::SelectDropTarget  
 Эта функция вызывается для перерисовки элемента в стиль, используемый для указания целевого объекта для операции перетаскивания и вставки.  
  
```  
BOOL SelectDropTarget(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #9](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="selectitem"></a>CTreeCtrl::SelectItem  
 Эта функция используется для выбора отображаемых элементов данного дерева.  
  
```  
BOOL SelectItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `hItem` — **NULL**, эта функция выбирает элемент отсутствует.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #26](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="selectsetfirstvisible"></a>CTreeCtrl::SelectSetFirstVisible  
 Эта функция вызывается для прокрутки по вертикали представлении в виде дерева, таким образом, чтобы данный элемент первой видимой позиции.  
  
```  
BOOL SelectSetFirstVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева должен быть задан как к первому элементу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция отправляет сообщение окну с `TVM_SELECTITEM` и `TVGN_FIRSTVISIBLE` сообщений параметров.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #28](../../mfc/reference/codesnippet/cpp/ctreectrl-class_32.cpp)]  
  
##  <a name="setautoscrollinfo"></a>CTreeCtrl::SetAutoscrollInfo  
 Задает скорость автопрокрутки текущего элемента управления представления дерева.  
  
```  
BOOL SetAutoscrollInfo(
    UINT uPixelsPerSec,   
    UINT uUpdateTime);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uPixelsPerSec`|Количество пикселей, в секунду для прокрутки.|  
|[in] `uUpdateTime`|Временной интервал между обновлениями элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `true`.  
  
### <a name="remarks"></a>Примечания  
 Параметры автоматической прокрутки используются для прокрутку и отобразить элемент, который в настоящее время не является видимым. Элемент управления представления дерева должен иметь `TVS_EX_AUTOHSCROLL` расширенный стиль, который описан в [расширенные стили для элемента управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
 Этот метод отправляет [TVM_SETAUTOSCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb773738) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает поведение автопрокрутки текущего элемента управления представления дерева. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Мы намеренно внесены элемента представления дерева узкий, чтобы автоматически нужно прокручивать экран для отображения элемента дерева, который находится в фокусе. В примере кода задается древовидный элемент управления для автоматической прокрутки 30 пикселей в секунду каждые 5 секунд, пока не будет виден элемент дерева.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/ctreectrl-class_33.cpp)]  
  
##  <a name="setbkcolor"></a>CTreeCtrl::SetBkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773741), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** значение, содержащее новый цвет фона. Если это значение равно -1, элемент управления вернется к использованию системный цвет заливки фона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет текста. Если это значение равно -1, элемент управления использует системный цвет для цвета текста.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="setcheck"></a>CTreeCtrl::SetCheck  
 Вызовите эту функцию-член для задания состояния проверки для элемента управления дерева.  
  
```  
BOOL SetCheck(
    HTREEITEM hItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 **HTREEITEM** получать изменение состояния проверки.  
  
 `fCheck`  
 Указывает, будет ли элемент управления дерева отмечать флажком. По умолчанию `SetCheck` задает элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если установлен флажок элемента управления дерева ( `fCheck` значение **TRUE**), элемент отображается с флажком рядом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #29](../../mfc/reference/codesnippet/cpp/ctreectrl-class_34.cpp)]  
  
### <a name="example"></a>Пример  
 Чтобы использовать флажки, задайте TVS_CHECKBOXES перед заполнением в элементе управления иерархического представления.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #30](../../mfc/reference/codesnippet/cpp/ctreectrl-class_35.cpp)]  
  
##  <a name="setextendedstyle"></a>CTreeCtrl::SetExtendedStyle  
 Задает расширенные стили для текущего элемента представления дерева.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,   
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwExMask`|Битовая маска, определяющая, какие стили в текущий элемент управления представления дерева затрагиваются этим методом. Если этот параметр равен нулю, он игнорируется и значение `dwExStyles` для элемента представления дерева назначен параметр.<br /><br /> Укажите ноль или побитовое сочетание (OR) стили, описанные в [дерево управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb759981).|  
|[in] `dwExStyles`|Битовая маска, определяющая, какие стили в виде дерева элемента управления установите или снимите флажок.<br /><br /> Чтобы задать сочетание стилей, укажите побитовое сочетание (OR) стили, описанные в [дерево управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb759981). Чтобы очистить набор стилей, укажите ноль.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее предыдущего расширенные стили элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает стили, заданные в `dwExMask` параметра, затем устанавливает стили, заданные в `dwExStyles` параметра. Расширенные стили, которые соответствуют битам в `dwExMask` изменения.  
  
 Этот метод отправляет [TVM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773744) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода добавляется `TVS_EX_AUTOHSCROLL` расширенный стиль с текущим элементом управления представления дерева. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Мы намеренно внесены элемента представления дерева узкий, чтобы автоматически нужно прокручивать экран для отображения элемента дерева, который находится в фокусе.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctreectrl-class_36.cpp)]  
  
##  <a name="setimagelist"></a>CTreeCtrl::SetImageList  
 Вызовите эту функцию для задания с обычным или состояние списка изображений для дерева просмотра элемента управления и перерисовки элемента управления с помощью новых образов.  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на список изображений для назначения. Если `pImageList` — **NULL**, будут удалены все изображения из элемента управления иерархического представления.  
  
 `nImageListType`  
 Тип списка изображений для задания. Список изображений может принимать одно из следующих значений:  
  
- `TVSIL_NORMAL`Задает список изображений, обычный, который содержит выбранные и невыбранные образы для элемента представления дерева. Это состояние необходимо использовать для наложения изображений.  
  
- `TVSIL_STATE`Задает список изображений состояния, который содержит изображения для элементов представления дерева, которые находятся в состоянии, определяемые пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на изображения списке выше, при его наличии; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetImageList](#getimagelist).  
  
##  <a name="setindent"></a>CTreeCtrl::SetIndent  
 Вызывайте эту функцию, чтобы задать ширину отступа для дерево и перерисовки элемента управления, чтобы отразить новую ширину.  
  
```  
void SetIndent(UINT nIndent);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndent`  
 Ширина в пикселях отступы. Если `nIndent` меньше, чем минимальная ширина системные, новая ширина присвоено минимальное системные.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetIndent](#getindent).  
  
##  <a name="setinsertmark"></a>CTreeCtrl::SetInsertMark  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb773753), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetInsertMark(
    HTREEITEM hItem,  
    BOOL fAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 **HTREEITEM** , указывающий, в какой элемент будет помещен метка вставки. Если этот аргумент является **NULL**, метка вставки удаляется.  
  
 *fAfter*  
 **BOOL** значение, указывающее, если знак вставки помещается перед или после указанного элемента. Если этот аргумент не равен нулю, метка вставки будут располагаться после элемента. Если этот аргумент равен нулю, метка вставки будут располагаться перед элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #31](../../mfc/reference/codesnippet/cpp/ctreectrl-class_37.cpp)]  
  
##  <a name="setinsertmarkcolor"></a>CTreeCtrl::SetInsertMarkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773755), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Объект **COLORREF** значение, содержащее новый цвет метки вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее предыдущий цвет метки вставки.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor).  
  
##  <a name="setitem"></a>CTreeCtrl::SetItem  
 Вызывайте эту функцию, чтобы задать атрибуты элемента представления указанного дерева.  
  
```  
BOOL SetItem(TVITEM* pItem);

 
BOOL SetItem(
    HTREEITEM hItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) атрибуты структуру, содержащую новый элемент, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `hItem`  
 Дескриптор элемента, атрибуты которого должны быть заданы. В разделе **hItem** членом `TVITEM` структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nMask`  
 Целое число, указывающее, какие атрибуты следует задать. В разделе **маска** членом `TVITEM` структуры.  
  
 `lpszItem`  
 Адрес строка, содержащая текст элемента.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления. В разделе `iImage` членом `TVITEM` структуры.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в список изображений элемента управления иерархического представления. В разделе **iSelectedImage** членом `TVITEM` структуры.  
  
 `nState`  
 Задает значения для состояния элемента. В разделе **состояние** членом `TVITEM` структуры.  
  
 `nStateMask`  
 Указывает, какие состояния должны быть заданы. В разделе **stateMask** членом `TVITEM` структуры.  
  
 `lParam`  
 32-разрядное значение конкретного приложения, связанный с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 В `TVITEM` структуры **hItem** член определяет элемент и **маска** элемент указывает, какие атрибуты следует задать.  
  
 Если **маска** член или `nMask` указывает `TVIF_TEXT` значение, **pszText** члена или `lpszItem` является адрес строки с завершающим нулем и **cchTextMax** элемент обрабатывается. Если **маска** (или `nMask`) указывает `TVIF_STATE` значение, **stateMask** члена или `nStateMask` параметр указывает, какой элемент состояний для изменения и **состояние** члена или `nState` параметр содержит значения для этих состояний.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #32](../../mfc/reference/codesnippet/cpp/ctreectrl-class_38.cpp)]  
  
##  <a name="setitemdata"></a>CTreeCtrl::SetItemData  
 Вызывайте эту функцию, чтобы установить 32-разрядное значение конкретного приложения, связанный с указанным элементом.  
  
```  
BOOL SetItemData(
    HTREEITEM hItem,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, данные которого требуется получить.  
  
 `dwData`  
 32-разрядное значение конкретного приложения, связанные с элемента, заданного параметром `hItem`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #33](../../mfc/reference/codesnippet/cpp/ctreectrl-class_39.cpp)]  
  
##  <a name="setitemexpandedimageindex"></a>CTreeCtrl::SetItemExpandedImageIndex  
 Задает индекс изображения для отображения указанного элемента текущего элемента представления дерева в развернутом состоянии.  
  
```  
BOOL SetItemExpandedImageIndex(
    HTREEITEM hItem,   
    int iExpandedImage);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления представления дерева.|  
|[in] `iExpandedImage`|Индекс изображения для отображения указанного элемента в развернутом состоянии.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот метод назначает `iExpandedImage` параметр `iExpandedImage` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры, а затем использует эту структуру в сообщении.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 Пример кода является тривиальным тест для определения, является ли [CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex) метод возвращает значение, установленное [CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex) метод. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;8](../../mfc/reference/codesnippet/cpp/ctreectrl-class_40.cpp)]  
  
##  <a name="setitemheight"></a>CTreeCtrl::SetItemHeight  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773761), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT SetItemHeight(SHORT cyHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `cyHeight`  
 Задает новую высоту каждого элемента в представлении дерева в пикселях. Если этот аргумент меньше высоты изображения, он будет задать высоту изображения. Если этот аргумент не совпадает, то значение будет округлено до ближайшего значения, даже. Если этот аргумент равен -1, элемент управления вернется к использованию его высота элемента по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота предыдущих элементов, в пикселях.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetItemHeight](#getitemheight).  
  
##  <a name="setitemimage"></a>CTreeCtrl::SetItemImage  
 Связывает изображений с элементом.  
  
```  
BOOL SetItemImage(
    HTREEITEM hItem,  
    int nImage,  
    int nSelectedImage);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор для задается, изображение для элемента.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в список изображений элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в дерево может иметь пару помещаются растровые изображения, связанные с ним. То изображения появляются слева от метки элемента. Одно изображение отображается в том случае, если элемент выбран, а другой отображается, если элемент не выбран. Например элемент можно отобразить открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Вызывайте эту функцию, чтобы задать индекс изображения элемента и его выбранного образа в пределах списка изображений элемента управления иерархического представления.  
  
 Дополнительные сведения об образах см. в разделе [CImageList](../../mfc/reference/cimagelist-class.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetItemImage](#getitemimage).  
  
##  <a name="setitemstate"></a>CTreeCtrl::SetItemState  
 Задает состояние элемента, заданного параметром `hItem`.  
  
```  
BOOL SetItemState(
    HTREEITEM hItem,  
    UINT nState,  
    UINT nStateMask);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, состояние которой требуется задать.  
  
 `nState`  
 Указывает новые состояния для элемента.  
  
 `nStateMask`  
 Указывает, какие состояния будут изменены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сведения о состояниях см. в разделе [CTreeCtrl::GetItem](#getitem).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetItemState](#getitemstate).  
  
##  <a name="setitemstateex"></a>CTreeCtrl::SetItemStateEx  
 Задает расширенные состояние указанного элемента в текущий элемент управления представления дерева.  
  
```  
BOOL SetItemStateEx(
    HTREEITEM hItem,   
    UINT uStateEx);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления представления дерева.|  
|[in] `uStateEx`|Расширенные состояния элемента. Дополнительные сведения см. в разделе `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот метод назначает `uStateEx` параметр `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры, а затем использует эту структуру в сообщении.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_treeCtrl`, который используется для доступа к текущей элемента представления дерева. В примере кода также определяет целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает элемента представления дерева в отключенном состоянии. В предыдущем разделе в примере кода, который не отображается, мы создали дерево, состоит из корневого узла страны или региона для США, вложенные узлы для состояний Пенсильвания и Вашингтона и дерево элементов для тех городов, в этих состояниях. Данный пример кода задает Пенсильвания узел в отключенном состоянии.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctreectrl-class_41.cpp)]  
  
##  <a name="setitemtext"></a>CTreeCtrl::SetItemText  
 Задает текст элемента, заданного параметром `hItem`.  
  
```  
BOOL SetItemText(
    HTREEITEM hItem,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, текст которого требуется задать.  
  
 `lpszItem`  
 Адрес строка, содержащая новый текст для элемента  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #34](../../mfc/reference/codesnippet/cpp/ctreectrl-class_42.cpp)]  
  
##  <a name="setlinecolor"></a>CTreeCtrl::SetLineColor  
 Вызовите эту функцию-член для задайте цвет текущей строки в элементе управления иерархического представления.  
  
```  
COLORREF SetLineColor(COLORREF clrNew = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Новый цвет линии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий цвет линии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения win32 [TVM_SETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773764), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #35](../../mfc/reference/codesnippet/cpp/ctreectrl-class_43.cpp)]  
  
##  <a name="setscrolltime"></a>CTreeCtrl::SetScrollTime  
 Вызовите эту функцию-член для установки времени на максимально прокрутки для элемента управления иерархического представления.  
  
```  
UINT SetScrollTime(UINT uScrollTime);
```  
  
### <a name="parameters"></a>Параметры  
 *uScrollTime*  
 Новой прокрутки максимальное время в миллисекундах. Если это значение меньше 100, он будет округляется до 100.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие прокрутки максимальное время в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения win32 [TVM_SETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773767), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settextcolor"></a>CTreeCtrl::SetTextColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773769), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** значение, содержащее новый цвет текста. Если этот аргумент равен -1, элемент управления вернется к использованию системный цвет для цвета текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее на предыдущий цвет текста. Если это значение равно -1, элемент управления системный цвет для использовалась цвет текста.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #36](../../mfc/reference/codesnippet/cpp/ctreectrl-class_44.cpp)]  
  
##  <a name="settooltips"></a>CTreeCtrl::SetToolTips  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773772), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта, который будет использоваться в элементе управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, содержащий ранее использовался с помощью элемента управления всплывающей подсказки или **NULL** если подсказки не использовались ранее.  
  
### <a name="remarks"></a>Примечания  
 Для того чтобы использовать подсказки, указать **TVS_NOTOOLTIPS** стиля при создании `CTreeCtrl` объекта.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CTreeCtrl::GetToolTips](#gettooltips).  
  
##  <a name="showinfotip"></a>CTreeCtrl::ShowInfoTip  
 Отображает подсказку для указанного элемента в текущий элемент управления представления дерева.  
  
```  
void ShowInfoTip(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор для элемента представления дерева в элементе управления. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о различиях между подсказки и всплывающих подсказках найдите раздел «Подсказки и всплывающих подсказках» в [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_SHOWINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb773779) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sortchildren"></a>CTreeCtrl::SortChildren  
 Вызывайте эту функцию, чтобы отсортировать в алфавитном порядке дочерние элементы данного родительского элемента в элементе управления древовидного представления.  
  
```  
BOOL SortChildren(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор родительского элемента, чьи дочерние элементы должны быть отсортированы. Если `hItem` — **NULL**, сортировка будет продолжена из корневого элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `SortChildren`не обращаться дерева. только дочерние элементы `hItem` будут отсортированы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #37](../../mfc/reference/codesnippet/cpp/ctreectrl-class_45.cpp)]  
  
##  <a name="sortchildrencb"></a>CTreeCtrl::SortChildrenCB  
 Эта функция используется для сортировки элементов представления дерева, используя функцию обратного вызова, определяемые приложением, которая сравнивает элементы.  
  
```  
BOOL SortChildrenCB(LPTVSORTCB pSort);
```  
  
### <a name="parameters"></a>Параметры  
 *pSort*  
 Указатель на [TVSORTCB](http://msdn.microsoft.com/library/windows/desktop/bb773462) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция сравнения структуры, **lpfnCompare**, должен возвращать отрицательное значение, если первый элемент должен находиться перед второй, положительное значение, если первый элемент должен следовать за секунду, или нуль, если два элемента эквивалентны.  
  
 `lParam1` И `lParam2` параметров соответствуют **lParam** членом [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуры двух элементов сравниваемых. `lParamSort` Параметр соответствует параметру **lParam** членом `TV_SORTCB` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl #38](../../mfc/reference/codesnippet/cpp/ctreectrl-class_46.cpp)]  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #39](../../mfc/reference/codesnippet/cpp/ctreectrl-class_47.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CImageList](../../mfc/reference/cimagelist-class.md)

