---
title: "CListBox-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CListBox class
- list boxes
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: 26
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
ms.openlocfilehash: f4df970f2df35d399c0c700cf504a76482ad3f6d
ms.lasthandoff: 02/24/2017

---
# <a name="clistbox-class"></a>CListBox-класс
Предоставляет функции списка Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CListBox : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CListBox::CListBox](#clistbox)|Создает объект `CListBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|Добавляет строку в поле со списком.|  
|[CListBox::CharToItem](#chartoitem)|Переопределение для обеспечения настраиваемого `WM_CHAR` обработки для рисования владельцем списков, которых нет строк.|  
|[CListBox::CompareItem](#compareitem)|Вызывается платформой для определения положения элемента в списке отсортированный рисование владельцем.|  
|[CListBox::Create](#create)|Поле списка Windows создает и присоединяет его к `CListBox` объекта.|  
|[CListBox::DeleteItem](#deleteitem)|Вызывается платформой, когда пользователь удаляет элемент из списка рисование владельцем.|  
|[CListBox::DeleteString](#deletestring)|Удаляет строку из списка.|  
|[CListBox::Dir](#dir)|Добавляет имена файлов, дисков или оба из текущего каталога в поле со списком.|  
|[CListBox::DrawItem](#drawitem)|Вызывается инфраструктурой при изменении внешнего вида изменяется список рисование владельцем.|  
|[См](#findstring)|Поиск строки в поле со списком.|  
|[CListBox::FindStringExact](#findstringexact)|Выполняет поиск первой строки списка, которая совпадает с указанной строкой.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Возвращает отсчитываемый от нуля индекс текущего элемента привязки в поле со списком.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Определяет индекс элемента, который имеет прямоугольника фокуса в поле со списком множественного выбора.|  
|[CListBox::GetCount](#getcount)|Возвращает количество строк в поле со списком.|  
|[CListBox::GetCurSel](#getcursel)|Возвращает отсчитываемый от нуля индекс строки, выбранного в поле со списком.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Возвращает ширину в пикселях, что поле со списком может прокручиваться по горизонтали.|  
|[CListBox::GetItemData](#getitemdata)|Возвращает 32-разрядное значение, связанное с элементом списка.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Возвращает указатель на элемент списка.|  
|[CListBox::GetItemHeight](#getitemheight)|Определяет высоту элементов в поле со списком.|  
|[CListBox::GetItemRect](#getitemrect)|Возвращает прямоугольник, ограничивающий элемент списка, как оно отображается в данный момент.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Получает число элементов в столбце.|  
|[CListBox::GetLocale](#getlocale)|Извлекает идентификатор языкового стандарта для списка.|  
|[CListBox::GetSel](#getsel)|Возвращает состояние элемента списка выбора.|  
|[CListBox::GetSelCount](#getselcount)|Возвращает число строк, выбранных в поле со списком множественного выбора.|  
|[CListBox::GetSelItems](#getselitems)|Возвращает индекс строки, выбранной в поле со списком.|  
|[CListBox::GetText](#gettext)|Копирует элемент списка в буфер.|  
|[CListBox::GetTextLen](#gettextlen)|Возвращает длину в байтах элемента списка.|  
|[CListBox::GetTopIndex](#gettopindex)|Возвращает индекс первой видимой строки в поле со списком.|  
|[CListBox::InitStorage](#initstorage)|Выделит место для блоков памяти для строки и элементы списка.|  
|[CListBox::InsertString](#insertstring)|Вставляет строку в определенном месте в списке.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Возвращает индекс ближайшего точку элемента списка.|  
|[CListBox::MeasureItem](#measureitem)|Вызывается инфраструктурой при создании списка рисование владельцем для определения списка измерений.|  
|[CListBox::ResetContent](#resetcontent)|Удаляет все записи из списка.|  
|[CListBox::SelectString](#selectstring)|Поиск и выбирает строку в поле со списком одиночным выбором.|  
|[CListBox::SelItemRange](#selitemrange)|Выбирает или отменяет выделение диапазона строк в поле со списком множественного выбора.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Задает привязку в поле со списком множественного выбора, чтобы начать расширенного выделения.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Задает прямоугольник фокуса на элемент по указанному индексу в поле со списком множественного выбора.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Задает ширину столбца список из нескольких столбцов.|  
|[CListBox::SetCurSel](#setcursel)|Выбирает строку списка.|  
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|Задает ширину в пикселях, что поле со списком может прокручиваться по горизонтали.|  
|[CListBox::SetItemData](#setitemdata)|Задает 32-разрядное значение, связанное с элементом списка.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Задает указатель на элемент списка.|  
|[CListBox::SetItemHeight](#setitemheight)|Задает высоту элементов в поле со списком.|  
|[CListBox::SetLocale](#setlocale)|Задает идентификатор языкового стандарта для списка.|  
|[CListBox::SetSel](#setsel)|Выбор или Отмена элемент списка в поле со списком множественного выбора.|  
|[CListBox::SetTabStops](#settabstops)|Задает позиции табуляции в поле со списком.|  
|[CListBox::SetTopIndex](#settopindex)|Задает отсчитываемый от нуля индекс первой видимой строки в поле со списком.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Переопределение для обеспечения настраиваемого `WM_KEYDOWN` обработки для списков с **LBS_WANTKEYBOARDINPUT** набор стилей.|  
  
## <a name="remarks"></a>Примечания  
 Отображает список элементов, таких как имена файлов, который пользователь может просмотреть и выбрать.  
  
 В поле со списком единственного выбора пользователь может выбрать только один элемент. В поле со списком множественного выбора можно выбрать диапазон элементов. Когда пользователь выбирает элемент, он выделяется и списке отправляет сообщение уведомления родительского окна.  
  
 Поле со списком можно создать из шаблона диалогового окна или непосредственно в коде. Чтобы напрямую создать построить `CListBox` объекта, а затем вызвать [создать](#create) функции-члена для создания элемента управления списка Windows и присоединить его к `CListBox` объекта. Чтобы использовать поле со списком в шаблона диалогового окна, объявите переменную в классе диалогового окна списка, а затем используйте `DDX_Control` в классе диалогового окна `DoDataExchange` функции для подключения переменную-член для элемента управления. (это выполняется за вас автоматически при добавлении переменной элемента управления в классе диалогового окна.)  
  
 Построение может быть задачей в класс, производный от `CListBox`. Создание конструктора для производного класса и вызове **создать** из внутри конструктора.  
  
 Если требуется обрабатывать сообщения уведомления Windows, отправляемые поле со списком с родительским (обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)), добавление карты сообщение входа и обработчик сообщений функции-члена родительский класс для каждого сообщения.  
  
 Каждая запись сопоставления сообщений имеет следующий вид:  
  
 `ON_Notification( id, memberFxn )`  
  
 где `id` указывает идентификатор дочернего окна элемента управления списка, отправку уведомления, и `memberFxn` имя родительской функции члена, написанный для обработки уведомления.  
  
 Прототип функции родительского выглядит следующим образом:  
  
 `afx_msg void memberFxn( );`  
  
 Ниже приведен список потенциальных записей сопоставления сообщений и описание вариантов, в которых они были бы отправлены родительского.  
  
- **ON_LBN_DBLCLK** пользователь дважды щелкает строку в поле со списком. Только поле со списком, который имеет [LBS_NOTIFY](../../mfc/reference/list-box-styles.md) стиль будет отправлять это сообщение уведомления.  
  
- **ON_LBN_ERRSPACE** списка не может выделить достаточно памяти для удовлетворения запроса.  
  
- **ON_LBN_KILLFOCUS** списке теряет фокус ввода.  
  
- **ON_LBN_SELCANCEL** выбранного списка отменяется. Это сообщение отправляется только в том случае, если список содержит **LBS_NOTIFY** стиль.  
  
- **ON_LBN_SELCHANGE** изменения выбора в поле со списком. Это уведомление не отправляется при изменении выделения [CListBox::SetCurSel](#setcursel) функции-члена. Данное уведомление относится только к поле со списком, который имеет **LBS_NOTIFY** стиль. **LBN_SELCHANGE** отправляется уведомление для списка множественного выбора всякий раз, когда пользователь нажимает клавишу со стрелкой, даже если изменяется.  
  
- **ON_LBN_SETFOCUS** списка получает фокус ввода.  
  
- **ON_WM_CHARTOITEM** Получает список рисование владельцем, никакие строки не имеет `WM_CHAR` сообщение.  
  
- **ON_WM_VKEYTOITEM** список с **LBS_WANTKEYBOARDINPUT** получает стиль `WM_KEYDOWN` сообщение.  
  
 При создании `CListBox` объекта в диалоговое окно (с помощью ресурса диалогового окна), `CListBox` объект автоматически уничтожается, когда пользователь закрывает окно.  
  
 При создании `CListBox` объекта в окне, может потребоваться уничтожить `CListBox` объекта. При создании `CListBox` объекта в стеке удаляется автоматически. При создании `CListBox` объектов в куче с помощью **новый** функции, необходимо вызвать **удаление** для объекта, чтобы уничтожить его, когда пользователь закрывает родительского окна.  
  
 Если выделять память в `CListBox` объекта, переопределить `CListBox` деструктор для удаления выделения.  
  
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
 Указывает на строку символом null, должен быть добавлен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс строки в списке. Возвращаемое значение является **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для сохранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 Если в списке не был создан с [LBS_SORT](../../mfc/reference/list-box-styles.md) стиль, строка добавляется в конец списка. В противном случае — строка вставляется в списке, и список отсортирован. Если поле списка был создан с **LBS_SORT** стиля, но не [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) стиль, платформа список сортируется по одной или нескольких вызовов `CompareItem` функции-члена.  
  
 Используйте [InsertString](#insertstring) для вставки строки в указанное место в списке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#3;](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>CListBox::CharToItem  
 Вызывается инфраструктурой при получении списка родительского окна `WM_CHARTOITEM` сообщения из списка.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nKey`  
 Код ANSI знака, введенный пользователем.  
  
 `nIndex`  
 Текущая позиция курсора списков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает – 1 или -2 для дальнейших действий или неотрицательное число, указывающее индекс элемента списка для выполнения действия по умолчанию для клавиши. Реализация по умолчанию возвращает – 1.  
  
### <a name="remarks"></a>Примечания  
 `WM_CHARTOITEM` Сообщение отправляется в списке при получении `WM_CHAR` сообщения, но только если поле списка соответствует всем этим критериям:  
  
-   Представляет список рисование владельцем.  
  
-   Не имеет [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) набор стилей.  
  
-   Содержит по крайней мере один элемент.  
  
 Никогда не должны вызвать эту функцию самостоятельно. Переопределите эту функцию, чтобы предоставить собственную пользовательскую обработку сообщения клавиатуры.  
  
 Во время переопределения должны возвращать значение платформа определить, какие действия. Возвращаемое значение – 1 или -2 указывает обрабатываются все аспекты выбора элемента и не требует дальнейших действий в списке. Перед возвратом – 1 или -2, можно выбрать в списке или переместить курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Для перемещения курсора используйте [SetCaretIndex](#setcaretindex).  
  
 Возвращаемое значение 0 или больше указывает индекс элемента в списке и указывает, что поле списка должен выполнить действие по умолчанию для клавиши на данный элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#4;](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>CListBox::CListBox  
 Создает объект `CListBox`.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Примечания  
 Создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор **ClistBox** , а затем вызвать **создать**, который инициализирует списка Windows и присоединяет его к `CListBox`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#1;](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CListBox::CompareItem  
 Вызывается средой, чтобы определить относительное положение элемента в списке отсортированный рисование владельцем.  
  
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
|–1|Сортирует элемент 1 до 2 элемента.|  
|0|1 и 2 элемент сортировки же.|  
|1|Сортирует элемент 1 после элемента 2.|  
  
 В разделе [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) описание `COMPAREITEMSTRUCT` структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. При создании списка рисование владельцем **LBS_SORT** стиль, необходимо переопределить эту функцию-член для платформы сортировка новые элементы, добавленные в список.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#5;](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>CListBox::Create  
 Поле списка Windows создает и присоединяет его к `CListBox` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль окна списка. Примените любое сочетание [стили списков](../../mfc/reference/list-box-styles.md) в поле.  
  
 `rect`  
 Указывает размер списка и положение. Может быть либо `CRect` объекта или `RECT` структуры.  
  
 `pParentWnd`  
 Указывает список родительского окна (обычно `CDialog` объекта). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CListBox` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который инициализирует списка Windows и присоединяет его к `CListBox` объекта.  
  
 Когда **создать** выполняет Windows отправляет [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) сообщений в элементе управления списка.  
  
 Эти сообщения обрабатываются по умолчанию с помощью [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), и [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) функции-члены в `CWnd` базового класса. Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CListBox`, Добавление нового класса схемы сообщений и переопределить выше функции-члены обработчик сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Примените следующий [стили окна](../../mfc/reference/window-styles.md) в элемент управления "список".  
  
- **WS_CHILD** всегда  
  
- **WS_VISIBLE** обычно  
  
- **WS_DISABLED** редко  
  
- **WS_VSCROLL** для добавления вертикальной полосы прокрутки  
  
- **WS_HSCROLL** для добавления горизонтальной полосы прокрутки  
  
- **WS_GROUP** для группирования элементов управления  
  
- **WS_TABSTOP** чтобы разрешить переход к этому элементу управления  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#2;](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>CListBox::DeleteItem  
 Вызывается платформой, когда пользователь удаляет элемент из рисование владельцем `CListBox` объекта или удаляет поле списка.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDeleteItemStruct`  
 Длинный указатель Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) структуру, содержащую сведения о удаляемого элемента.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для перерисовки списка рисование владельцем при необходимости.  
  
 В разделе [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) описание `DELETEITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox №&6;](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>CListBox::DeleteString  
 Удаляет элемент в позиции `nIndex` из списка.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс удаляемой строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество строк, оставшихся в списке. Возвращаемое значение является **LB_ERR** Если `nIndex` указывает индекс больше числа элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Все элементы `nIndex` теперь вниз на одну позицию. Например если поле со списком содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первой позиции. `nIndex`=&0; в позиции первого элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#7;](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>CListBox::Dir  
 Добавляет список имен файлов, дисков и/или поле со списком.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Параметры  
 `attr`  
 Может быть любым сочетанием `enum` значения описано в **CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus), или любое сочетание следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|0x0000|Файл для чтения и записи.|  
|0x0001|Файл может считываться, но не записываются.|  
|0x0002|Файл является скрытым и не отображается в каталоге.|  
|0x0004|Файл является системным файлом.|  
|0x0010|Имя, указанное в `lpszWildCard` указывает каталог.|  
|0x0020|Файл заархивирован.|  
|0x4000|Включить все диски, которые соответствуют имени, заданному в `lpszWildCard`.|  
|0x8000|Флаг exclusive. Если флаг exclusive перечислены только файлы указанного типа. В противном случае — помимо файлов «normal» отображаются файлы указанного типа.|  
  
 `lpszWildCard`  
 Указывает строку спецификация файла. Строка может содержать подстановочные знаки (например, *.\*).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс последнего имени файла добавляется в список. Возвращаемое значение является **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для хранения новых строк.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox №&8;](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>CListBox::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида изменяется список рисование владельцем.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Длинный указатель [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** и **itemState** члены `DRAWITEMSTRUCT` структуры определяют рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CListBox` объекта. Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` перед этим членом завершении функции.  
  
 В разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание `DRAWITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox №&9;](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>См  
 Находит первую строку в поле со списком, который содержит указанный префикс без изменения списков выбора.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nStartAfter`. Если `nStartAfter` –&1;, весь список просматривается с самого начала.  
  
 `lpszItem`  
 Указывает нулем строка, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента сопоставления или **LB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Используйте [SelectString](#selectstring) функции-члена для поиска и выберите строку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#10;](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>CListBox::FindStringExact  
 Находит первый списка строку, соответствующую строку, указанную в `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndexStart`  
 Задает отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nIndexStart`. Если `nIndexStart` –&1;, весь список просматривается с самого начала.  
  
 `lpszFind`  
 Указывает на строку, завершающуюся значением null для поиска. Эта строка может содержать полное имя файла, включая расширение. Поиск не чувствителен к регистру, поэтому строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента сопоставления или **LB_ERR** , если не удалось выполнить поиск.  
  
### <a name="remarks"></a>Примечания  
 Если поле списка был создан с стиль рисования владельцем, но без [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) стиль, `FindStringExact` функции-члена пытается сопоставить двойное значение со значением `lpszFind`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&11;](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>CListBox::GetAnchorIndex  
 Возвращает отсчитываемый от нуля индекс текущего элемента привязки в списке.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс текущего элемента привязки, в случае успешного выполнения; в противном случае **LB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 В поле список с множественным выбором элемент привязки является первый или последний элемент в блоке смежных выбранных элементов.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="getcaretindex"></a>CListBox::GetCaretIndex  
 Определяет индекс элемента, который имеет прямоугольника фокуса в поле со списком множественного выбора.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента, который имеет прямоугольника фокуса в поле со списком. Если поле со списком для выбора одного списка, возвращается индекс элемента, который выбран, при их наличии.  
  
### <a name="remarks"></a>Примечания  
 Элемент может или не может быть выбран.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="getcount"></a>CListBox::GetCount  
 Получает число элементов в поле со списком.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в поле со списком или **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Количество возвращаемых результатов, больше, чем значение индекса последнего элемента (индекс начинается с нуля).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#12;](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>CListBox::GetCurSel  
 Получает отсчитываемый от нуля индекс текущего выделенного элемента, если в поле со списком для выбора одного.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущего выделенного элемента, если это поле со списком выбора одного. Это `LB_ERR` , если элемент не выбран в данный момент.  
  
 В поле список с множественным выбором, индекс элемента, который находится в фокусе.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать `GetCurSel` для списка множественного выбора. Используйте [CListBox::GetSelItems](#getselitems) вместо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#13;](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent  
 Получает ширину в пикселях, на которое он может прокручиваться по горизонтали в окне списка.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина прокрутки окна списка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Это применимо только в том случае, если список содержит горизонтальную полосу прокрутки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#14;](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>CListBox::GetItemData  
 Получает значение двойного слова, предоставляемый приложением, связанные с элементом указанного списка.  
  
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
 [!code-cpp[NVC_MFC_CListBox&#15;](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>CListBox::GetItemDataPtr  
 Возвращает значение 32-разрядных предоставляемый приложением, связанное с элементом указанного списка как указатель ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель или значение -1, если произошла ошибка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox №&16;](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>CListBox::GetItemHeight  
 Определяет высоту элементов в поле со списком.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список содержит **LBS_OWNERDRAWVARIABLE** стиль; в противном случае — он должен быть равным 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях элементов в поле со списком. Если список содержит [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) стиль, возвращаемое значение имеет высоту элемента, заданного параметром `nIndex`. При возникновении ошибки возвращается **LB_ERR**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&17;](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>CListBox::GetItemRect  
 Получает размеры прямоугольника границ поле со списком элемента как в данный момент отображается в окне списка.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
 `lpRect`  
 Указывает длинный указатель [структура RECT](../../mfc/reference/rect-structure1.md) , получающий клиентских координат элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&18;](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>CListBox::GetListBoxInfo  
 Получает число элементов в столбце.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов на столбец `CListBox` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) сообщений, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlocale"></a>CListBox::GetLocale  
 Извлекает языковой стандарт, используемый в списке.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение идентификатора (LCID) языка для строк в окне списка.  
  
### <a name="remarks"></a>Примечания  
 Языковой стандарт используется, например, для определения порядка сортировки строк в отсортированном списке.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::SetLocale](#setlocale).  
  
##  <a name="getsel"></a>CListBox::GetSel  
 Получает состояние выбора элемента.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положительное число, если указанный элемент выделен; в противном случае — 0. Возвращает значение `LB_ERR` при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает с обоих Выбор одного и нескольких списков.  
  
 Для извлечения индекса элемента списка, выбранной в данный момент, используйте [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&19;](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>CListBox::GetSelCount  
 Получает общее количество выбранных элементов в поле список с множественным выбором.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число выбранных элементов в поле со списком. Если поле со списком для выбора одного списка, возвращается **LB_ERR**.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::GetSelItems](#getselitems).  
  
##  <a name="getselitems"></a>CListBox::GetSelItems  
 Заполняет буфер массива целых чисел, указывающее элемент числа выбранных элементов в поле со списком множественного выбора.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxItems`  
 Указывает максимальное количество выбранных элементов, чьи номера элемента, должно быть помещено в буфер.  
  
 `rgIndex`  
 Задает указатель на буфер, достаточное количество целых чисел, определяемое `nMaxItems`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактическое число элементов, помещаются в буфер. Если поле со списком для выбора одного списка, возвращается `LB_ERR`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&20;](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="gettext"></a>CListBox::GetText  
 Возвращает строку, из списка.  
  
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
 Задает отсчитываемый от нуля индекс строки для извлечения.  
  
 `lpszBuffer`  
 Указывает на буфер, принимающий строку. Буфер должен иметь достаточно места для и завершающий символ null. Размер строки можно определить заранее путем вызова `GetTextLen` функции-члена.  
  
 `rString`  
 Ссылка на объект `CString`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки, исключая конечный символ null (в байтах). Если `nIndex` не указан допустимый индекс, возвращается значение **LB_ERR**.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма этого члена функции заливки `CString` вместе с текстом строки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#21;](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>CListBox::GetTextLen  
 Возвращает длину строки в элементе списка.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина строки в символах, за исключением завершающий символ null. Если `nIndex` не указан допустимый индекс, возвращается значение **LB_ERR**.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::GetText](#gettext).  
  
##  <a name="gettopindex"></a>CListBox::GetTopIndex  
 Возвращает отсчитываемый от нуля индекс первой видимой позиции в списке.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первой видимой позиции в поле со списком, в случае успешного выполнения **LB_ERR** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Первоначально элемент 0 находится в верхней части списка, но если прокрутку списка, наверху может оказаться другой элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#22;](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="initstorage"></a>CListBox::InitStorage  
 Выделяет память для хранения элементов списка.  
  
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
 При успешном выполнении максимальное количество элементов, можно хранить в списке перед перераспределение памяти требуется **LB_ERRSPACE**, доступна, то есть не хватает памяти.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается перед добавлением большое количество элементов `CListBox`.  
  
 Эта функция помогает ускорить инициализации список полей, имеющих большое число элементов (более 100). Он выделит место указанный объем памяти, поэтому последующие [AddString](#addstring), [InsertString](#insertstring), и [Dir](#dir) функции принимают кратчайший срок. Оценки можно использовать для параметров. Если вы пересмотреть некоторый дополнительный объем памяти выделяется; Если вы недооценивать обычного выделения используется для элементов, которые больше предварительно выделенной.  
  
 Windows 95/98 только: `nItems` ограничен 16-разрядных значений. Это означает, что списки не может содержать более 32 767 элементов. Несмотря на то, что количество элементов является ограниченным, общий размер элементов в поле со списком ограничено только объемом доступной памяти.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#23;](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>CListBox::InsertString  
 Вставляет строку в поле со списком.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс позиции, вставляется строка. Если этот параметр имеет значение –1, строка добавляется в конец списка.  
  
 `lpszItem`  
 Указывает на оканчивающуюся символом NULL строку, которую нужно вставить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс позиции, в которую была вставлена строка. Возвращаемое значение является **LB_ERR** ; при возникновении ошибки возвращается **LB_ERRSPACE** Если недостаточно места для сохранения новой строки.  
  
### <a name="remarks"></a>Примечания  
 В отличие от [AddString](#addstring) функции-члена `InsertString` не ведет список с [LBS_SORT](../../mfc/reference/list-box-styles.md) стиль сортировки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#24;](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>CListBox::ItemFromPoint  
 Определяет элемент списка ближайшую точку, указанную в `pt`.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Точка, для которой необходимо найти ближайшего элемента, указанных относительно левого верхнего угла клиентской области окна списка.  
  
 `bOutside`  
 Ссылка на `BOOL` переменной, которой будет присвоено `TRUE` Если `pt` находится вне клиентской области ближайшего элемента списка, `FALSE` Если `pt` находится внутри области ближайшего элемента списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, ближайшего к точке, указанной в `pt`.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно позволяет определять, какой элемент списка наводится указатель мыши.  
  
### <a name="example"></a>Пример  
  В примере показано [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="measureitem"></a>CListBox::MeasureItem  
 Вызывается инфраструктурой при создании списка стилей рисования владельцем.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Длинный указатель [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows из списка измерений. При создании списка с [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) стиль, платформа вызывает эту функцию-член для каждого элемента в списке. В противном случае этот член вызывается только один раз.  
  
 Дополнительные сведения об использовании [LBS_OWNERDRAWFIXED](../../mfc/reference/list-box-styles.md) стиля в списке рисование владельцем, созданные с `SubclassDlgItem` функцию-член `CWnd`, см. обсуждение в [14 технических Примечание](../../mfc/tn014-custom-controls.md).  
  
 В разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры **.**  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#25;](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>CListBox::ResetContent  
 Удаляет все элементы из списка.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#26;](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>CListBox::SelectString  
 Поиск элемента списка, совпадающий с указанной строкой, а если соответствующий элемент найден, он выбирает элемент.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nStartAfter`  
 Содержит отсчитываемый от нуля индекс элемента перед первым элементом, в котором производится поиск. Когда поиск достигает конца списка, он продолжает в верхней части списка обратно элемента, заданного параметром `nStartAfter`. Если `nStartAfter` –&1;, весь список просматривается с самого начала.  
  
 `lpszItem`  
 Указывает нулем строка, содержащая префикс для поиска. Поиск ситуация независимые, поэтому эта строка может содержать любое сочетание прописных и строчных букв.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выбранного элемента, если поиск был успешным. Если поиск завершилась ошибкой, возвращается **LB_ERR** и текущего выделения не изменяется.  
  
### <a name="remarks"></a>Примечания  
 Прокрутка списка, при необходимости, для отображения выбранного элемента в представлении.  
  
 Эта функция-член не может использоваться со списком, который имеет [LBS_MULTIPLESEL](../../mfc/reference/list-box-styles.md) стиль.  
  
 Элемент выбран только в том случае, если его начальных символов (от начальной) соответствует символов в строки, заданной параметром `lpszItem`.  
  
 Используйте `FindString` функции-члена для поиска строки без выбора элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#27;](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>CListBox::SelItemRange  
 Выделяет несколько последовательных элементов в поле со списком множественного выбора.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Параметры  
 `bSelect`  
 Указывает, как выбрать в списке. Если `bSelect` — **TRUE**, выбран и выделяются; Если строка **FALSE**, выделение удаляется, и строка теряет фокус.  
  
 `nFirstItem`  
 Задает отсчитываемый от нуля индекс первого элемента в набор.  
  
 `nLastItem`  
 Задает отсчитываемый от нуля индекс последнего элемента в набор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только с множественным выбором списки. Если необходимо выбрать только один элемент в поле со списком множественного выбора — то есть, если `nFirstItem` равен `nLastItem` — вызвать [SetSel](#setsel) вместо этого функция-член.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#28;](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>CListBox::SetAnchorIndex  
 Задает привязку в поле со списком множественного выбора, чтобы начать расширенного выделения.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента списка, который будет служить в качестве привязки.  
  
### <a name="remarks"></a>Примечания  
 В поле список с множественным выбором элемент привязки является первый или последний элемент в блоке смежных выбранных элементов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#29;](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>CListBox::SetCaretIndex  
 Задает прямоугольник фокуса на элемент по указанному индексу в поле со списком множественного выбора.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента для получения прямоугольника фокуса в поле со списком.  
  
 *bScroll*  
 Если это значение равно 0, элемент при прокрутке, пока он не будет полностью видимой. Если это значение не равно 0, элемент прокручиваться, пока он не будет хотя бы частично видимой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Если элемент не отображается, его в области просмотра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#30;](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>CListBox::SetColumnWidth  
 Задает ширину в пикселях всех столбцов в список из нескольких столбцов (с [LBS_MULTICOLUMN](../../mfc/reference/list-box-styles.md) стиль).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `cxWidth`  
 Задает ширину в пикселях всех столбцов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#31;](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>CListBox::SetCurSel  
 Выбирает строку и прокручивается в представлении, при необходимости.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Параметры  
 `nSelect`  
 Задает отсчитываемый от нуля индекс строки для выбора. Если `nSelect` –&1;, списке задано для выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `LB_ERR`При возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 При выборе новой строки в списке снимает выделение с ранее выбранной строки.  
  
 Используйте эту функцию-член только с одиночным выбором списки.  
  
 Чтобы задать или удалить выбор в поле список с множественным выбором, используйте [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#32;](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>CListBox::SetHorizontalExtent  
 Задает ширину в пикселях, на которое поле со списком может прокручиваться по горизонтали.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Параметры  
 *cxExtent*  
 Задает количество пикселей, на которое списка может прокручиваться по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Если размер поля меньше, чем это значение, горизонтальная полоса прокрутки по горизонтали прокручивает элементов в поле со списком. Если список имеет как больших или превышающими это значение, скрывается горизонтальной полосы прокрутки.  
  
 В ответ на вызов `SetHorizontalExtent`, списке должно определено с [WS_HSCROLL](../../mfc/reference/window-styles.md) стиль.  
  
 Эта функция-член не является полезным для нескольких столбцов списков. Списки по нескольким столбцам, вызовите `SetColumnWidth` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#33;](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>CListBox::SetItemData  
 Задает 32-разрядное значение, связанное с указанным элементом в списке.  
  
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
 [!code-cpp[NVC_MFC_CListBox&#34;](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>CListBox::SetItemDataPtr  
 Задает 32-разрядное значение, связанное с указанного элемента в поле со списком указанный указатель ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента.  
  
 `pData`  
 Задает указатель, связанный с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель остается допустимым в течение времени жизни окна списка, несмотря на то, что относительное положение элемента в списке могут измениться при добавлении и удалении элементов. Таким образом индекс элемента в поле можно изменить, но указатель остается надежным.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#35;](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>CListBox::SetItemHeight  
 Задает высоту элементов в поле со списком.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Задает отсчитываемый от нуля индекс элемента в списке. Этот параметр используется только в том случае, если список содержит **LBS_OWNERDRAWVARIABLE** стиль; в противном случае — он должен быть равным 0.  
  
 `cyItemHeight`  
 Высота в пикселях элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **LB_ERR** Если недопустимый индекс или высоту.  
  
### <a name="remarks"></a>Примечания  
 Если список содержит [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) стиль, эта функция устанавливает высоту элемента, заданного параметром `nIndex`. В противном случае эта функция устанавливает высоту всех элементов в поле со списком.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#36;](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>CListBox::SetLocale  
 Задает идентификатор языкового стандарта для этого списка.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewLocale`  
 Новое значение языкового стандарта идентификатор (LCID), чтобы задать для поля со списком.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение идентификатора (LCID) языка для этого списка.  
  
### <a name="remarks"></a>Примечания  
 Если **SetLocale** не вызывается, по умолчанию языкового стандарта, полученная от системы. Этот язык системы по умолчанию можно изменить с помощью панели управления Язык и International.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#37;](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>CListBox::SetSel  
 Выбирает строку в поле со списком множественного выбора.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Содержит отсчитываемый от нуля индекс строки. Если значение –&1;, выбор добавляемые или удаляемые из всех строк, в зависимости от значения `bSelect`.  
  
 `bSelect`  
 Указывает, как выбрать в списке. Если `bSelect` — `TRUE`, выбран и выделяются; Если строка `FALSE`, выделение удаляется, и строка теряет фокус. Указанная строка выбран и выделен по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `LB_ERR`При возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только с множественным выбором списки.  
  
 Чтобы выбрать элемент из списка один, используйте [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#38;](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
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
 Указывает количество позиций табуляции в окне списка.  
  
 `rgTabStops`  
 Указывает на первый элемент массива целых чисел, содержащий позиций табуляции в единицах диалогового окна. Единица диалогового окна — горизонтальное или вертикальное расстояние. Одна единица горизонтальной диалогового окна равен одной четвертой текущей единице измерения базового ширину диалогового окна и одну единицу вертикальной диалоговое окно равно одну восьмую Текущая единица высота основы диалоговое окно. Базовые единицы диалогового окна вычисляются на основе высота и ширина текущего системного шрифта. **GetDialogBaseUnits** функции Windows возвращает единицу текущего диалогового окна в пикселях. Позиции табуляции должны быть отсортированы по возрастанию; Обратная табуляция не допускаются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если были установлены на всех вкладках; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить табуляции размером 2 единицы диалогового окна по умолчанию, вызовите версию без параметров эта функция-член. Чтобы установить позицию табуляции до размера, 2, вызовите версию с `cxEachStop` аргумент.  
  
 Чтобы установить табуляции в массив размеров, используйте версию с `rgTabStops` и `nTabStops` аргументы. Позиции табуляции, которые будут задаваться для каждого значения в `rgTabStops`, вплоть до номера, указанного в `nTabStops`.  
  
 В ответ на вызов `SetTabStops` функция-член списка должен быть создан с помощью [LBS_USETABSTOPS](../../mfc/reference/list-box-styles.md) стиль.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#39;](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
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
 Система выполняет прокрутку списка до элемента, заданного параметром `nIndex` отображается в верхней части списка достигнуто максимальное прокрутки диапазона или поля.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#40;](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>CListBox::VKeyToItem  
 Вызывается инфраструктурой при получении списка родительского окна `WM_VKEYTOITEM` сообщения из списка.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nKey`  
 Виртуальный код клавиши ключа была нажата. Список стандартных кодов виртуального ключа см. в разделе Winuser.h  
  
 `nIndex`  
 Текущая позиция курсора списков.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает — 2 дальнейшие действия, – 1 для действия по умолчанию или неотрицательное число, указывающее индекс элемента списка для выполнения действия по умолчанию для клавиши.  
  
### <a name="remarks"></a>Примечания  
 `WM_VKEYTOITEM` Сообщение отправляется в списке при получении `WM_KEYDOWN` сообщения, но только если поле списка соответствует оба следующих:  
  
-   Имеет [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) набор стилей.  
  
-   Содержит по крайней мере один элемент.  
  
 Никогда не должны вызвать эту функцию самостоятельно. Переопределите эту функцию, чтобы предоставить собственную пользовательскую обработку сообщения клавиатуры.  
  
 Должен возвращать значение определить, какое действие выполняется переопределение платформы. Возвращаемое значение — 2 указывает, что приложение обрабатываются все аспекты выбора элемента и не требует дальнейших действий в списке. До возвращения — 2, можно выбрать в списке или переместить курсор или оба. Чтобы выбрать в списке, используйте [SetCurSel](#setcursel) или [SetSel](#setsel). Для перемещения курсора используйте [SetCaretIndex](#setcaretindex).  
  
 Возвращаемое значение-1 указывает, что поле списка должен выполнить действие по умолчанию в ответ на нажатие клавиши. Реализация по умолчанию возвращает – 1.  
  
 Возвращаемое значение 0 или больше указывает индекс элемента в списке и указывает, что поле списка должен выполнить действие по умолчанию для клавиши на данный элемент.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CListBox&#41;](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
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

