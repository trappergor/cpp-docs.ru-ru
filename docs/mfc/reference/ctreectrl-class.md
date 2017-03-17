---
title: "Класс CTreeCtrl | Документы Microsoft"
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5341367b44540e2d0991fd61e52611826bbdcda1
ms.lasthandoff: 02/24/2017

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
|[CTreeCtrl::Create](#create)|Создает дерево и присоединяет его к `CTreeCtrl` объекта.|  
|[CTreeCtrl::CreateDragImage](#createdragimage)|Создает растровое изображение перетаскивания для элемента представления указанного дерева.|  
|[CTreeCtrl::CreateEx](#createex)|Создает дерево с указанным расширенные стили Windows и присоединяет его к `CTreeCtrl` объекта.|  
|[CTreeCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы в элементе управления древовидного представления.|  
|[CTreeCtrl::DeleteItem](#deleteitem)|Удаляет элемент в дерево.|  
|[CTreeCtrl::EditLabel](#editlabel)|Изменение указанного дерева представления элемента на месте.|  
|[CTreeCtrl::EndEditLabelNow](#endeditlabelnow)|Отменяет операцию изменения метки элемента дерево в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::EnsureVisible](#ensurevisible)|Гарантирует, что элемент дерева является видимым в его управления иерархического представления.|  
|[CTreeCtrl::Expand](#expand)|Разворачивает или сворачивает дочерние элементы элемента указанного дерева представления.|  
|[CTreeCtrl::GetBkColor](#getbkcolor)|Получает текущий цвет фона элемента управления.|  
|[CTreeCtrl::GetCheck](#getcheck)|Возвращает состояние проверки элемента дерева элемента управления.|  
|[CTreeCtrl::GetChildItem](#getchilditem)|Извлекает дочерний элемент указанного дерева.|  
|[CTreeCtrl::GetCount](#getcount)|Получает число элементов дерева, связанную с элементом управления представления дерева.|  
|[CTreeCtrl::GetDropHilightItem](#getdrophilightitem)|Возвращает целевой объект операции и перетаскивания.|  
|[CTreeCtrl::GetEditControl](#geteditcontrol)|Получает дескриптор элемента управления, используемый для редактирования элемента представления указанного дерева.|  
|[CTreeCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, используя текущий элемент управления иерархического представления.|  
|[CTreeCtrl::GetFirstVisibleItem](#getfirstvisibleitem)|Возвращает первый видимый элемент элемент указанного дерева.|  
|[CTreeCtrl::GetImageList](#getimagelist)|Получает дескриптор списка изображений, связанного с элементом управления представления дерева.|  
|[CTreeCtrl::GetIndent](#getindent)|Возвращает смещение (в пикселях) элемент дерева от своего родительского объекта.|  
|[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Получает цвет, используемый для рисования знак вставки для древовидного представления.|  
|[CTreeCtrl::GetItem](#getitem)|Извлекает атрибуты элемент указанного дерева.|  
|[CTreeCtrl::GetItemData](#getitemdata)|Возвращает 32-разрядное значение конкретного приложения, связанные с элементом.|  
|[CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)|Возвращает индекс изображения, отображаемого в развернутом состоянии после указанного элемента текущего элемента управления иерархического представления.|  
|[CTreeCtrl::GetItemHeight](#getitemheight)|Извлекает из текущей высоты элементов представления дерева.|  
|[CTreeCtrl::GetItemImage](#getitemimage)|Извлекает изображения, связанные с элементом.|  
|[CTreeCtrl::GetItemPartRect](#getitempartrect)|Возвращает прямоугольник, ограничивающий указанную часть указанного элемента в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::GetItemRect](#getitemrect)|Возвращает прямоугольник, ограничивающий элемент дерева.|  
|[CTreeCtrl::GetItemState](#getitemstate)|Возвращает состояние элемента.|  
|[CTreeCtrl::GetItemStateEx](#getitemstateex)|Извлекает расширенные состояние указанного элемента в элементе управления иерархического представления текущей.|  
|[CTreeCtrl::GetItemText](#getitemtext)|Возвращает текст элемента.|  
|[CTreeCtrl::GetLastVisibleItem](#getlastvisibleitem)|Получает последний развернутый элемент в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::GetLineColor](#getlinecolor)|Получает текущий цвет линии для элемента управления иерархического представления.|  
|[CTreeCtrl::GetNextItem](#getnextitem)|Получает указанное отношение соответствует элемент представления дерева.|  
|[CTreeCtrl::GetNextSiblingItem](#getnextsiblingitem)|Возвращает следующий одноуровневый элемент указанного дерева.|  
|[CTreeCtrl::GetNextVisibleItem](#getnextvisibleitem)|Получает следующий элемент отображается представление элемента указанного дерева.|  
|[CTreeCtrl::GetParentItem](#getparentitem)|Получает родительский элемент указанного дерева.|  
|[CTreeCtrl::GetPrevSiblingItem](#getprevsiblingitem)|Возвращает предыдущий одноуровневый элемент указанного дерева.|  
|[CTreeCtrl::GetPrevVisibleItem](#getprevvisibleitem)|Возвращает предыдущий элемент отображается представление элемента указанного дерева.|  
|[CTreeCtrl::GetRootItem](#getrootitem)|Возвращает корневой элемент дерева указанного представления.|  
|[CTreeCtrl::GetScrollTime](#getscrolltime)|Получает время максимальной прокрутки для элемента управления иерархического представления.|  
|[CTreeCtrl::GetSelectedCount](#getselectedcount)|Получает число выбранных элементов в элементе управления иерархического представления текущей.|  
|[CTreeCtrl::GetSelectedItem](#getselecteditem)|Извлекает элемент текущего выбранного дерева.|  
|[CTreeCtrl::GetTextColor](#gettextcolor)|Получает текущий цвет текста элемента управления.|  
|[CTreeCtrl::GetToolTips](#gettooltips)|Получает дескриптор для дочернего элемента управления всплывающей подсказки, используемый управления иерархического представления.|  
|[CTreeCtrl::GetVisibleCount](#getvisiblecount)|Получает число элементов отображается дерево, связанную с элементом управления представления дерева.|  
|[CTreeCtrl::HitTest](#hittest)|Возвращает текущую позицию курсора, связанные с `CTreeCtrl` объекта.|  
|[CTreeCtrl::InsertItem](#insertitem)|Вставляет новый элемент в дерево.|  
|[CTreeCtrl::ItemHasChildren](#itemhaschildren)|Возвращает ненулевое значение, если указанный элемент содержит дочерние элементы.|  
|[CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)|Сопоставляет идентификатор указанного специальных дескриптор в дереве элемент в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::MapItemToAccID](#mapitemtoaccid)|Сопоставляет указанный дескриптор дерева-элемент в текущий элемент управления иерархического представления с идентификатором специальных возможностей.|  
|[CTreeCtrl::Select](#select)|Выбирает прокрутке и перерисовывает элемент указанного дерева.|  
|[CTreeCtrl::SelectDropTarget](#selectdroptarget)|Перерисовывает элемент дерева как целевой объект операции и перетаскивания.|  
|[CTreeCtrl::SelectItem](#selectitem)|Выбирает элемент указанного дерева.|  
|[CTreeCtrl::SelectSetFirstVisible](#selectsetfirstvisible)|Выбирает элемент указанного дерева в качестве первой видимой позиции.|  
|[CTreeCtrl::SetAutoscrollInfo](#setautoscrollinfo)|Задает скорость autoscroll текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetBkColor](#setbkcolor)|Задает цвет фона элемента управления.|  
|[CTreeCtrl::SetCheck](#setcheck)|Задает состояние проверки элемента управления дерева.|  
|[CTreeCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetImageList](#setimagelist)|Задает дескриптор списка изображений, связанного с элементом управления представления дерева.|  
|[CTreeCtrl::SetIndent](#setindent)|Задает смещение (в пикселях) элемент дерева от своего родительского объекта.|  
|[CTreeCtrl::SetInsertMark](#setinsertmark)|Задает знак вставки в дерево.|  
|[CTreeCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Задает цвет, используемый для рисования знак вставки для древовидного представления.|  
|[CTreeCtrl::SetItem](#setitem)|Задает атрибуты элемент указанного дерева.|  
|[CTreeCtrl::SetItemData](#setitemdata)|Задает 32-разрядное значение конкретного приложения, связанные с элементом.|  
|[CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)|Задает индекс изображения, отображаемого в развернутом состоянии после указанного элемента текущего элемента управления иерархического представления.|  
|[CTreeCtrl::SetItemHeight](#setitemheight)|Задает высоту дерева Просмотр элементов.|  
|[CTreeCtrl::SetItemImage](#setitemimage)|Связывает изображений с элементом.|  
|[CTreeCtrl::SetItemState](#setitemstate)|Задает состояние объекта.|  
|[CTreeCtrl::SetItemStateEx](#setitemstateex)|Задает расширенные состояние указанного элемента в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::SetItemText](#setitemtext)|Задает текст элемента.|  
|[CTreeCtrl::SetLineColor](#setlinecolor)|Задает текущий цвет линии для элемента управления иерархического представления.|  
|[CTreeCtrl::SetScrollTime](#setscrolltime)|Задает время максимальной прокрутки для элемента управления иерархического представления.|  
|[CTreeCtrl::SetTextColor](#settextcolor)|Задает цвет текста элемента управления.|  
|[CTreeCtrl::SetToolTips](#settooltips)|Задает дочерний элемент управления представления дерева элемента управления всплывающей подсказки.|  
|[CTreeCtrl::ShowInfoTip](#showinfotip)|Отображает всплывающую подсказку для указанного элемента в текущий элемент управления иерархического представления.|  
|[CTreeCtrl::SortChildren](#sortchildren)|Сортирует потомков заданного родительского элемента.|  
|[CTreeCtrl::SortChildrenCB](#sortchildrencb)|Сортирует потомков заданного родительского элемента с помощью функции сортировки определяется приложением.|  
  
## <a name="remarks"></a>Примечания  
 «Дерево» — это окно, которое отображает иерархический список элементов, таких как заголовков в документе, записи в индексе, или файлы и каталоги на диске. Каждый элемент состоит из метки и необязательный растровый рисунок, и каждый элемент может иметь список элементов, связанных с ним. Щелкнув элемент, пользователь может разворачивать и сворачивать связанного списка элементов.  
  
 Этот элемент управления (и, следовательно, `CTreeCtrl` класса) доступны только для программы, запущенные в Windows 98 и Windows NT версии 4 и более поздних версий.  
  
 Дополнительные сведения об использовании `CTreeCtrl`, см.:  
  
- [Элементы управления](../../mfc/controls-mfc.md)  
  
- [Использование CTreeCtrl](../../mfc/using-ctreectrl.md)  
  
- [Ссылка на элемент управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb759988) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Статья базы знаний Q222905: Практическое руководство: Отображение контекстного меню для CTreeCtrl  
  
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
 Задает стиль элемента управления иерархического представления. Применение стилей окна, описанные в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)и любое сочетание [стили элемента управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760013) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение элемента управления иерархического представления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительского окна элемента управления иерархического представления, обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать древовидный элемент управления как дочернего окна другие окна, используйте **создать** функции-члена. При создании дерева элемента управления с помощью **создать**, необходимо передать его **WS_VISIBLE**, помимо других стили древовидного представления.  
  
 Создании `CTreeCtrl` в два этапа. Первый вызов конструктора, затем вызовите **создать**, который создает дерева и присоединяет его к `CTreeCtrl` объекта.  
  
 Чтобы создать дерево с расширенные стили окна, вызовите [CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_1.cpp)]  
  
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
 Задает стиль элемента управления иерархического представления. Применение стилей окна, описанные в [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)и любое сочетание [стили элемента управления представления дерева](http://msdn.microsoft.com/library/windows/desktop/bb760013) как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="createdragimage"></a>CTreeCtrl::CreateDragImage  
 Эта функция вызывается для создания перетаскивания растровое изображение для данного элемента в элементе управления древовидного представления, Создание списка изображений для изображения и добавить точечный рисунок в список изображений.  
  
```  
CImageList* CreateDragImage(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева можно перетаскивать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на список изображений, в которую был добавлен перетаскивания точечного рисунка, если выполнено успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Приложение использует функции списка изображений для отображения изображения при перетаскивания элемента.  
  
 `CImageList` Постоянный объект и его следует удалить после завершения. Пример:  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_2.cpp)]  
  
##  <a name="ctreectrl"></a>CTreeCtrl::CTreeCtrl  
 Создает объект `CTreeCtrl`.  
  
```  
CTreeCtrl();
```  
  
##  <a name="deleteallitems"></a>CTreeCtrl::DeleteAllItems  
 Эта функция вызывается для удаления всех элементов из элемента управления иерархического представления.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_3.cpp)]  
  
##  <a name="deleteitem"></a>CTreeCtrl::DeleteItem  
 Эта функция вызывается для удаления элемента из элемента управления иерархического представления.  
  
```  
BOOL DeleteItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор удаляемого элемента дерева. Если *hitem* имеет **TVI_ROOT** значение, все элементы будут удалены из элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_4.cpp)]  
  
##  <a name="editlabel"></a>CTreeCtrl::EditLabel  
 Эта функция вызывается для начала редактирования на месте текста указанного элемента.  
  
```  
CEdit* EditLabel(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева, который нужно изменить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха указатель `CEdit` объект, который используется для редактирования текста элемента; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Редактирование осуществляется, заменив текст элемента управления редактирования одной строки, содержащий текст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_5.cpp)]  
  
##  <a name="endeditlabelnow"></a>CTreeCtrl::EndEditLabelNow  
 Завершает операцию изменения метки элемента дерево в текущий элемент управления иерархического представления.  
  
```  
BOOL EndEditLabelNow(BOOL fCancelWithoutSave);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `fCancelWithoutSave`|`true`Чтобы отменить изменения элемента дерево до завершения операции изменения или `false` сохранить изменения в дереве элементов до завершения операции.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_ENDEDITLABELNOW](http://msdn.microsoft.com/library/windows/desktop/bb773564) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ensurevisible"></a>CTreeCtrl::EnsureVisible  
 Вызывайте эту функцию, чтобы убедиться, что элемент дерева является видимым.  
  
```  
BOOL EnsureVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева сделан видимым.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если система прокрутка элементов в элементе управления иерархического представления, чтобы убедиться, что указанный элемент является видимым. В противном случае — возвращает значение **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 При необходимости функция расширяется родительский элемент или прокрутка дерева, таким образом, чтобы элемент видим.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl №&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_6.cpp)]  
  
##  <a name="expand"></a>CTreeCtrl::Expand  
 Вызывайте эту функцию, чтобы развернуть или свернуть список дочерних элементов, если имеется, сопоставленный с элементом заданного родительского объекта.  
  
```  
BOOL Expand(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор разворачивания элемента дерева.  
  
 `nCode`  
 Флаг, указывающий тип действия. Этот флаг может иметь одно из следующих значений:  
  
- `TVE_COLLAPSE`Сворачивание списка.  
  
- `TVE_COLLAPSERESET`Сворачивание списка и удаление дочерних элементов. **TVIS_EXPANDEDONCE** Сбросить флаг состояния. Этот флаг должен использоваться с `TVE_COLLAPSE` флаг.  
  
- `TVE_EXPAND`При развертывании списка.  
  
- `TVE_TOGGLE`Сворачивание списка, если он развернут в настоящее время или развернуть его, если он свернут в настоящее время.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
##  <a name="getbkcolor"></a>CTreeCtrl::GetBkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773570), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее цвет фона текущего окна для элемента управления. Если это значение равно -1, элемент управления использует системный цвет окон. В этом случае можно использовать `::GetSysColor(COLOR_WINDOW)` для получения текущего цвета системы, используя элемент управления.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="getcheck"></a>CTreeCtrl::GetCheck  
 Вызовите эту функцию-член для получения состояния флажка элемента.  
  
```  
BOOL GetCheck(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 **HTREEITEM** о том, какие для получения сведений о состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления дерева проверяется; в противном случае — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getchilditem"></a>CTreeCtrl::GetChildItem  
 Просмотреть эту функцию, чтобы получить дерево элементов, вызывается дочернего элемента, заданного параметром `hItem`.  
  
```  
HTREEITEM GetChildItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор дочернего элемента, в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#7;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_7.cpp)]  
  
##  <a name="getcount"></a>CTreeCtrl::GetCount  
 Эта функция используется для получения количества элементов в элемент управления деревом.  
  
```  
UINT GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления иерархического представления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl №&8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_8.cpp)]  
  
##  <a name="getdrophilightitem"></a>CTreeCtrl::GetDropHilightItem  
 Эта функция вызывается для извлечения элемента, который является целевым объектом операции и перетащите.  
  
```  
HTREEITEM GetDropHilightItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента сбрасывается в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl №&9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="geteditcontrol"></a>CTreeCtrl::GetEditControl  
 Эта функция вызывается для получения дескриптора элемента управления поля ввода используются для редактирования текста элемента представления дерева.  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на поле редактирования, используемый для редактирования текста элемента, если выполнено успешно; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#10;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_10.cpp)]  
  
##  <a name="getextendedstyle"></a>CTreeCtrl::GetExtendedStyle  
 Извлекает расширенные стили, используя текущий элемент управления иерархического представления.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее побитовое сочетание (или) текущего элемента управления иерархического представления расширенных стилей. Дополнительные сведения см. в разделе [дерево управления расширенных стилей](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773580) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getfirstvisibleitem"></a>CTreeCtrl::GetFirstVisibleItem  
 Эта функция вызывается для получения первый видимый элемент управления иерархического представления.  
  
```  
HTREEITEM GetFirstVisibleItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор первой видимой позиции; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getimagelist"></a>CTreeCtrl::GetImageList  
 Эта функция вызывается для получения дескриптора нормали или список изображение состояния, связанный с элемента управления иерархического представления.  
  
```  
CImageList* GetImageList(UINT nImageList) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nImageList`  
 Тип списка изображений для извлечения. Список изображений может принимать одно из следующих значений:  
  
- `TVSIL_NORMAL`Извлекает список обычный образ, который содержит выбранные и невыбранные изображения для элемента представления дерева.  
  
- `TVSIL_STATE`Извлекает список изображения состояния, который содержит изображения для элементов представления дерева, которые находятся в состоянии, определяемые пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент управления списка изображений в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в дерево могут иметь пару точечных рисунков, связанных с ним. Одно изображение отображается в том случае, если элемент выбран, а другая отображается, если элемент не выбран. Например элемент может отображаться открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Дополнительные сведения о списках изображений см. в разделе [CImageList](../../mfc/reference/cimagelist-class.md) класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&11;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_11.cpp)]  
  
##  <a name="getindent"></a>CTreeCtrl::GetIndent  
 Эта функция вызывается для получения сумма, в пикселях, что дочерние элементы отображаются с отступом относительно родительские элементы.  
  
```  
UINT GetIndent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Величину отступа измеряется в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#12;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_12.cpp)]  
  
##  <a name="getinsertmarkcolor"></a>CTreeCtrl::GetInsertMarkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773590), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее текущий цвет метки вставки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#13;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_13.cpp)]  
  
##  <a name="getitem"></a>CTreeCtrl::GetItem  
 Эта функция вызывается для получения атрибутов элемент указанного дерева.  
  
```  
BOOL GetItem(TVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdata"></a>CTreeCtrl::GetItemData  
 Эта функция вызывается для получения 32-разрядное значение конкретного приложения, связанный с указанным элементом.  
  
```  
DWORD_PTR GetItemData(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, данные которой требуется извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение конкретного приложения, связанные с элемента, заданного параметром `hItem`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#14;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_14.cpp)]  
  
##  <a name="getitemexpandedimageindex"></a>CTreeCtrl::GetItemExpandedImageIndex  
 Возвращает индекс изображения, отображаемого в развернутом состоянии после указанного элемента текущего элемента управления иерархического представления.  
  
```  
int GetItemExpandedImageIndex(HTREEITEM hItem)const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения, отображаемого в развернутом состоянии после указанного элемента.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сообщение возвращает [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структура, описывающая элемент управления иерархического представления, а затем этот метод извлекает `iExpandedImage` элемент из этой структуры.  
  
##  <a name="getitemheight"></a>CTreeCtrl::GetItemHeight  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773599), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT GetItemHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента в пикселях.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#15;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_15.cpp)]  
  
##  <a name="getitemimage"></a>CTreeCtrl::GetItemImage  
 Каждый элемент в дерево могут иметь пару точечных рисунков, связанных с ним.  
  
```  
BOOL GetItemImage(
    HTREEITEM hItem,  
    int& nImage,  
    int& nSelectedImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, изображение которой требуется извлечь.  
  
 `nImage`  
 Целое число, Получает индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Целое число, Получает индекс изображения выбранного элемента в список изображений элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 То изображения появляются слева от метки элемента. Одно изображение отображается в том случае, если элемент выбран, а другая отображается, если элемент не выбран. Например элемент может отображаться открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Эта функция вызывается для извлечения индекса элемента и его выбранного изображения в списке изображений элемента управления иерархического представления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl №&16;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_16.cpp)]  
  
##  <a name="getitempartrect"></a>CTreeCtrl::GetItemPartRect  
 Возвращает прямоугольник, ограничивающий указанную часть указанного элемента в текущий элемент управления иерархического представления.  
  
```  
BOOL GetItemPartRect(
    HTREEITEM hItem,   
    int nPart,   
    LPRECT lpRect)const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления.|  
|[in] `nPart`|Идентификатор для компонента. Необходимо задать значение `TVGIPR_BUTTON`.|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. В случае успешной структуры получает координаты прямоугольника компонент, указываемый `hItem` и `nPart`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент управления дерева, ограничен прямоугольник графики. При каждом нажатии точки этого прямоугольника, элемент считается *попаданий*. Этот метод возвращает большой прямоугольник, что при выборе точки в прямоугольнике элемент, определенный с `hItem` попаданий параметра.  
  
 Этот метод отправляет `TVM_GETITEMPARTRECT` сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе [TreeView_GetItemPartRect](http://msdn.microsoft.com/library/windows/desktop/bb773847) макрос.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода используется идентификатор специальных возможностей и [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) метод для получения дескриптора для корневого элемента иерархического представления. Затем в примере используется дескриптор и [CTreeCtrl::GetItemPartRect](#getitempartrect) метод 3D прямоугольник вокруг элемента. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Мы использовали [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) метод, чтобы сопоставить корневой элемент дерева представления с идентификатором специальных возможностей.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="getitemrect"></a>CTreeCtrl::GetItemRect  
 Эта функция вызывается для получения прямоугольника, ограничивающего `hItem` и определить, является ли видимым или нет.  
  
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
 Если этот параметр имеет ненулевое значение, ограничивающий прямоугольник включает только текст элемента. В противном случае он включает в себя всю строку, занимает элемент в элементе управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент видим, с ограничивающим прямоугольником, содержащихся в `lpRect`. В противном случае — 0 с `lpRect` неинициализированным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&17;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_19.cpp)]  
  
##  <a name="getitemstate"></a>CTreeCtrl::GetItemState  
 Возвращает состояние элемента, заданного параметром `hItem`.  
  
```  
UINT GetItemState(
    HTREEITEM hItem,  
    UINT nStateMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, состояние которой требуется извлечь.  
  
 `nStateMask`  
 Маска, определяющая один или несколько состояний, которые требуется извлечь. Дополнительные сведения о возможных значениях `nStateMask`, см. обсуждение **состояние** и **stateMask** члены [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **UINT** , содержащий побитовую операцию или значения, указанные в nStateMask. Сведения о возможных значениях см. в разделе [CTreeCtrl::GetItem](#getitem). Чтобы найти значение для конкретного состояния, выполните побитовую операцию и значения состояния и возвращаемого значения, как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&18;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_20.cpp)]  
  
##  <a name="getitemstateex"></a>CTreeCtrl::GetItemStateEx  
 Извлекает расширенные состояние указанного элемента в элементе управления иерархического представления текущей.  
  
```  
UINT GetItemStateEx(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расширенные состояние элемента. Дополнительные сведения см. в разделе `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сообщение возвращает [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуру, которая описывает элемент управления иерархического представления и этот метод возвращает `uStateEx` элемент из этой структуры.  
  
##  <a name="getitemtext"></a>CTreeCtrl::GetItemText  
 Возвращает текст элемента, заданного параметром `hItem`.  
  
```  
CString GetItemText(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, текст которой требуется извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий текст элемента.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetNextItem](#getnextitem).  
  
##  <a name="getlastvisibleitem"></a>CTreeCtrl::GetLastVisibleItem  
 Возвращает последний элемент неразвернутыми узла в текущий элемент управления иерархического представления.  
  
```  
HTREEITEM GetLastVisibleItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор последнего элемента неразвернутыми узел, если метод выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETNEXTITEM](http://msdn.microsoft.com/library/windows/desktop/bb773622) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дополнительные сведения см. в разделе `TVGN_LASTVISIBLE` флаг в `flag` параметр этого сообщения.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. В следующем примере используются один или несколько из этих переменных.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода Получает дескриптор для последнего элемента узел неразвернутыми дерева, а затем выводит 3D прямоугольник вокруг элемента. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1 №&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_21.cpp)]  
  
##  <a name="getlinecolor"></a>CTreeCtrl::GetLineColor  
 Эта функция-член реализует поведение сообщения win32 [TVM_GETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773619), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetLineColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет линии.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&19;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_22.cpp)]  
  
##  <a name="getnextitem"></a>CTreeCtrl::GetNextItem  
 Вызов эту функцию, чтобы получить дерево просмотреть элемент, имеющий указанную связь, обозначенными `nCode` параметр в `hItem`.  
  
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
  
- `TVGN_DROPHILITE`Получает элемент, который является целевым объектом операции и перетаскивания.  
  
- `TVGN_FIRSTVISIBLE`Возвращает первый видимый элемент.  
  
- `TVGN_LASTVISIBLE`Извлекает расширенные последнего элемента в дереве. Это не получить последний элемент отображается в окне представления дерева.  
  
- `TVGN_NEXT`Получает следующий элемент того же уровня.  
  
- `TVGN_NEXTVISIBLE`Извлекает следующий видимый элемент, следующий за указанным элементом.  
  
- `TVGN_PARENT`Извлекает родительский указанного элемента.  
  
- `TVGN_PREVIOUS`Возвращает предыдущий элемент того же уровня.  
  
- `TVGN_PREVIOUSVISIBLE`Возвращает первый видимый элемент, который предшествует указанного элемента.  
  
- `TVGN_ROOT`Возвращает первый дочерний элемент корневого элемента, в состав которого входит указанный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор следующего элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает **NULL** Если извлекаемого элемента является корневым узлом дерева. Например, если вы используете это сообщение с `TVGN_PARENT` флаг первого уровня потомком корневой узел дерева, возвратит сообщение **NULL**.  
  
### <a name="example"></a>Пример  
 Пример использования `GetNextItem` в цикле, в разделе [CTreeCtrl::DeleteItem](#deleteitem).  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&20;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_23.cpp)]  
  
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
 [!code-cpp[NVC_MFC_CTreeCtrl&#21;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_24.cpp)]  
  
##  <a name="getnextvisibleitem"></a>CTreeCtrl::GetNextVisibleItem  
 Эта функция вызывается для извлечения следующего элемента видимой части `hItem`.  
  
```  
HTREEITEM GetNextVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор Далее видимого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="getparentitem"></a>CTreeCtrl::GetParentItem  
 Эта функция вызывается для получения родительский `hItem`.  
  
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
  В примере показано [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
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
 [!code-cpp[NVC_MFC_CTreeCtrl&#22;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_25.cpp)]  
  
##  <a name="getprevvisibleitem"></a>CTreeCtrl::GetPrevVisibleItem  
 Эта функция вызывается для получения предыдущих видимым элемент `hItem`.  
  
```  
HTREEITEM GetPrevVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор предыдущего видимого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#23;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_26.cpp)]  
  
##  <a name="getrootitem"></a>CTreeCtrl::GetRootItem  
 Эта функция вызывается для получения корневого элемента управления иерархического представления.  
  
```  
HTREEITEM GetRootItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор корневого элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::EditLabel](#editlabel).  
  
##  <a name="getscrolltime"></a>CTreeCtrl::GetScrollTime  
 Вызовите эту функцию-член для получения времени максимальное прокрутки для элемента управления иерархического представления.  
  
```  
UINT GetScrollTime() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прокрутите максимальное время в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения win32 [TVM_GETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773625), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getselectedcount"></a>CTreeCtrl::GetSelectedCount  
 Получает число выбранных элементов в элементе управления иерархического представления текущей.  
  
```  
UINT GetSelectedCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число выбранных элементов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_GETSELECTEDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb773629) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getselecteditem"></a>CTreeCtrl::GetSelectedItem  
 Эта функция вызывается для получения текущего выделенного элемента управления иерархического представления.  
  
```  
HTREEITEM GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор выбранного элемента; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#24;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_27.cpp)]  
  
##  <a name="gettextcolor"></a>CTreeCtrl::GetTextColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773633), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет текста. Если это значение равно -1, элемент управления использует системный цвет для цвета текста.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="gettooltips"></a>CTreeCtrl::GetToolTips  
 Эта функция-член реализует поведение сообщения Win32 [TVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773729), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объекта для использования по структуре дерева. Если [создать](#create) функция-член использует стиль **TVS_NOTOOLTIPS**, подсказки не используются, и **NULL** возвращается.  
  
### <a name="remarks"></a>Примечания  
 Реализация MFC `GetToolTips` возвращает `CToolTipCtrl` объект, который используется для управления дерева, а не дескриптор для элемента управления всплывающей подсказки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#25;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_28.cpp)]  
  
##  <a name="getvisiblecount"></a>CTreeCtrl::GetVisibleCount  
 Эта функция вызывается для получения количество видимых элементов в элементе управления древовидного представления.  
  
```  
UINT GetVisibleCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество видимых элементов в элементе управления иерархического представления; в противном случае — значение 1.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="hittest"></a>CTreeCtrl::HitTest  
 Эта функция вызывается для определения расположение указанной точки относительно клиентской области элемента управления иерархического представления.  
  
```  
HTREEITEM HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
  
HTREEITEM HitTest(TVHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Клиентских координат точки для тестирования.  
  
 `pFlags`  
 Указатель на целое число, который получает сведения о результатах проверки нажатия. Это может быть одно или несколько значений, перечисленных в разделе **флаги** элемента в разделе «Примечания».  
  
 `pHitTestInfo`  
 Адрес [TVHITTESTINFO будет СОДЕРЖАТЬ](http://msdn.microsoft.com/library/windows/desktop/bb773448) структуру, содержащую позиции нажму теста, которые получает сведения о результатах проверки нажатия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента представления дерева, занимающий заданную точку или **NULL** Если ни один элемент занимает точку.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функцией `pt` параметр задает координаты точки для тестирования. Функция возвращает дескриптор элемента в указанной точке или **NULL** Если ни один элемент занимает точку. Кроме того `pFlags` параметр содержит значение, указывающее расположение указанной точки. Доступны следующие значения:  
  
|||  
|-|-|  
|Значение|Значение|  
|TVHT_ABOVE|Выше клиентской области.|  
|TVHT_BELOW|Ниже области клиента.|  
|TVHT_NOWHERE|В клиентской области, но ниже последнего элемента.|  
|TVHT_ONITEM|Растровое изображение или метку, связанную с элементом.|  
|TVHT_ONITEMBUTTON|На кнопке, связанные с элементом.|  
|TVHT_ONITEMICON|В растровое изображение, связанное с элементом.|  
|TVHT_ONITEMINDENT|В отступы, связанные с элементом.|  
|TVHT_ONITEMLABEL|Метки (строка), связанные с элементом.|  
|TVHT_ONITEMRIGHT|В области справа от элемента.|  
|TVHT_ONITEMSTATEICON|Значок состояния древовидный элемент, который находится в состоянии, определяемые пользователем.|  
|TVHT_TOLEFT|Слева от клиентской области.|  
|TVHT_TORIGHT|В правой части клиентской области.|  
|||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
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
 Указатель на `TVINSERTSTRUCT` , определяющий атрибуты элемента представления дерева для вставки.  
  
 `nMask`  
 Целое число, задающее атрибуты для задания. В разделе `TVITEM` в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpszItem`  
 Адрес строка, содержащая текст элемента.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в списке изображений элемента управления иерархического представления.  
  
 `nState`  
 Задает значения для состояний элемента. Состояния элемента управления представления дерева см. в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список соответствующих состояний.  
  
 `nStateMask`  
 Указывает, какие состояния должны быть заданы. В разделе `TVITEM` в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lParam`  
 32-разрядное значение конкретного приложения, связанные с элементом.  
  
 `hParent`  
 Дескриптор родительского вставленного элемента.  
  
 *hInsertAfter*  
 Дескриптор элементом, после которого вставляется новый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор нового элемента в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Пример ситуации, в которых может потребоваться использовать каждой версии функции, при вставке элемента управления дерева.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#27;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_30.cpp)]  
  
##  <a name="itemhaschildren"></a>CTreeCtrl::ItemHasChildren  
 Эта функция позволяет определить, является ли заданный элемент дерева `hItem` имеет дочерние элементы.  
  
```  
BOOL ItemHasChildren(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если заданная элемент дерева `hItem` есть дочерние элементы; 0, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Если таким образом, можно воспользоваться [CTreeCtrl::GetChildItem](#getchilditem) для получения этих дочерних элементов.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetSelectedItem](#getselecteditem).  
  
##  <a name="mapaccidtoitem"></a>CTreeCtrl::MapAccIdToItem  
 Сопоставляет идентификатор указанного специальных возможностей дескриптор элемента дерево в текущий элемент управления иерархического представления.  
  
```  
HTREEITEM MapAccIdToItem(UINT uAccId) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `uAccId`|Специальные возможности идентификатор элемента в дереве элементов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента иерархического представления ( `HTREEITEM`), соответствующий `uAccId` параметр. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.  
  
### <a name="remarks"></a>Примечания  
 Специальные возможности — это приложения, помочь людям с ограниченными возможностями использования компьютеров. Использование идентификатора специальных возможностей `IAccessible` интерфейс, чтобы уникальным образом определять элемент в окне. Дополнительные сведения об идентификаторах специальных возможностей поиска в разделе «Об активных поддержка специальных возможностей» на [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_MAPACCIDTOHTREEITEM](http://msdn.microsoft.com/library/windows/desktop/bb773734) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода используется идентификатор специальных возможностей и [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) метод для получения дескриптора для корневого элемента иерархического представления. В примере используется дескриптор и [CTreeCtrl::GetItemPartRect](#getitempartrect) метод 3D прямоугольник вокруг элемента. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Мы использовали [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) метод, чтобы сопоставить корневой элемент дерева представления с идентификатором специальных возможностей.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="mapitemtoaccid"></a>CTreeCtrl::MapItemToAccID  
 Сопоставляет указанного дескриптора элемента представления дерева в элементе управления иерархического представления текущего идентификатора специальных возможностей.  
  
```  
UINT MapItemToAccID(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента в элементе управления иерархического представления. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Специальные возможности идентификатор, соответствующий `hItem` параметр.  
  
### <a name="remarks"></a>Примечания  
 Специальные возможности — это приложения, помочь людям с ограниченными возможностями использования компьютеров. Использование идентификатора специальных возможностей `IAccessible` интерфейс, чтобы уникальным образом определять элемент в окне. Дополнительные сведения об идентификаторах специальных возможностей поиска в разделе «Об активных поддержка специальных возможностей» на [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_MAPHTREEITEMTOACCID](http://msdn.microsoft.com/library/windows/desktop/bb773735) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода получает идентификационный номер для элемента управления иерархического представления. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Данный пример кода Получает уникальный идентификационный номер для страны или региона корневого узла.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctreectrl-class_31.cpp)]  
  
##  <a name="select"></a>CTreeCtrl::Select  
 Эта функция используется для выбора отображаемых элементов данного дерева, прокрутить элемент в представление или перерисовывает элемент в стиль, используемый для указания цели операции и перетащите.  
  
```  
BOOL Select(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
 `nCode`  
 Тип предпринимаемой операции. Этот параметр может принимать одно из следующих значений:  
  
- `TVGN_CARET`Устанавливает выделение для данного элемента.  
  
- `TVGN_DROPHILITE`Перерисовывает заданного элемента в стиль, используемый для указания цели операции и перетаскивания.  
  
- `TVGN_FIRSTVISIBLE`Таким образом, чтобы данный элемент первой видимой позиции по вертикали прокручивает представлении в виде дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `nCode` содержит значение `TVGN_CARET`, родительское окно получает **TVN_SELCHANGING** и **TVN_SELCHANGED** сообщений уведомления. Кроме того Если указанный элемент является потомком свернутого родительского элемента, родительского списка дочерних элементов расширяется для отображения указанного элемента. В этом случае родительское окно получает **TVN_ITEMEXPANDING** и **TVN_ITEMEXPANDED** сообщений уведомления.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::HitTest](#hittest).  
  
##  <a name="selectdroptarget"></a>CTreeCtrl::SelectDropTarget  
 Эта функция используется для повторной отрисовки элемента в стиль, используемый для указания цели операции и перетаскивания.  
  
```  
BOOL SelectDropTarget(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl №&9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
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
 Если `hItem` — **NULL**, то эта функция выбирает элемент отсутствует.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="selectsetfirstvisible"></a>CTreeCtrl::SelectSetFirstVisible  
 Эта функция вызывается для прокрутки по вертикали представлении в виде дерева, чтобы данный элемент является первой видимой позиции.  
  
```  
BOOL SelectSetFirstVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента дерева в качестве первой видимой позиции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция отправляет сообщение в окне с `TVM_SELECTITEM` и `TVGN_FIRSTVISIBLE` сообщений параметров.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#28;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_32.cpp)]  
  
##  <a name="setautoscrollinfo"></a>CTreeCtrl::SetAutoscrollInfo  
 Задает скорость autoscroll текущего элемента управления иерархического представления.  
  
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
 Параметры autoscroll используются для прокручивается в представлении элемент, который в настоящее время не является видимым. Элемент управления иерархического представления должен иметь `TVS_EX_AUTOHSCROLL` расширенный стиль, который описан в [расширенные стили элемента управления иерархического представления](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
 Этот метод отправляет [TVM_SETAUTOSCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb773738) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает поведение autoscroll текущего элемента управления иерархического представления. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Мы специально сделано управления иерархического представления узкий, чтобы автоматически нужно прокручивать экран для отображения элемента дерева, имеющий фокус. В примере кода задается дерево управления для автоматической прокрутки 30 пикселов в секунду каждые 5 секунд, пока не будет виден элемент дерева.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/ctreectrl-class_33.cpp)]  
  
##  <a name="setbkcolor"></a>CTreeCtrl::SetBkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773741), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** значение, содержащее новый цвет фона. Если это значение равно -1, элемент управления будет возвратиться к использованию системный цвет для цвета фона.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее текущий цвет текста. Если это значение равно -1, элемент управления использует системный цвет для цвета текста.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::SetTextColor](#settextcolor).  
  
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
 Указывает, является ли элемент управления дерева установлен или снят флажок. По умолчанию `SetCheck` задает элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если установлен элемент управления дерева ( `fCheck` значение **TRUE**), элемент отображается с рядом флажок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#29;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_34.cpp)]  
  
### <a name="example"></a>Пример  
 Чтобы использовать флажки, установите TVS_CHECKBOXES до заполнения дерева.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#30;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_35.cpp)]  
  
##  <a name="setextendedstyle"></a>CTreeCtrl::SetExtendedStyle  
 Задает расширенные стили текущего элемента управления иерархического представления.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,   
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwExMask`|Битовая маска, определяющая, какие стили в элементе управления иерархического представления текущей затрагиваются этим методом. Если этот параметр равен нулю, он игнорируется и значение `dwExStyles` параметру присваивается элементу управления иерархического представления.<br /><br /> Укажите ноль или побитовое сочетание (или) стилей, описанные в [дерево управления расширенных стилей](http://msdn.microsoft.com/library/windows/desktop/bb759981).|  
|[in] `dwExStyles`|Битовая маска, определяющая, какие стили в текущем представлении дерева управления установите или снимите флажок.<br /><br /> Чтобы задать сочетание стили, укажите побитовое сочетание (или) стилей, описанные в [дерево управления расширенных стилей](http://msdn.microsoft.com/library/windows/desktop/bb759981). Чтобы очистить набор стилей, укажите ноль.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее предыдущего расширенные стили элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает стили, заданные в `dwExMask` , затем задает стили, заданные в `dwExStyles` параметр. Расширенные стили, которые соответствуют битам в `dwExMask` изменения.  
  
 Этот метод отправляет [TVM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773744) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода добавляется `TVS_EX_AUTOHSCROLL` расширенный стиль для текущего элемента управления иерархического представления. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Мы специально сделано управления иерархического представления узкий, чтобы автоматически нужно прокручивать экран для отображения элемента дерева, имеющий фокус.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/ctreectrl-class_36.cpp)]  
  
##  <a name="setimagelist"></a>CTreeCtrl::SetImageList  
 Вызовите эту функцию для задания обычную или состояние списка изображений для дерева элемента управления и перерисовывает элемент управления с помощью новых образов.  
  
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
  
- `TVSIL_NORMAL`Задает список обычный образ, который содержит выбранные и невыбранные изображения для элемента представления дерева. Это состояние необходимо использовать для наложения изображений.  
  
- `TVSIL_STATE`Задает список изображений состояния, который содержит изображения для элементов представления дерева, которые находятся в состоянии, определяемые пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на предыдущем список изображений, при его наличии; в противном случае **NULL**.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetImageList](#getimagelist).  
  
##  <a name="setindent"></a>CTreeCtrl::SetIndent  
 Эта функция вызывается для задания ширины отступа для управления иерархического представления и перерисовывает элемент управления, чтобы отразить новую ширину.  
  
```  
void SetIndent(UINT nIndent);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndent`  
 Ширина в пикселях отступы. Если `nIndent` меньше, чем минимальная ширина определяемые системой, новая ширина присвоено минимальные системные.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetIndent](#getindent).  
  
##  <a name="setinsertmark"></a>CTreeCtrl::SetInsertMark  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb773753), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetInsertMark(
    HTREEITEM hItem,  
    BOOL fAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 **HTREEITEM** , указывающий, в какой элемент будет помещен знак вставки. Если этот аргумент равен **NULL**, метка вставки удаляется.  
  
 *fAfter*  
 **BOOL** значение, указывающее, если знак вставки помещается до или после указанного элемента. Если этот аргумент не равен нулю, метка вставки будет помещен после элемента. Если этот аргумент равен нулю, знак вставки помещается перед элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#31;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_37.cpp)]  
  
##  <a name="setinsertmarkcolor"></a>CTreeCtrl::SetInsertMarkColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773755), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `clrNew`  
 Объект **COLORREF** значение, содержащее новый цвет метки вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, содержащее на предыдущий цвет метки вставки.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor).  
  
##  <a name="setitem"></a>CTreeCtrl::SetItem  
 Эта функция используется, чтобы задать атрибуты элемента указанного дерева представления.  
  
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
 Указатель на [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуру, содержащую новый элемент атрибуты, как описано в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `hItem`  
 Дескриптор элемента, атрибуты которого должны быть заданы. В разделе **hItem** членом `TVITEM` в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nMask`  
 Целое число, задающее атрибуты для задания. В разделе **маска** членом `TVITEM` структуры.  
  
 `lpszItem`  
 Адрес строка, содержащая текст элемента.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления. В разделе `iImage` членом `TVITEM` структуры.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в списке изображений элемента управления иерархического представления. В разделе **iSelectedImage** членом `TVITEM` структуры.  
  
 `nState`  
 Задает значения для состояний элемента. В разделе **состояние** членом `TVITEM` структуры.  
  
 `nStateMask`  
 Указывает, какие состояния должны быть заданы. В разделе **stateMask** членом `TVITEM` структуры.  
  
 `lParam`  
 32-разрядное значение конкретного приложения, связанные с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 В `TVITEM` структуры, **hItem** член определяет элемент и **маска** член задает атрибуты для задания.  
  
 Если **маска** член или `nMask` параметр указывает `TVIF_TEXT` значение, **pszText** член или `lpszItem` является адрес строки с завершающим нулем и **cchTextMax** игнорируется. Если **маска** (или `nMask`) указывает `TVIF_STATE` значение, **stateMask** член или `nStateMask` параметр указывает, какой элемент имеет состояние для изменения и **состояние** член или `nState` параметр содержит значения для этих состояний.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#32;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_38.cpp)]  
  
##  <a name="setitemdata"></a>CTreeCtrl::SetItemData  
 Эта функция используется для установки 32-разрядное значение конкретного приложения, связанный с указанным элементом.  
  
```  
BOOL SetItemData(
    HTREEITEM hItem,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор элемента, данные которой требуется извлечь.  
  
 `dwData`  
 32-разрядное значение конкретного приложения, связанные с элемента, заданного параметром `hItem`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#33;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_39.cpp)]  
  
##  <a name="setitemexpandedimageindex"></a>CTreeCtrl::SetItemExpandedImageIndex  
 Задает индекс изображения, отображаемого в развернутом состоянии после указанного элемента текущего элемента управления иерархического представления.  
  
```  
BOOL SetItemExpandedImageIndex(
    HTREEITEM hItem,   
    int iExpandedImage);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления.|  
|[in] `iExpandedImage`|Индекс изображения, отображаемого в развернутом состоянии после указанного элемента.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот метод назначает `iExpandedImage` параметр `iExpandedImage` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуру и затем использует этот структуры в сообщении.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода является тривиальным тест для определения, является ли [CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex) метод возвращает значение, установленное [CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex) метод. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1 №&8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_40.cpp)]  
  
##  <a name="setitemheight"></a>CTreeCtrl::SetItemHeight  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773761), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT SetItemHeight(SHORT cyHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `cyHeight`  
 Задает новую высоту каждого элемента в представлении дерева в пикселях. Если этот аргумент меньше, чем высота изображений, то он будет происходить Высота изображения. Если этот аргумент не совпадает, то значение будет округлено до ближайшего значения, даже. Если этот аргумент равен -1, элемент управления будет возвратиться к использованию его высота элемента по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота предыдущих элементов, в пикселях.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetItemHeight](#getitemheight).  
  
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
 Дескриптор элемента, для которого изображение задается.  
  
 `nImage`  
 Индекс изображения элемента в список изображений элемента управления иерархического представления.  
  
 `nSelectedImage`  
 Индекс изображения выбранного элемента в списке изображений элемента управления иерархического представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Каждый элемент в дерево могут иметь пару точечных рисунков, связанных с ним. То изображения появляются слева от метки элемента. Одно изображение отображается в том случае, если элемент выбран, а другая отображается, если элемент не выбран. Например элемент может отображаться открыть папку, при этом и закрытую папку, если она еще не выбрана.  
  
 Эта функция вызывается для настройки индекса изображения элемента и его выбранное изображение в список изображений элемента управления иерархического представления.  
  
 Дополнительные сведения о образах см. [CImageList](../../mfc/reference/cimagelist-class.md).  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetItemImage](#getitemimage).  
  
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
 Дескриптор элемента, состояние которого требуется задать.  
  
 `nState`  
 Указывает новые состояния для элемента.  
  
 `nStateMask`  
 Указывает, какие состояния будут изменены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сведения о состояниях см. в разделе [CTreeCtrl::GetItem](#getitem).  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetItemState](#getitemstate).  
  
##  <a name="setitemstateex"></a>CTreeCtrl::SetItemStateEx  
 Задает расширенные состояние указанного элемента в текущий элемент управления иерархического представления.  
  
```  
BOOL SetItemStateEx(
    HTREEITEM hItem,   
    UINT uStateEx);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления.|  
|[in] `uStateEx`|Расширенные состояние элемента. Дополнительные сведения см. в разделе `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Этот метод назначает `uStateEx` параметр `uStateEx` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуру и затем использует этот структуры в сообщении.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_treeCtrl`, который используется для доступа к текущего элемента управления иерархического представления. В примере также определяется целое число без знака и нескольких переменных HTREEITEM. Эти переменные используются в следующем примере.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает дерево элемента в отключенном состоянии. В предыдущем разделе примера кода, который не показан, мы создали дерево, состоящий из корневого узла страны или региона для США, подузлы состояний Пенсильвании и Вашингтон и дерево элементов для тех городов, в этих состояний. Данный пример кода задает узел Пенсильвания в отключенном состоянии.  
  
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
 Дескриптор элемента, для которых задается.  
  
 `lpszItem`  
 Строка, содержащая новый текст для элемента адрес  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#34;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_42.cpp)]  
  
##  <a name="setlinecolor"></a>CTreeCtrl::SetLineColor  
 Вызовите эту функцию-член задать текущий цвет линии для управления иерархического представления.  
  
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
 [!code-cpp[NVC_MFC_CTreeCtrl&#35;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_43.cpp)]  
  
##  <a name="setscrolltime"></a>CTreeCtrl::SetScrollTime  
 Вызовите эту функцию-член для установки времени максимальное прокрутки для элемента управления иерархического представления.  
  
```  
UINT SetScrollTime(UINT uScrollTime);
```  
  
### <a name="parameters"></a>Параметры  
 *uScrollTime*  
 Новое время максимальной прокрутки в миллисекундах. Если это значение меньше 100, оно округляется до 100.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие время максимальной прокрутки в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения win32 [TVM_SETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773767), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="settextcolor"></a>CTreeCtrl::SetTextColor  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773769), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Объект **COLORREF** значение, содержащее новый цвет текста. Если этот аргумент равен -1, элемент управления будет возвратиться к использованию системный цвет для цвета текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее на предыдущий цвет текста. Если это значение равно -1, элемент управления использовал системный цвет для цвета текста.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#36;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_44.cpp)]  
  
##  <a name="settooltips"></a>CTreeCtrl::SetToolTips  
 Эта функция-член реализует поведение сообщения Win32 [TVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773772), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, который будет использоваться в структуре дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) объект, содержащий ранее используемые с помощью элемента управления всплывающей подсказки или **NULL** Если ранее использовались не подсказки.  
  
### <a name="remarks"></a>Примечания  
 Для того чтобы использовать подсказки, указать **TVS_NOTOOLTIPS** стиля при создании `CTreeCtrl` объекта.  
  
### <a name="example"></a>Пример  
  В примере показано [CTreeCtrl::GetToolTips](#gettooltips).  
  
##  <a name="showinfotip"></a>CTreeCtrl::ShowInfoTip  
 Отображает всплывающую подсказку для указанного элемента в текущий элемент управления иерархического представления.  
  
```  
void ShowInfoTip(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `hItem`|Дескриптор элемента управления иерархического представления. Дополнительные сведения см. в разделе `hItem` членом [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) структуры.|  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о различиях между всплывающих подсказках и всплывающих подсказках, найдите раздел «Всплывающих подсказках и всплывающих подсказках» на [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Этот метод отправляет [TVM_SHOWINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb773779) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sortchildren"></a>CTreeCtrl::SortChildren  
 Эта функция вызывается для дочерних элементов заданного родительского элемента в элементе управления древовидного представления отсортировать в алфавитном порядке.  
  
```  
BOOL SortChildren(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Параметры  
 `hItem`  
 Дескриптор родительского элемента, чьи дочерние элементы должны быть отсортированы. Если `hItem` — **NULL**, сортировка будет выполняться из корневого элемента дерева.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `SortChildren`не обращаться дерева; только дочерние элементы `hItem` будут отсортированы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#37;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_45.cpp)]  
  
##  <a name="sortchildrencb"></a>CTreeCtrl::SortChildrenCB  
 Эта функция вызывается для сортировки элементов представления дерева с помощью функции обратного вызова, определяемые приложением, сравнивает элементы.  
  
```  
BOOL SortChildrenCB(LPTVSORTCB pSort);
```  
  
### <a name="parameters"></a>Параметры  
 *pSort*  
 Указатель на [TVSORTCB](http://msdn.microsoft.com/library/windows/desktop/bb773462) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция сравнения структуры, **lpfnCompare**, должен возвращать отрицательное значение, если первый элемент должен предшествовать второй, положительное значение, если первый элемент должен следовать второй, или нуль, если два элемента эквивалентны.  
  
 `lParam1` И `lParam2` параметры соответствуют **lParam** членом [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структуры двух элементов с которым производится сравнение. `lParamSort` Параметр соответствует **lParam** членом `TV_SORTCB` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTreeCtrl&#38;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_46.cpp)]  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#39;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_47.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CImageList-класс](../../mfc/reference/cimagelist-class.md)

