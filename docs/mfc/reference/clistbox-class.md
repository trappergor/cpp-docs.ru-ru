---
title: "CListBox-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
dev_langs: C++
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ecf574deed95fca6a96e8e5a5c1d1e0bebed1854
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clistbox-class"></a>CListBox-класс
Предоставляет функции списка Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CListBox : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CListBox::CListBox](#clistbox)|Создает объект `CListBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|Добавляет строку в поле со списком.|  
|[CListBox::CharToItem](#chartoitem)|Переопределение, чтобы указать пользовательский `WM_CHAR` обработки для списков рисуемый владельцем, которых нет строки.|  
|[CListBox::CompareItem](#compareitem)|Вызывается платформой для определения положения элемента в поле со списком отсортированный рисования владельцем.|  
|[CListBox::Create](#create)|Создание списка Windows и прикрепляет его к `CListBox` объекта.|  
|[CListBox::DeleteItem](#deleteitem)|Вызывается платформой, когда пользователь удаляет элемент из списка рисуемый владельцем.|  
|[CListBox::DeleteString](#deletestring)|Удаляет строку из списка.|  
|[CListBox::Dir](#dir)|Добавляет имена файлов, дисков или оба из текущего каталога в поле со списком.|  
|[CListBox::DrawItem](#drawitem)|Вызывается платформой при изменении вида изменяется рисуемый владельцем списка.|  
|[См](#findstring)|Поиск строки в поле со списком.|  
|[CListBox::FindStringExact](#findstringexact)|Находит строки первого списков, которая совпадает с указанной строкой.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Определяет индекс элемента, который содержит прямоугольник фокуса в поле со списком с множественным выбором.|  
|[CListBox::GetCount](#getcount)|Возвращает число строк в поле со списком.|  
|[CListBox::GetCurSel](#getcursel)|Возвращает отсчитываемый от нуля индекс строки, выбранного в поле со списком.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях горизонтальной прокруткой поле со списком.|  
|[CListBox::GetItemData](#getitemdata)|Возвращает 32-разрядное значение, связанное с элементом списка.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Возвращает указатель на элемент в списке.|  
|[CListBox::GetItemHeight](#getitemheight)|Определяет высоту элементов в поле со списком.|  
|[CListBox::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник элемента списка, как оно отображается в данный момент.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Возвращает количество элементов каждого столбца.|  
|[CListBox::GetLocale](#getlocale)|Возвращает идентификатор языкового стандарта для списка.|  
|[CListBox::GetSel](#getsel)|Возвращает состояние элемента в списке выбора.|  
|[CListBox::GetSelCount](#getselcount)|Возвращает число строк, выбранного в поле со списком с множественным выбором.|  
|[CListBox::GetSelItems](#getselitems)|Возвращает индексы строки, выбранной в поле со списком.|  
|[CListBox::GetText](#gettext)|Копирует элемент списков в буфер.|  
|[CListBox::GetTextLen](#gettextlen)|Возвращает длину в байтах элемента в списке.|  
|[CListBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой строки в поле со списком.|  
|[CListBox::InitStorage](#initstorage)|Предварительно размещает блоки памяти для элементов списка и строк.|  
|[CListBox::InsertString](#insertstring)|Вставляет строку в определенном месте в поле со списком.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Возвращает индекс элемента списков ближайшую точку.|  
|[CListBox::MeasureItem](#measureitem)|Вызывается платформой при создании списка рисуемый владельцем для определения измерений в списке.|  
|[CListBox::ResetContent](#resetcontent)|Удаляет все записи из списка.|  
|[CListBox::SelectString](#selectstring)|Выполняет поиск и выбирает строку в поле со списком с единственным выбором.|  
|[CListBox::SelItemRange](#selitemrange)|Выбирает или отменяет выделение диапазона строк в поле со списком с множественным выбором.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Задает привязку в поле со списком множественным выбором, чтобы начать расширенного выделения.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Задает прямоугольник фокуса к элементу по указанному индексу в поле со списком с множественным выбором.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Задает ширину столбца список из нескольких столбцов.|  
|[CListBox::SetCurSel](#setcursel)|Выбирает строку списков.|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях горизонтальной прокруткой поле со списком.|  
|[CListBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с элементом списка.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Задает указатель к элементу в списке.|  
|[CListBox::SetItemHeight](#setitemheight)|Задает высоту элементов в поле со списком.|  
|[CListBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для списка.|  
|[CListBox::SetSel](#setsel)|Выбирает или отменяет выделение элемента списка в поле со списком с множественным выбором.|  
|[CListBox::SetTabStops](#settabstops)|Задает позиции табуляции в поле со списком.|  
|[CListBox::SetTopIndex](#settopindex)|Задает отсчитываемый от нуля индекс первой видимой строки в поле со списком.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Переопределение, чтобы указать пользовательский `WM_KEYDOWN` обработки для списков с **LBS_WANTKEYBOARDINPUT** стиля набора.|  
  
## <a name="remarks"></a>Примечания  
 Поле со списком отображает список элементов, таких как имена файлов, который пользователь может просмотреть и выбрать.  
  
 В поле со списком с единственным выбором пользователь может выбрать только один элемент. В поле со списком с множественным выбором можно выбрать диапазон элементов. Когда пользователь выбирает элемент, он выделяется и списке отправляет сообщение уведомления в родительское окно.  
  
 Можно создать поле со списком из шаблона диалогового окна или непосредственно в коде. Чтобы создать напрямую, создания `CListBox` объекта, а затем вызвать [создать](#create) функции-члена для создания списков управления Windows и присоединить его к `CListBox` объекта. Чтобы использовать поле со списком в шаблон диалогового окна, объявите переменную списков в классе диалогового окна, а затем `DDX_Control` в поле класса своего диалогового окна `DoDataExchange` функции для подключения переменной-члена для элемента управления. (это выполняется автоматически автоматически при добавлении переменной элемента управления в классе диалогового окна.)  
  
 Построение может быть задачей в классе, производном от `CListBox`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 Если вы хотите обработки сообщений Windows уведомления, отправленные в поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавить схему сообщений входа и обработчик сообщений функции-члена родительского класса для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 `ON_Notification( id, memberFxn )`  
  
 где `id` указывает идентификатор дочернего окна списков управления, отправляющего уведомление и `memberFxn` имя функции-члена родительского вы написали для обработки уведомления.  
  
 Прототип функции родительского элемента выглядит следующим образом:  
  
 `afx_msg void memberFxn( );`  
  
 Ниже приведен список возможных операций схемы сообщений и описание вариантов, в которых они были бы отправлены на родительский:  
  
- **ON_LBN_DBLCLK** пользователь дважды щелкает строку в поле со списком. Только поле со списком, который имеет [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль будет отправлять это сообщение уведомления.  
  
- **ON_LBN_ERRSPACE** списка не удается выделить достаточно памяти для выполнения запроса.  
  
- **ON_LBN_KILLFOCUS** списке теряет фокус ввода.  
  
- **ON_LBN_SELCANCEL** отменить текущее выделение списков. Это сообщение отправляется только в том случае, если поле со списком имеет **LBS_NOTIFY** стиля.  
  
- **ON_LBN_SELCHANGE** был изменен выбор в поле со списком. Это уведомление отправляется не в том случае, если параметр изменяется при [CListBox::SetCurSel](#setcursel) функции-члена. Данное уведомление относится только к поле со списком, который имеет **LBS_NOTIFY** стиля. **LBN_SELCHANGE** отправляется уведомление для списка множественным выбором всякий раз, когда пользователь нажимает клавишу со стрелкой, даже если не изменяется.  
  
- **ON_LBN_SETFOCUS** списка получает фокус ввода.  
  
- **ON_WM_CHARTOITEM** Получает список рисуемый владельцем, никакие строки не имеет `WM_CHAR` сообщения.  
  
- **ON_WM_VKEYTOITEM** списка **LBS_WANTKEYBOARDINPUT** получает стиль `WM_KEYDOWN` сообщения.  
  
 Если вы создаете `CListBox` объектов в диалоговом окне (с помощью ресурса диалогового окна) `CListBox` объект автоматически освобождается, когда пользователь закрывает диалоговое окно.  
  
 Если вы создаете `CListBox` объект внутри другого окна, может потребоваться уничтожить `CListBox` объекта. Если вы создаете `CListBox` объекта в стеке, удаляется автоматически. При создании `CListBox` объекта в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закрывает родительского окна.  
  
 Если выделять память в `CListBox` объекта, переопределите `CListBox` деструктор для удаления выделения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="addstring"></a>CListBox::AddString  
 Добавляет строку в поле со списком.  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItem`  
 Указывает на строку с завершающим нулем, должен быть добавлен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс строки в окне списка. Возвращает значение **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для хранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 Если в списке не был создан с [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, строка добавляется в конец списка. В противном случае строка вставляется в списке, и список сортируется. Если поле списка был создан с **LBS_SORT** стиля, но не [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, платформа сортировку списка, один или несколько вызовов `CompareItem` функции-члена.  
  
 Используйте [InsertString](#insertstring) для вставки строки в определенное место в окне списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>CListBox::CharToItem  
 Вызывается платформой при получении списка родительскому окну `WM_CHARTOITEM` сообщения из списка.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nKey`  
 Код ANSI знак, введенный пользователем.  
  
 `nIndex`  
 Текущая позиция курсора списков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает - 1 или - 2 для дальнейших действий или неотрицательное число, указывающее индекс элемента списков для выполнения действия по умолчанию для нажатия клавиши. Реализация по умолчанию возвращается значение-1.  
  
### <a name="remarks"></a>Примечания  
 `WM_CHARTOITEM` Сообщение отправляется в списке при получении `WM_CHAR` сообщения, но только если списке соответствует всем этим критериям:  
  
-   Представляет список рисуемого владельцем.  
  
-   Не поддерживает [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля набора.  
  
-   Содержит по крайней мере одного элемента.  
  
 Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию для предоставления собственных обычной обработки сообщений клавиатуры.  
  
 Во время переопределения должен возвращать значение, чтобы сообщить платформе, какое действие вы выполняли. Возвращаемое значение - 1 или - 2 указывает обрабатывать все аспекты выберите нужный элемент и не требует дальнейших действий в списке. Перед возвратом - 1 или - 2, можно выбрать в списке или переместите курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Чтобы переместить курсор, используйте [SetCaretIndex](#setcaretindex).  
  
 Возвращаемое значение 0 или больше указывает индекс элемента в поле со списком и указывает, что поле списка следует выполнить действия по умолчанию нажатие клавиши на данный элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>CListBox::CListBox  
 Создает объект `CListBox`.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Примечания  
 Создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор **ClistBox** и затем вызвать **создать**, который инициализирует списка Windows и прикрепляет его к `CListBox`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CListBox::CompareItem  
 Вызывается платформой для определения относительной позиции нового элемента в поле со списком отсортированный рисования владельцем.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpCompareItemStruct`  
 Длинный указатель `COMPAREITEMSTRUCT` структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает относительную позицию двух элементов, описанных в [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) структуры. Он может быть любым из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|-1|Элемент 1 предшествует элемент 2.|  
|0|1 и 2 элемент сортировки одинаковыми.|  
|1|Элемент 1 сортирует после элемента 2.|  
  
 В разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT` структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. При создании списка рисуемый владельцем **LBS_SORT** стилей, необходимо переопределить эту функцию-член для помощи в новые элементы, добавленные в список сортировки платформу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>CListBox::Create  
 Создание списка Windows и прикрепляет его к `CListBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль списка. Примените любое сочетание [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) в поле.  
  
 `rect`  
 Указывает списков размер и положение. Может быть как `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает поле списка родительскому окну (обычно `CDialog` объекта). Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор поле списка элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который инициализирует списка Windows и прикрепляет его к `CListBox` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений в элемент управления «список».  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CListBox`, добавить схему сообщений к новому классу и переопределить предыдущей функции-члены обработчика сообщений. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Применить следующие [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) к элементу управления в списке.  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** для добавления вертикальной полосы прокрутки  
  
- **WS_HSCROLL** для добавления горизонтальной полосы прокрутки  
  
- **WS_GROUP** для группировки элементов управления  
  
- **WS_TABSTOP** чтобы разрешить переход на данный элемент управления  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>CListBox::DeleteItem  
 Вызывается платформой, когда пользователь удаляет элемент из рисуемый владельцем `CListBox` объекта или уничтожает поле списка.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDeleteItemStruct`  
 Длинный указатель на Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для перерисовки списка рисуемый владельцем, при необходимости.  
  
 В разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание `DELETEITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>CListBox::DeleteString  
 Удаляет элемент в позиции `nIndex` поле со списком.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс строки для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк, оставшихся в списке. Возвращает значение **LB_ERR** Если `nIndex` указывает индекс больше числа элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Все элементы, следующие `nIndex` теперь перемещаются на одну позицию вниз. Например если поле со списком содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первую позицию. `nIndex`= 0 в первую позицию элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>CListBox::Dir  
 Добавляет список имен файлов, дисков или оба значения в поле со списком.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Параметры  
 `attr`  
 Может быть любым сочетанием `enum` значений описано в **CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus), или любое сочетание следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|0x0000|Файл для чтения и записи.|  
|0x0001|Файл может быть считывается, но не записываются.|  
|0x0002|Файл является скрытым и не отображается в списках каталогов.|  
|0x0004|Файл является системным файлом.|  
|0x0010|Имя, заданное `lpszWildCard` указывает каталог.|  
|0x0020|Файл сохранен в архиве.|  
|0x4000|Включить все диски, которые соответствуют имени, указанного параметром `lpszWildCard`.|  
|0x8000|Флаг exclusive. Если установить флаг exclusive, включаются только файлы указанного типа. В противном случае файлы указанного типа, перечислены помимо файлов «normal».|  
  
 `lpszWildCard`  
 Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс последнего имени файла добавляется в список. Возвращает значение **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для хранения новых строк.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>CListBox::DrawItem  
 Вызывается платформой при изменении вида изменяется рисуемый владельцем списка.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** и **itemState** члены `DRAWITEMSTRUCT` структура определять рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CListBox` объекта. Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` до этого элемента, функция завершается.  
  
 В разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание `DRAWITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>См  
 Выполняет поиск первой строки в поле со списком, который содержит указанный префикс без изменения списков выбора.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nStartAfter`. Если `nStartAfter` равно -1, весь список просматривается с самого начала.  
  
 `lpszItem`  
 Указывает на строку, завершающуюся значением null, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента сопоставления или **LB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Используйте [SelectString](#selectstring) функции-члена для поиска и выберите строку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>CListBox::FindStringExact  
 Находит первый списков строки, соответствующая строка, указанная в `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndexStart`  
 Задает отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nIndexStart`. Если `nIndexStart` равно -1, весь список просматривается с самого начала.  
  
 `lpszFind`  
 Указывает на строку, завершающуюся значением null, для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не учитывается регистр, поэтому строка может содержать любое сочетание букв верхнего и нижнего регистра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента сопоставления или **LB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Если поле списка создавался стиль рисования владельцем, но без [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, `FindStringExact` функция-член пытается найти соответствие двойное значение для значения `lpszFind`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>CListBox::GetAnchorIndex  
 Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс текущего элемента привязки в случае успешного выполнения; в противном случае **LB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 В поле со списком с множественным выбором элементом привязки является первому или последнему элементу в блоке смежных выбранных элементов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="getcaretindex"></a>CListBox::GetCaretIndex  
 Определяет индекс элемента, который содержит прямоугольник фокуса в поле со списком с множественным выбором.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента, имеющего прямоугольник фокуса в поле со списком. Если список имеет поле со списком с единственным выбором, возвращается индекс элемента, который выбран, если таковые имеются.  
  
### <a name="remarks"></a>Примечания  
 Элемент может или не может быть выбран.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="getcount"></a>CListBox::GetCount  
 Возвращает число элементов в поле со списком.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в поле со списком или **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Количество возвращаемых результатов — единицу больше, чем значение индекса последнего элемента (индекс начинается с нуля).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>CListBox::GetCurSel  
 Возвращает отсчитываемый от нуля индекс текущего выделенного элемента при наличии таковой, в поле со списком с единственным выбором.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента, если это поле со списком с единственным выбором. Это `LB_ERR` , если элемент не выбран в данный момент.  
  
 В поле списка с множественным выбором индекс элемента, который находится в фокусе.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать `GetCurSel` для списка множественного выбора. Используйте [CListBox::GetSelItems](#getselitems) вместо него.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent  
 Получает ширину в пикселях, на которое он может прокручиваться по горизонтали в поле со списком.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина прокрутки списка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Это применимо только в том случае, если список содержит горизонтальную полосу прокрутки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>CListBox::GetItemData  
 Извлекает значение двойное слово соответственно, предоставляемую приложением, связанный с элементом указанного списка.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-разрядное значение, связанное с элементом, или **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Двойное значение было `dwItemData` параметр [SetItemData](#setitemdata) вызова.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>CListBox::GetItemDataPtr  
 Возвращает значение предоставленного приложением 32-разрядной, связанное с элементом указанного списка как указатель ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель или значение -1, если произошла ошибка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>CListBox::GetItemHeight  
 Определяет высоту элементов в поле со списком.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список содержит **LBS_OWNERDRAWVARIABLE** стиля; в противном случае оно должно иметь значение 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях элементов в поле со списком. Если список содержит [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, возвращаемым значением является высота элемента, заданного параметром `nIndex`. При возникновении ошибки возвращается **LB_ERR**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>CListBox::GetItemRect  
 Возвращает размеры прямоугольника элемента границы поле со списком как в настоящее время оно отображается в окне списка.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
 `lpRect`  
 Указывает длинный указатель [структура RECT](../../mfc/reference/rect-structure1.md) , получающий списков клиентские координаты элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>CListBox::GetListBoxInfo  
 Возвращает количество элементов каждого столбца.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов каждого столбца из `CListBox` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) сообщения, как описано в Windows SDK.  
  
##  <a name="getlocale"></a>CListBox::GetLocale  
 Возвращает языковой стандарт, используемый в списке.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение код (LCID) языка для строк в поле со списком.  
  
### <a name="remarks"></a>Примечания  
 Локаль используется, например, для определения порядка сортировки строк в отсортированном списке.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::SetLocale](#setlocale).  
  
##  <a name="getsel"></a>CListBox::GetSel  
 Извлекает состояние выбора элемента.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное число, если указанный элемент выбран; в противном случае — 0. Возвращает значение `LB_ERR` при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает с обоих выбора одной и нескольких списков.  
  
 Получить индекс элемента списка, выбранной с помощью [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>CListBox::GetSelCount  
 Получает общее количество выбранных элементов в поле со списком с множественным выбором.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число выбранных элементов в поле со списком. Если список имеет поле со списком с единственным выбором, возвращаемое значение равно **LB_ERR**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::GetSelItems](#getselitems).  
  
##  <a name="getselitems"></a>CListBox::GetSelItems  
 Заполняет массив целых чисел, который определяет элемент числа выбранных элементов в поле со списком с множественным выбором буфера.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxItems`  
 Указывает максимальное количество выбранных элементов, чьи номера элемента, должно быть помещено в буфер.  
  
 `rgIndex`  
 Устанавливает указатель на буфер, достаточный для числа целые числа, заданные `nMaxItems`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактическое число элементов, помещаются в буфер. Если список имеет поле со списком с единственным выбором, возвращаемое значение равно `LB_ERR`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="gettext"></a>CListBox::GetText  
 Получает строку из списка.  
  
```  
int GetText(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
void GetText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс строки, которые требуется получить.  
  
 `lpszBuffer`  
 Указывает для буфера, принимающего строку. Буфер должен иметь достаточно места для строки и знак завершения null. Размер строки можно определить заранее, вызвав `GetTextLen` функции-члена.  
  
 `rString`  
 Ссылка на объект `CString`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, за исключением завершающий символ null (в байтах). Если `nIndex` не указывает допустимый индекс, возвращаемым значением является **LB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма этого элемента функция заливки `CString` вместе с текстом строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>CListBox::GetTextLen  
 Возвращает длину строки в элементе списка.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в символов, включая завершающий символ null. Если `nIndex` не указывает допустимый индекс, возвращаемым значением является **LB_ERR**.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::GetText](#gettext).  
  
##  <a name="gettopindex"></a>CListBox::GetTopIndex  
 Возвращает отсчитываемый от нуля индекс первой видимой позиции в списке.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первой видимой позиции в поле со списком, в случае успешного выполнения **LB_ERR** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Изначально элемент 0 находится в верхней части списка, но если прокрутить список, сверху может оказаться другой элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="initstorage"></a>CListBox::InitStorage  
 Выделяет память для хранения элементов списков.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nItems`  
 Указывает количество элементов для добавления.  
  
 `nBytes`  
 Указывает объем памяти в байтах для выделения для элемента строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении максимальное количество элементов, можно хранить в списке перед перераспределение памяти требуется **LB_ERRSPACE**, доступен, то есть не хватает памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию перед добавлением большое количество элементов для `CListBox`.  
  
 Эта функция помогает ускорить инициализации списка полей, имеющих большое количество элементов (более 100). Он предварительно размещает указанный объем памяти, поэтому последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайшие сроки. Оценки можно использовать для параметров. Если вы пересмотреть, некоторые дополнительная память выделяется; Если стоит недооценивать, обычный распределение используется для элементов, которые превышают предварительно выделенной сумму.  
  
 Windows 95/98 только: `nItems` ограничен 16-разрядных значений. Это означает, что списки не может содержать более 32 767 элементов. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничен только объемом доступной памяти.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>CListBox::InsertString  
 Вставляет строку в поле со списком.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс позиции для вставки строки. Если этот параметр имеет значение -1, строка добавляется в конец списка.  
  
 `lpszItem`  
 Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Возвращает значение **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для хранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 В отличие от [AddString](#addstring) функции-члена `InsertString` не ведет список с [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль сортировки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>CListBox::ItemFromPoint  
 Определяет элемент ближайшую точку, указанную в списке `pt`.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Точка, для которого нужно искать ближайший элемент по указанному относительно левого верхнего угла клиентской области окна списка.  
  
 `bOutside`  
 Ссылка на `BOOL` переменную, которая будет присвоено `TRUE` Если `pt` выходит за пределы клиентской области ближайшего элемента списка, `FALSE` Если `pt` находится внутри клиентской области ближайшего элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, ближайшего к точке, указанной в `pt`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить, какой элемент списков наводится указатель мыши, можно использовать эту функцию.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="measureitem"></a>CListBox::MeasureItem  
 Вызывается платформой при создании списка стиль рисования владельцем.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows размеры списков. Если при создании списка [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, платформа вызывает эту функцию-член для каждого элемента в поле со списком. В противном случае этот член вызывается только один раз.  
  
 Дополнительные сведения об использовании [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля в списке рисуемый владельцем, созданных с помощью `SubclassDlgItem` функцию-член `CWnd`, см. обсуждение в [Технические заметки 14](../../mfc/tn014-custom-controls.md).  
  
 В разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры **.**  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>CListBox::ResetContent  
 Удаляет все элементы из списка.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>CListBox::SelectString  
 Поиск для элементов списков, совпадающий с указанной строкой, а если соответствующий элемент найден, он выбирает элемент.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает нижней части списка, он по-прежнему в верхней части списка обратно элемент с указанным `nStartAfter`. Если `nStartAfter` равно -1, весь список просматривается с самого начала.  
  
 `lpszItem`  
 Указывает на строку, завершающуюся значением null, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выбранного элемента, если был выполнен поиск. Если поиск завершилась неудачно, возвращается **LB_ERR** и текущего выделения не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Прокручивает списка, при необходимости, чтобы сделать выбранный элемент видимым.  
  
 Эта функция-член не может использоваться со списком, который имеет [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля.  
  
 Элемент выбирается только в том случае, если его начальные символы (от начальной) соответствует знаков в строки, заданной параметром `lpszItem`.  
  
 Используйте `FindString` функции-члена для поиска строки без выбора элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>CListBox::SelItemRange  
 В поле со списком с множественным выбором, выбирает несколько последовательных элементов.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Параметры  
 `bSelect`  
 Указывает, как выбрать в списке. Если `bSelect` — **TRUE**, строка выбран и выделяются; Если **FALSE**, выделение удаляется, и строка теряет фокус.  
  
 `nFirstItem`  
 Задает отсчитываемый от нуля индекс первого элемента для задания.  
  
 `nLastItem`  
 Задает отсчитываемый от нуля индекс последнего элемента для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только с множественным выбором списки. Если вам нужно выбрать только один элемент в поле со списком с множественным выбором — то есть если `nFirstItem` равен `nLastItem` — вызвать [SetSel](#setsel) функцию-член, вместо этого.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>CListBox::SetAnchorIndex  
 Задает привязку в поле со списком множественным выбором, чтобы начать расширенного выделения.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента списков, который будет служить в качестве привязки.  
  
### <a name="remarks"></a>Примечания  
 В поле со списком с множественным выбором элементом привязки является первому или последнему элементу в блоке смежных выбранных элементов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>CListBox::SetCaretIndex  
 Задает прямоугольник фокуса к элементу по указанному индексу в поле со списком с множественным выбором.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента для получения прямоугольника фокуса в поле со списком.  
  
 *bScroll*  
 Если это значение равно 0, элемент при прокрутке, пока он не будет полностью видимыми. Если это значение не равно 0, элемент при прокрутке пока хотя бы частично видимой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Если элемент не отображается, его в области просмотра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>CListBox::SetColumnWidth  
 Задает ширину в пикселях всех столбцов в список с несколькими столбцами (создана с [LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиль).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `cxWidth`  
 Задает ширину в пикселях всех столбцов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>CListBox::SetCurSel  
 Выбирает строку и прокручивается в представлении, при необходимости.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Параметры  
 `nSelect`  
 Задает отсчитываемый от нуля индекс строки для выбора. Если `nSelect` равно -1, имеет значение списка выбора не имеют.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `LB_ERR`При возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 При выборе новой строки списка удаляет выделение из ранее выбранной строки.  
  
 Используйте эту функцию-член только с единственным выбором списки.  
  
 Чтобы задать или удалить выбор в поле со списком с множественным выбором, используйте [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>CListBox::SetHorizontalExtent  
 Задает ширину в пикселях, на которое поле со списком может прокручиваться по горизонтали.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Параметры  
 *cxExtent*  
 Задает количество пикселей, на которое списка может прокручиваться по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Если размер поля меньше, чем это значение, горизонтальная полоса прокрутки по горизонтали прокручивает элементы в поле со списком. Если список имеет как большие или превышающими это значение, горизонтальная полоса прокрутки будет скрыта.  
  
 Ответ на вызов `SetHorizontalExtent`, списке должно определено с [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) стиля.  
  
 Эта функция-член неприменим к нескольким столбцам списки. Списки по нескольким столбцам, вызовите `SetColumnWidth` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>CListBox::SetItemData  
 Задает 32-разрядное значение, связанное с указанным элементом в поле со списком.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
 `dwItemData`  
 Задает значение, связанное с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>CListBox::SetItemDataPtr  
 Задает 32-разрядное значение, связанное с указанным элементом в поле со списком указанный указатель ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
 `pData`  
 Указывает указатель, связанный с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель остается допустимым в течение жизненного цикла поле со списком, несмотря на то, что относительное положение данного элемента в списке может измениться при добавлении и удалении элементов. Таким образом индекс элемента в поле можно изменить, но указатель остается надежным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>CListBox::SetItemHeight  
 Задает высоту элементов в поле со списком.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список содержит **LBS_OWNERDRAWVARIABLE** стиля; в противном случае оно должно иметь значение 0.  
  
 `cyItemHeight`  
 Высота в пикселях элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** Если недопустимый индекс или высоту.  
  
### <a name="remarks"></a>Примечания  
 Если список содержит [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля, эта функция задает высоту элемента, заданного параметром `nIndex`. В противном случае эта функция задает высоту всех элементов в поле со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>CListBox::SetLocale  
 Задает идентификатор языкового стандарта для этого списка.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLocale`  
 Новое значение языкового стандарта идентификатор (LCID), чтобы задать для поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение языкового стандарта код (LCID) для этого списка.  
  
### <a name="remarks"></a>Примечания  
 Если **SetLocale** не вызывается, значение по умолчанию языковой стандарт, полученной из системы. Этот язык системы по умолчанию можно изменить с помощью панели управления язык (или международной) приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>CListBox::SetSel  
 Выбирает строку в поле со списком с множественным выбором.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс строки, задаваемый. Если значение -1, выделенный фрагмент добавлены или удалены из всех строк, в зависимости от значения `bSelect`.  
  
 `bSelect`  
 Указывает, как выбрать в списке. Если `bSelect` — `TRUE`, выбран и выделяются; Если строка `FALSE`, выделение удаляется, и строка теряет фокус. Указанная строка выбран и выделяются по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `LB_ERR`При возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только с множественным выбором списки.  
  
 Чтобы выбрать элемент из списка единственным выбором, используйте [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="settabstops"></a>CListBox::SetTabStops  
 Задает позиции табуляции в поле со списком.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Параметры  
 `cxEachStop`  
 Позиции табуляции устанавливаются на каждый `cxEachStop` единицы диалогового окна. В разделе *rgTabStops* описание единицы диалогового окна.  
  
 `nTabStops`  
 Указывает количество позиций табуляции для того, в окне списка.  
  
 `rgTabStops`  
 Указывает на первый элемент массива целых чисел, содержащий позиций табуляции в диалоговых единицах. Единица размера диалогового окна является горизонтальное или вертикальное расстояние. Единицы диалогового окна горизонтальной равен одной четвертой текущий блок базовый ширины диалогового окна и единицы диалогового окна вертикальная равен одну восьмую текущий блок высота основы диалогового окна. Базовые единицы диалогового окна вычисляются в зависимости от высоты и ширины текущего системного шрифта. **GetDialogBaseUnits** Windows функция возвращает базовых единиц текущего диалогового окна в пикселях. Позиции табуляции, которые должны быть отсортированы по возрастанию; Обратная табуляция не допускаются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если были заданы все знаки табуляции; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить позиции табуляции по умолчанию размер 2 единицы диалогового окна, вызовите конструктор версию эта функция-член. Чтобы установить позицию табуляции до размера, 2, вызовите версию с `cxEachStop` аргумент.  
  
 Чтобы установить позиции табуляции массив размеров, используйте версию с `rgTabStops` и `nTabStops` аргументы. Позиции табуляции, которые будут задаваться для каждого значения в `rgTabStops`, вплоть до номера, указанного в `nTabStops`.  
  
 Ответ на вызов `SetTabStops` функция-член списка должен быть создан с [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>CListBox::SetTopIndex  
 Обеспечивает видимость элемента определенного списка.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ноль при успешном завершении, или **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Система выполняет прокрутку списка до элемента, заданного параметром `nIndex` отображается в верхней части списка достигнут диапазона максимальную прокрутку или поля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>CListBox::VKeyToItem  
 Вызывается платформой при получении списка родительскому окну `WM_VKEYTOITEM` сообщения из списка.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nKey`  
 Виртуального кода клавиши ключа была нажата. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nIndex`  
 Текущая позиция курсора списков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возврат - 2 для никаких дополнительных действий, - 1 для действия по умолчанию или неотрицательное число, указывающее индекс элемента списка для выполнения действия по умолчанию для нажатия клавиши.  
  
### <a name="remarks"></a>Примечания  
 `WM_VKEYTOITEM` Сообщение отправляется в списке при получении `WM_KEYDOWN` сообщения, но только если списке соответствует оба из следующих действий:  
  
-   Имеет [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) стиля набора.  
  
-   Содержит по крайней мере одного элемента.  
  
 Никогда не следует вызывать эту функцию самостоятельно. Переопределите эту функцию для предоставления собственных обычной обработки сообщений клавиатуры.  
  
 Должен возвращать значение, чтобы сообщить платформе, какое действие выполняется переопределение. Возвращаемое значение, равное - 2 показывает, что приложение обрабатывать все аспекты выберите нужный элемент и не требует дальнейших действий в списке. Возвращение до - 2, можно выбрать в списке или переместите курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Чтобы переместить курсор, используйте [SetCaretIndex](#setcaretindex).  
  
 Возвращаемое значение - 1 указывает, что поле списка должен выполнить действия по умолчанию в ответ на нажатие клавиши. Реализация по умолчанию возвращается значение-1.  
  
 Возвращаемое значение 0 или больше указывает индекс элемента в поле со списком и указывает, что поле списка следует выполнить действия по умолчанию нажатие клавиши на данный элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLTEST](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)   
 [CComboBox-класс](../../mfc/reference/ccombobox-class.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)   
 [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md)   
 [Класс CStatic](../../mfc/reference/cstatic-class.md)
