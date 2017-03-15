---
title: "CTabCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
dev_langs:
- C++
helpviewer_keywords:
- tab controls
- CTabCtrl class, common controls
- CTabCtrl class
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
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
ms.openlocfilehash: e1d8497b444e4dd5ee1e2803c1a763f67e2e0054
ms.lasthandoff: 02/24/2017

---
# <a name="ctabctrl-class"></a>CTabCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "вкладка" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|Создает объект `CTabCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|Вычисляет набор вкладок площади указанным прямоугольником окна или вычисляет, будет соответствовать области отображения данного прямоугольника окна.|  
|[CTabCtrl::Create](#create)|Создает элемент управления вкладки и присоединяет его к экземпляру `CTabCtrl` объекта.|  
|[CTabCtrl::CreateEx](#createex)|Создает элемент управления вкладки с указанным расширенные стили Windows и присоединяет его к экземпляру `CTabCtrl` объекта.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы из элемента управления вкладками.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Удаляет элемент из элемента управления вкладками.|  
|[CTabCtrl::DeselectAll](#deselectall)|Сбрасывает элементы в элементе управления вкладками, очистки, которые были нажаты.|  
|[CTabCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления "Вкладка".|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Извлекает вкладки с текущим местоположением набор вкладок.|  
|[CTabCtrl::GetCurSel](#getcursel)|Определяет выбранную вкладку в наборе вкладок.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, используемые в данный момент используется для управления "Вкладка".|  
|[CTabCtrl::GetImageList](#getimagelist)|Получает список изображений, связанных с вкладок.|  
|[CTabCtrl::GetItem](#getitem)|Извлекает сведения о вкладке в элементе управления вкладками.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Получает число вкладок в элементе управления вкладками.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник для вкладки в элементе управления вкладками.|  
|[CTabCtrl::GetItemState](#getitemstate)|Получает состояние элемента управления указанной вкладки.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Возвращает текущее число строк из вкладок в наборе вкладок.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Получает дескриптор управления всплывающей подсказки, связанный с элементом управления вкладки.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Задает состояние выделения элемента вкладки.|  
|[CTabCtrl::HitTest](#hittest)|Определяет, какая вкладка, с указанными экранными позиции.|  
|[CTabCtrl::InsertItem](#insertitem)|Вставляет новую вкладку в наборе вкладок.|  
|[CTabCtrl::RemoveImage](#removeimage)|Удаляет изображение из списка изображений набор вкладок.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Устанавливает фокус на указанной вкладки в элементе управления вкладками.|  
|[CTabCtrl::SetCurSel](#setcursel)|Выбор вкладки в элементе управления вкладками.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для элемента управления tab.|  
|[CTabCtrl::SetImageList](#setimagelist)|Назначает списка изображений для элемента управления tab.|  
|[CTabCtrl::SetItem](#setitem)|Задает некоторые или все атрибуты вкладки.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Задает число байтов на вкладке зарезервировано для определяемых приложением данных в элементе управления вкладками.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Задает ширину и высоту элемента.|  
|[CTabCtrl::SetItemState](#setitemstate)|Задает состояние элемента управления указанной вкладки.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Задает минимальную ширину элементов в элементе управления вкладками.|  
|[CTabCtrl::SetPadding](#setpadding)|Задает объем пространства (заполнения) вокруг каждой вкладке значок и метку в наборе вкладок.|  
|[CTabCtrl::SetToolTips](#settooltips)|Присваивает набор вкладок элемента управления всплывающей подсказки.|  
  
## <a name="remarks"></a>Примечания  
 «Вкладка «является аналогом разделителям в записной книжке или меткам в CAB-файла. С помощью элемента управления "Вкладка" приложение может определить несколько страниц для одной области окна или диалогового окна. Каждая страница состоит из набора информации или группы элементов управления, которые приложение отображает, когда пользователь выбирает соответствующую вкладку. Специальный тип элемента управления "Вкладка" отображает вкладки, которые выглядят как кнопки. После нажатия кнопки должны немедленно выполнить команду вместо отображения страницы.  
  
 Этот элемент управления (и, следовательно, `CTabCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Дополнительные сведения об использовании `CTabCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CTabCtrl с помощью](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-nameadjustrecta--ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl::AdjustRect  
 Вычисляет набор вкладок площади указанным прямоугольником окна или вычисляет, будет соответствовать области отображения данного прямоугольника окна.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `bLarger`  
 Указывает операцию для выполнения. Если этот параметр равен **TRUE**, `lpRect` указывает отображаемый прямоугольник и получает соответствующие прямоугольника окна. Если этот параметр равен **FALSE**, `lpRect` указывает прямоугольник окна и получает соответствующие отображаемый прямоугольник.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, которая указывает данного прямоугольника и получает расчетный прямоугольник.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="a-namecreatea--ctabctrlcreate"></a><a name="create"></a>CTabCtrl::Create  
 Создает элемент управления вкладки и присоединяет его к экземпляру `CTabCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления вкладок. Примените любое сочетание [вкладке Стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb760549), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В разделе **примечания** список стилей окна, которые также можно применить к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления "Вкладка". Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает вкладку родительского окна элемента управления, обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления "Вкладка".  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если инициализация объекта выполнена успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Создании `CTabCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает вкладок и присоединяет его к `CTabCtrl` объекта.  
  
 В дополнение к вкладке Стили элемента управления можно применить следующие стили окна вкладки в элемент управления.  
  
- **WS_CHILD** создает дочернего окна, представляющий вкладок элемента управления. Нельзя использовать с `WS_POPUP` стиль.  
  
- **WS_VISIBLE** создает набор вкладок, изначально является видимым.  
  
- **WS_DISABLED** создает окно, которое первоначально будет отключено.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления, в которых пользователь может перемещать из одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с помощью **WS_GROUP** стиля после первого элемента управления относятся к той же группе. Следующий элемент управления с **WS_GROUP** стиль завершает группы стилей и запускает следующей группы (то есть одна группа заканчивается начинается следующий).  
  
- **WS_TABSTOP** указывает один из любого количества элементов, по которым можно перемещаться с помощью клавиши TAB. Пользователь перемещается клавишей TAB к следующему элементу управления, определяемое **WS_TABSTOP** стиль.  
  
 Чтобы создать набор вкладок с расширенные стили окна, вызовите [CTabCtrl::CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="a-namecreateexa--ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связывает его с `CTabCtrl` объекта.  
  
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
 Задает стиль элемента управления вкладок. Примените любое сочетание [вкладке Стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb760549), описанный в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В разделе **примечания** в [создать](#create) список стилей окна, которые также можно применить к элементу управления.  
  
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
  
 `CreateEx`Создает элемент управления с помощью расширенных стилей Windows, заданные `dwExStyle`. Расширенные стили, определенные для элемента управления с помощью набора [SetExtendedStyle](#setextendedstyle). Например, используйте `CreateEx` установка стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` установка стилей, таких как **TCS_EX_FLATSEPARATORS**. Дополнительные сведения см. в разделе стили, описанные в [вкладка управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namectabctrla--ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 Создает объект `CTabCtrl`.  
  
```  
CTabCtrl();
```  
  
##  <a name="a-namedeleteallitemsa--ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 Удаляет все элементы из элемента управления вкладками.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="a-namedeleteitema--ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::DeleteItem  
 Удаляет заданный элемент из элемента управления вкладками.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля значение элемента для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl&#3;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="a-namedeselectalla--ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::DeselectAll  
 Сбрасывает элементы в элементе управления вкладками, очистки, которые были нажаты.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Параметры  
 *fExcludeFocus*  
 Флаг, указывающий область deselection элемент. Если этот параметр имеет значение **FALSE**, все кнопки на вкладке будут сброшены. Если задано значение **TRUE**, а затем сбросит все элементы вкладок, за исключением выбранного в данный момент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32, [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedrawitema--ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида изменения рисование владельцем элемента управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуры, описывающий элемент для рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CTabCtrl` объекта.  
  
 Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` перед этим членом завершении функции.  
  
##  <a name="a-namegetcurfocusa--ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 Возвращает индекс текущей вкладки.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущей вкладки.  
  
##  <a name="a-namegetcursela--ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl::GetCurSel  
 Получает текущую выбранную вкладку в наборе вкладок.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс выбранной вкладки в случае успешного выполнения или – 1, если выбрана вкладка «нет».  
  
##  <a name="a-namegetextendedstylea--ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 Извлекает расширенные стили, используемые в данный момент используется для управления "Вкладка".  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представляет расширенные стили в настоящее время для вкладок элемента управления. Это значение представляет собой сочетание [вкладок расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl::GetImageList  
 Получает список изображений, связанной с вкладок.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на список изображений на вкладке управления, в случае успешного выполнения; в противном случае — **NULL**.  
  
##  <a name="a-namegetitema--ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl::GetItem  
 Извлекает сведения о вкладке в элементе управления вкладками.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс вкладки.  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, можно задать сведения для извлечения. Также используется для получения сведения о вкладке. Эта структура используется с `InsertItem`, `GetItem`, и `SetItem` функции-члены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения; **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 При отправке сообщения **маска** элемент задает атрибуты, возвращаемые. Если **маска** указывает `TCIF_TEXT` значение, **pszText** член должен содержать адрес буфера, принимающего текста элемента и **cchTextMax** элемента необходимо указать размер буфера.  
  
 **Маска**  
 Значение, указывающее, какие `TCITEM` членов получить или задать структуры. Этот элемент может содержать ноль или сочетание следующих значений:  
  
- `TCIF_TEXT`**PszText** член является допустимым.  
  
- `TCIF_IMAGE``iImage` Член является допустимым.  
  
- `TCIF_PARAM`**LParam** член является допустимым.  
  
- `TCIF_RTLREADING`Текст **pszText** при отображении используется порядок чтения справа налево в системах иврит и арабский язык.  
  
- `TCIF_STATE`**DwState** член является допустимым.  
  
 **pszText**  
 Указатель нулем строка, содержащая текст, если структура содержит сведения о вкладке. Если структура получает сведения, этот элемент задает адрес буфера, который получает текст вкладки.  
  
 **cchTextMax**  
 Размер буфера, на который указывает **pszText**. Этот член учитывается, если не получает сведения о структуре.  
  
 `iImage`  
 Индекс в управления "Вкладка" список изображений, или – 1, если изображение отсутствует для вкладки.  
  
 **lParam**  
 Определяемые приложением данные, связанные с вкладкой. При наличии более четырех байт определяемые приложением данные на вкладке приложение должно определить структуру и использовать ее вместо `TCITEM` структуры. Должен быть первым членом структуры прикладного [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)структуры. **TCITEMHEADER** идентична структуре `TCITEM` структуры, но без **lParam** член. Разница между размером структуры и размер **TCITEMHEADER** структуры должно равняться количеству дополнительный байт на вкладке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl&#4;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="a-namegetitemcounta--ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl::GetItemCount  
 Получает число вкладок в элементе управления вкладками.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления вкладками.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namegetitemrecta--ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl::GetItemRect  
 Возвращает ограничивающий прямоугольник для указанной вкладки в элементе управления вкладками.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента вкладки.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающий прямоугольник вкладки. Эти координаты используйте режим сопоставления текущей области просмотра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namegetitemstatea--ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl::GetItemState  
 Получает состояние элемента управления вкладки, идентифицируемый `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента, для которого необходимо получить сведения о состоянии.  
  
 `dwMask`  
 Маска, указывающая, что состояние элемента флаги для возврата. Список значений, в разделе маска членом [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `DWORD` значение, получение сведений о состоянии. Может принимать одно из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Элемент управления вкладки выбран.|  
|**TCIS_HIGHLIGHTED**|Будет выделен элемент управления вкладки и вкладки и текст, отображаются с помощью текущий цвет выделения. При использовании цветом, это будет true интерполяции, не сглаженный цвет.|  
  
### <a name="remarks"></a>Примечания  
 Состояние элемента определяется **dwState** членом `TCITEM` структуры.  
  
##  <a name="a-namegetrowcounta--ctabctrlgetrowcount"></a><a name="getrowcount"></a>CTabCtrl::GetRowCount  
 Возвращает текущее число строк в наборе вкладок.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк из вкладок в элементе управления вкладками.  
  
### <a name="remarks"></a>Примечания  
 Только вкладку элементы управления, имеющие **TCS_MULTILINE** стиль может занимать несколько строк вкладок.  
  
##  <a name="a-namegettooltipsa--ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::GetToolTips  
 Получает дескриптор управления всплывающей подсказки, связанный с элементом управления вкладки.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента управления всплывающей подсказки в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Создает набор вкладок элемента управления всплывающей подсказки, при наличии **TCS_TOOLTIPS** стиль. Можно также назначить управления всплывающей подсказки для элемента управления tab с помощью `SetToolTips` функции-члена.  
  
##  <a name="a-namehighlightitema--ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::HighlightItem  
 Задает состояние выделения элемента вкладки.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `idItem`  
 Отсчитываемый от нуля индекс элемента управления.  
  
 `fHighlight`  
 Значение, указывающее состояние выделения задать. Если это значение равно **TRUE**, выделяются вкладке; Если **FALSE**, набор вкладок в состояние по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует сообщение Win32 [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehittesta--ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::HitTest  
 Определяет, какая вкладка, позиции заданного экрана.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pHitTestInfo`  
 Указатель на [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], что указывает позицию экрана для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает отсчитываемый от нуля индекс вкладки или – 1, если в указанной позиции.  
  
##  <a name="a-nameinsertitema--ctabctrlinsertitem"></a><a name="insertitem"></a>CTabCtrl::InsertItem  
 Вставляет новую вкладку в существующий элемент управления вкладки.  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс новой вкладки.  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структура, которая задает атрибуты вкладки.  
  
 `lpszItem`  
 Адрес нулем строка, содержащая текст вкладки.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для вставки из списка изображений.  
  
 `nMask`  
 Указывает, что `TCITEM` атрибуты для задания структуры. Может содержать ноль или сочетание следующих значений:  
  
- `TCIF_TEXT`**PszText** член является допустимым.  
  
- `TCIF_IMAGE``iImage` Член является допустимым.  
  
- `TCIF_PARAM`**LParam** член является допустимым.  
  
- `TCIF_RTLREADING`Текст **pszText** при отображении используется порядок чтения справа налево в системах иврит и арабский язык.  
  
- `TCIF_STATE`**DwState** член является допустимым.  
  
 `lParam`  
 Определяемые приложением данные, связанные с вкладкой.  
  
 `dwState`  
 Задает значения для состояний элемента. Дополнительные сведения см. в разделе [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *dwStateMask*  
 Указывает, какие состояния должны быть заданы. Дополнительные сведения см. в разделе [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс новую вкладку в случае успешного выполнения; в противном случае — значение 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl&#5;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="a-nameremoveimagea--ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::RemoveImage  
 Удаляет указанный образ из списка изображений набор вкладок.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для удаления.  
  
### <a name="remarks"></a>Примечания  
 Вкладок обновляет индекс изображения каждой вкладки, чтобы каждая вкладка остаются связанными с одного изображения.  
  
##  <a name="a-namesetcurfocusa--ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 Устанавливает фокус на указанной вкладки в элементе управления вкладками.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Указывает индекс вкладки, который получает фокус.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcursela--ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::SetCurSel  
 Выбор вкладки в элементе управления вкладками.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента для выбора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс ранее выбранная вкладка, в случае успешного выполнения, в противном случае — значение 1.  
  
### <a name="remarks"></a>Примечания  
 Набор вкладок не отправляет **TCN_SELCHANGING** или **TCN_SELCHANGE** уведомление при выборе вкладки с помощью этой функции. Эти уведомления отправляются с помощью **WM_NOTIFY**, когда пользователь нажимает кнопку или клавиатурой для изменения табуляции.  
  
##  <a name="a-namesetextendedstylea--ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 Задает расширенные стили для элемента управления tab.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwNewStyle`  
 Значение, указывающее сочетание вкладку управления расширенные стили.  
  
 `dwExMask`  
 Объект `DWORD` значение, указывающее, какие стили в `dwNewStyle` , могут быть затронуты. Расширенные стили в `dwExMask` будет изменен. Все другие стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в `dwNewStyle` снижается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` значение, содержащее предыдущего [вкладок расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl::SetImageList  
 Назначает списка изображений для элемента управления tab.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на список изображений для назначения вкладок элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на список предыдущих изображений или **NULL** Если нет предыдущего списка изображений.  
  
##  <a name="a-namesetitema--ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl::SetItem  
 Задает некоторые или все атрибуты вкладки.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента.  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуру, содержащую новые атрибуты элемента. **Маска** член задает атрибуты для задания. Если **маска** указывает `TCIF_TEXT` значение, **pszText** член является адрес строки с завершающим нулем и **cchTextMax** игнорируется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [GetItem](#getitem).  
  
##  <a name="a-namesetitemextraa--ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 Задает число байтов на вкладке зарезервировано для определяемых приложением данных в элементе управления вкладками.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Количество дополнительных байтов для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetitemsizea--ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl::SetItemSize  
 Задает ширину и высоту элементов набора вкладок.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Новая ширина и высота (в пикселях) элементов набора вкладок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает старую ширину и высоту элементов набора вкладок.  
  
##  <a name="a-namesetitemstatea--ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl::SetItemState  
 Задает состояние элемента управления вкладки, идентифицируемый `nItem`.  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента, для которого устанавливаются сведения о состоянии.  
  
 `dwMask`  
 Маска, указывающая, что состояние элемента флаги для задания. Список значений, в разделе маска членом [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwState`  
 Ссылку на `DWORD` значение, содержащее сведения о состоянии. Может принимать одно из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Элемент управления вкладки выбран.|  
|**TCIS_HIGHLIGHTED**|Будет выделен элемент управления вкладки и вкладки и текст, отображаются с помощью текущий цвет выделения. При использовании цветом, это будет true интерполяции, не сглаженный цвет.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="a-namesetmintabwidtha--ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 Задает минимальную ширину элементов в элементе управления вкладками.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Минимальная ширина для элемента управления. Если этот параметр имеет значение -1, элемент управления будет использовать ширину вкладку по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина предыдущих минимальное вкладку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetpaddinga--ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl::SetPadding  
 Задает объем пространства (заполнения) вокруг каждой вкладке значок и метку в наборе вкладок.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Задает объем пространства (заполнения) вокруг каждой вкладке значок и метку в наборе вкладок.  
  
##  <a name="a-namesettooltipsa--ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::SetToolTips  
 Присваивает набор вкладок элемента управления всплывающей подсказки.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Дескриптор управления всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Можно получить управления всплывающей подсказки, связанный с элементом управления вкладки путем вызова `GetToolTips`.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl-класс](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)

