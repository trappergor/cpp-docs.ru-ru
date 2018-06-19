---
title: CTabCtrl-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e46a7d5720be765f2523ebde5d40655fb47b057
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378560"
---
# <a name="ctabctrl-class"></a>CTabCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "вкладка" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|Создает объект `CTabCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|Вычисляет отображаемую область элемента управления tab указанным прямоугольником окна или вычисляет окна прямоугольник, который будет соответствовать данной отображаемой области.|  
|[CTabCtrl::Create](#create)|Создает набор вкладок и прикрепляет его к экземпляру `CTabCtrl` объекта.|  
|[CTabCtrl::CreateEx](#createex)|Создает элемент управления вкладки с указанным расширенные стили Windows и прикрепляет его к экземпляру `CTabCtrl` объекта.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Удаляет все элементы из элемента управления tab.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Удаляет элемент из элемента управления tab.|  
|[CTabCtrl::DeselectAll](#deselectall)|Сбрасывает элементов в элементе управления вкладками, сбросить были нажаты.|  
|[CTabCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления "Вкладка".|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Извлекает вкладку с текущего местоположения элемента управления вкладками.|  
|[CTabCtrl::GetCurSel](#getcursel)|Определяет выбранной вкладки в элементе управления вкладками.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Извлекает расширенные стили, которые в настоящее время используются для управления "Вкладка".|  
|[CTabCtrl::GetImageList](#getimagelist)|Извлекает список изображений, связанных с элементом управления tab.|  
|[CTabCtrl::GetItem](#getitem)|Извлекает сведения о вкладке в элементе управления вкладками.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Возвращает число вкладок в наборе вкладок.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник для вкладки в элементе управления вкладками.|  
|[CTabCtrl::GetItemState](#getitemstate)|Получает состояние элемента управления для указанной вкладки.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Получает текущее число рядов вкладок в наборе вкладок.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Извлекает дескриптор управления всплывающей подсказки, связанный с элементом управления tab.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Задает состояние выделения элемента вкладки.|  
|[CTabCtrl::HitTest](#hittest)|Определяет, какие вкладки, с указанными экранными позиции.|  
|[CTabCtrl::InsertItem](#insertitem)|Вставляет новую вкладку в элементе управления вкладками.|  
|[CTabCtrl::RemoveImage](#removeimage)|Удаляет изображение из списка изображений элемента управления tab.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Устанавливает фокус на указанной вкладки в элементе управления вкладками.|  
|[CTabCtrl::SetCurSel](#setcursel)|Выбор вкладки в элементе управления вкладками.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Задает расширенные стили для элемента управления tab.|  
|[CTabCtrl::SetImageList](#setimagelist)|Назначает списка изображений элемента управления tab.|  
|[CTabCtrl::SetItem](#setitem)|Задает некоторые или все атрибуты "Вкладка".|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Задает число байтов для табуляции, зарезервированных для определяемых приложением данных в элементе управления вкладками.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Задает ширину и высоту элемента.|  
|[CTabCtrl::SetItemState](#setitemstate)|Задает состояние элемента управления указанной вкладки.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Задает минимальную ширину элементов в элементе управления вкладками.|  
|[CTabCtrl::SetPadding](#setpadding)|Задает объем пространства (заполнения) вокруг значка каждой вкладки и подписи в элементе управления вкладками.|  
|[CTabCtrl::SetToolTips](#settooltips)|Назначает всплывающая подсказка элемента управления tab.|  
  
## <a name="remarks"></a>Примечания  
 «Вкладка» является аналогом разделителей в записной книжке или меток в картотеке. С помощью элемента управления "Вкладка" приложение может определить несколько страниц для одной области окна или диалогового окна. Каждая страница состоит из набора сведений или группы элементов управления, которые приложение отображает, когда пользователь выбирает соответствующую вкладку. Специальный тип элемента управления "Вкладка" отображает вкладки, которые выглядят как кнопки. Нажатие кнопки следует немедленно выполнить команду вместо отображения страницы.  
  
 Этот элемент управления (и, следовательно, `CTabCtrl` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Дополнительные сведения об использовании `CTabCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect  
 Вычисляет отображаемую область элемента управления tab указанным прямоугольником окна или вычисляет окна прямоугольник, который будет соответствовать данной отображаемой области.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 `bLarger`  
 Указывает операцию для выполнения. Если этот параметр имеет **TRUE**, `lpRect` указывает отображаемый прямоугольник и получает соответствующие прямоугольника окна. Если этот параметр имеет **FALSE**, `lpRect` указывает прямоугольник окна и получает соответствующие отображаемый прямоугольник.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая указывает заданного прямоугольника и получает расчетный прямоугольник.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CTabCtrl::Create  
 Создает набор вкладок и прикрепляет его к экземпляру `CTabCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль элемента управления tab. Примените любое сочетание [вкладке Стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb760549), описанных в Windows SDK. В разделе **примечания** список стилей окна, которые также можно применить к элементу управления.  
  
 `rect`  
 Задает размер и положение элемента управления tab. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает родительскому окну элемента управления tab, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления tab.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** при инициализации объекта выполнен успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Создании `CTabCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает вкладок элемента управления и прикрепляет его к `CTabCtrl` объекта.  
  
 Помимо стили элемента управления tab можно применить следующие стили окна для элемента управления tab.  
  
- **WS_CHILD** создает дочернее окно, представляющий набор вкладок. Нельзя использовать с `WS_POPUP` стиля.  
  
- **WS_VISIBLE** создает элемент управления вкладки, изначально является видимым.  
  
- **WS_DISABLED** создает окно, которое изначально отключены.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления, в которых пользователь может перемещать из одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, имеющий **WS_GROUP** стиль после первого элемента управления принадлежать одной группе. Следующий элемент управления с **WS_GROUP** стиль завершает стиль группы и запуске следующей группы (то есть одна группа заканчивается до начала следующего).  
  
- **WS_TABSTOP** указывает один из любое число элементов управления с помощью которых можно перемещаться с помощью клавиши TAB. Пользователь перемещается клавишей TAB к следующему элементу управления, определяемое **WS_TABSTOP** стиля.  
  
 Чтобы создать набор вкладок с расширенные стили окна, вызовите [CTabCtrl::CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CTabCtrl::CreateEx  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `dwStyle`  
 Задает стиль элемента управления tab. Примените любое сочетание [вкладке Стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb760549), описанных в Windows SDK. В разделе **примечания** в [создать](#create) список стилей окна, которые также можно применить к элементу управления.  
  
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
  
 `CreateEx` Создает элемент управления с расширенные стили Windows, указанные для `dwExStyle`. Расширенные стили, определенные для элемента управления с помощью набора [SetExtendedStyle](#setextendedstyle). Например, использовать `CreateEx` задание стилей, таких как **WS_EX_CONTEXTHELP**, но использовать `SetExtendedStyle` задание стилей, таких как **TCS_EX_FLATSEPARATORS**. Дополнительные сведения см. в разделе стили, описанные в [вкладку управления расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546) в Windows SDK.  
  
##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl  
 Создает объект `CTabCtrl`.  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems  
 Удаляет все элементы из элемента управления tab.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem  
 Удаляет заданный элемент из элемента управления tab.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля значение элемента для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>  CTabCtrl::DeselectAll  
 Сбрасывает элементов в элементе управления вкладками, сбросить были нажаты.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Параметры  
 *fExcludeFocus*  
 Флаг, указывающий область deselection элемента. Если этот параметр имеет значение **FALSE**, приведет к сбросу всех кнопок. Если задано значение **TRUE**, то будут сброшены все элементы вкладки, за исключением выбранного в данный момент.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579), как описано в Windows SDK.  
  
##  <a name="drawitem"></a>  CTabCtrl::DrawItem  
 Вызывается платформой при изменении внешнего вида изменения рисуемый владельцем элемент управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуры, описывающий элемент для рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CTabCtrl` объекта.  
  
 Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` до этого элемента, функция завершается.  
  
##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus  
 Возвращает индекс текущей вкладки.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс текущей вкладки.  
  
##  <a name="getcursel"></a>  CTabCtrl::GetCurSel  
 Извлекает выбранной вкладки в элементе управления вкладками.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс выбранной вкладки в случае успешного выполнения или - 1, если выбрана вкладка «нет».  
  
##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle  
 Извлекает расширенные стили, которые в настоящее время используются для управления "Вкладка".  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представляет расширенные стили, которые в настоящее время для управления "Вкладка". Это значение представляет собой сочетание [вкладок расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546), как описано в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585), как описано в Windows SDK.  
  
##  <a name="getimagelist"></a>  CTabCtrl::GetImageList  
 Извлекает список изображений, связанной с элементом управления tab.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на список изображений на вкладке управления, в случае успешного выполнения; в противном случае **NULL**.  
  
##  <a name="getitem"></a>  CTabCtrl::GetItem  
 Извлекает сведения о вкладке в элементе управления вкладками.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс вкладки.  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, позволяет указать, какую информацию необходимо вернуть. Также используется для получения сведения о вкладке. Эта структура используется с `InsertItem`, `GetItem`, и `SetItem` функции-члены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения; **FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 При отправке сообщения **маска** задает атрибуты, возвращаемые. Если **маска** задает `TCIF_TEXT` значение **pszText** член должен содержать адрес буфера, принимающего текста элемента и **cchTextMax** элемент должен указывать размер буфера.  
  
 **Маска**  
 Значение, указывающее, какие `TCITEM` члены для получения или задания структур. Этот член может содержать ноль или сочетанием следующих значений:  
  
- `TCIF_TEXT` **PszText** член является допустимым.  
  
- `TCIF_IMAGE` `iImage` Член является допустимым.  
  
- `TCIF_PARAM` **LParam** член является допустимым.  
  
- `TCIF_RTLREADING` Текст **pszText** при отображении используется порядок чтения справа налево в системах иврит и арабский язык.  
  
- `TCIF_STATE` **DwState** член является допустимым.  
  
 **pszText**  
 Указатель на завершающуюся значением null строка, содержащая текст вкладки, если структура содержит сведения о вкладке. Если структура получает сведения, этот элемент указывает адрес буфера, принимающего текст вкладки.  
  
 **cchTextMax**  
 Размер буфера, на который указывает **pszText**. Этот член учитывается, если не получает сведения о структуре.  
  
 `iImage`  
 Индекс в управления "Вкладка" список изображений, или значение-1, если изображение отсутствует для вкладки.  
  
 **lParam**  
 Определяемые приложением данные, связанные с вкладкой. При наличии более четырех байт определяемые приложением данные на вкладке, приложение должно определить структуру и использовать его вместо `TCITEM` структуры. Должен быть первым элементом структуры, определяемые приложением [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)структуры. **TCITEMHEADER** идентична структуру `TCITEM` структуры, но без **lParam** член. Разница между размером структуры и размер **TCITEMHEADER** структуры должна равняться количеству дополнительные байты на вкладку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount  
 Возвращает число вкладок в наборе вкладок.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в элементе управления вкладками.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect  
 Возвращает ограничивающий прямоугольник для указанной вкладки в элементе управления вкладками.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента вкладки.  
  
 `lpRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает ограничивающий прямоугольник вкладки. Эти координаты использовать режим сопоставления текущего окна просмотра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemstate"></a>  CTabCtrl::GetItemState  
 Получает состояние элемента управления tab, определенные `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента, для которого требуется извлечь сведения о состоянии.  
  
 `dwMask`  
 Маска, указывающая, что элемент имеет состояние флаги для возврата. Список значений см. в разделе маска членом [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, как описано в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `DWORD` значение получение сведений о состоянии. Может принимать одно из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Выбран элемент управления вкладки.|  
|**TCIS_HIGHLIGHTED**|Будет выделен элемент управления вкладки и вкладку и текст, отображаются с помощью текущий цвет выделения. При использовании цветом, это будет true интерполяции, не сглаженный цвет.|  
  
### <a name="remarks"></a>Примечания  
 Состояние элемента определяется **dwState** членом `TCITEM` структуры.  
  
##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount  
 Возвращает текущее количество строк в элементе управления вкладками.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество рядов вкладок в наборе вкладок.  
  
### <a name="remarks"></a>Примечания  
 Только вкладку элементов управления, имеющих **TCS_MULTILINE** стилей может иметь несколько рядов вкладок.  
  
##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips  
 Извлекает дескриптор управления всплывающей подсказки, связанный с элементом управления tab.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор элемента управления всплывающей подсказки в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Набор вкладок создает элемента управления всплывающей подсказки, если у него есть **TCS_TOOLTIPS** стиля. Можно также назначить всплывающая подсказка вкладки с помощью `SetToolTips` функции-члена.  
  
##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem  
 Задает состояние выделения элемента вкладки.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `idItem`  
 Отсчитываемый от нуля индекс элемента управления tab.  
  
 `fHighlight`  
 Значение, указывающее состояние выделения. Если это значение равно **TRUE**, выделяются вкладке; Если **FALSE**, вкладке устанавливается в состояние по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует сообщение Win32 [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602), как описано в Windows SDK.  
  
##  <a name="hittest"></a>  CTabCtrl::HitTest  
 Определяет, какие вкладки, с указанными экранными позиции.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pHitTestInfo`  
 Указатель на [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) структуры, как описано в Windows SDK, указывающий позицию экрана для тестирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает отсчитываемый от нуля индекс вкладки или - 1, если в указанной позиции.  
  
##  <a name="insertitem"></a>  CTabCtrl::InsertItem  
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
 Отсчитываемый от нуля индекс вкладки «новые».  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структура, которая задает атрибуты вкладки.  
  
 `lpszItem`  
 Адрес нулем строка, содержащая текст вкладки.  
  
 `nImage`  
 Отсчитываемый от нуля индекс образа для вставки списка изображений.  
  
 `nMask`  
 Определяет, какая `TCITEM` структуры атрибуты для установки. Может содержать ноль или сочетанием следующих значений:  
  
- `TCIF_TEXT` **PszText** член является допустимым.  
  
- `TCIF_IMAGE` `iImage` Член является допустимым.  
  
- `TCIF_PARAM` **LParam** член является допустимым.  
  
- `TCIF_RTLREADING` Текст **pszText** при отображении используется порядок чтения справа налево в системах иврит и арабский язык.  
  
- `TCIF_STATE` **DwState** член является допустимым.  
  
 `lParam`  
 Определяемые приложением данные, связанные с вкладкой.  
  
 `dwState`  
 Задает значения для состояния элемента. Дополнительные сведения см. в разделе [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) в Windows SDK.  
  
 *dwStateMask*  
 Указывает, какие состояния должны быть заданы. Дополнительные сведения см. в разделе [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс вкладки «новые» в случае успешного выполнения; в противном случае - 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>  CTabCtrl::RemoveImage  
 Удаляет указанный образ из списка изображений элемента управления tab.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для удаления.  
  
### <a name="remarks"></a>Примечания  
 Набор вкладок обновляет индекс образа для каждой вкладки, чтобы каждая вкладка остается связанным с одного изображения.  
  
##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus  
 Устанавливает фокус на указанной вкладки в элементе управления вкладками.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Задает индекс вкладки, который получает фокус.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610), как описано в Windows SDK.  
  
##  <a name="setcursel"></a>  CTabCtrl::SetCurSel  
 Выбор вкладки в элементе управления вкладками.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента для выбора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс ранее выбранной вкладки в случае успеха, в противном случае - 1.  
  
### <a name="remarks"></a>Примечания  
 Набор вкладок не отправляет **TCN_SELCHANGING** или **TCN_SELCHANGE** сообщение уведомления, когда выбрана вкладка с использованием этой функции. Эти уведомления отправляются с помощью **WM_NOTIFY**при щелчке мышью или клавиатурой для изменения табуляции.  
  
##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle  
 Задает расширенные стили для элемента управления tab.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwNewStyle`  
 Значение, указывающее сочетание вкладку управления расширенные стили.  
  
 `dwExMask`  
 Объект `DWORD` значение, указывающее, какие стили в `dwNewStyle` , могут быть затронуты. Расширенные стили в `dwExMask` будет изменен. Все стили будут сохранены как есть. Если этот параметр равен нулю, то все стили в `dwNewStyle` будут затронуты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` значение с предыдущим [вкладок расширенные стили](http://msdn.microsoft.com/library/windows/desktop/bb760546), как описано в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627), как описано в Windows SDK.  
  
##  <a name="setimagelist"></a>  CTabCtrl::SetImageList  
 Назначает списка изображений элемента управления tab.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на список изображений для назначения вкладок элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущем список изображений или **NULL** Если нет предыдущего списка изображений.  
  
##  <a name="setitem"></a>  CTabCtrl::SetItem  
 Задает некоторые или все атрибуты "Вкладка".  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс элемента.  
  
 `pTabCtrlItem`  
 Указатель на [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуру, содержащую новые атрибуты элемента. **Маска** элемент указывает, какие атрибуты следует задать. Если **маска** задает `TCIF_TEXT` значение, **pszText** член является адрес строки с завершающим нулем и **cchTextMax** элемент обрабатывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [GetItem](#getitem).  
  
##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra  
 Задает число байтов для табуляции, зарезервированных для определяемых приложением данных в элементе управления вкладками.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Количество дополнительных байтов для задания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633), как описано в Windows SDK.  
  
##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize  
 Задает ширину и высоту элементов набора вкладок.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Новая ширина и высота (в пикселях) элементов набора вкладок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает старую ширину и высоту элементов набора вкладок.  
  
##  <a name="setitemstate"></a>  CTabCtrl::SetItemState  
 Задает состояние элемента управления tab, определенные `nItem`.  
  
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
 Маска, указывающая, что состояние элемента флаги для задания. Список значений см. в разделе маска членом [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) структуры, как описано в Windows SDK.  
  
 `dwState`  
 Ссылку на `DWORD` значение, содержащее сведения о состоянии. Может принимать одно из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Выбран элемент управления вкладки.|  
|**TCIS_HIGHLIGHTED**|Будет выделен элемент управления вкладки и вкладку и текст, отображаются с помощью текущий цвет выделения. При использовании цветом, это будет true интерполяции, не сглаженный цвет.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth  
 Задает минимальную ширину элементов в элементе управления вкладками.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Минимальная ширина должен быть задан для элемента управления tab. Если этот параметр имеет значение -1, элемент управления будет использовать ширину вкладку по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина предыдущих минимальное вкладку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция-член реализует поведение сообщения Win32 [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637), как описано в Windows SDK.  
  
##  <a name="setpadding"></a>  CTabCtrl::SetPadding  
 Задает объем пространства (заполнения) вокруг значка каждой вкладки и подписи в элементе управления вкладками.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Задает объем пространства (заполнения) вокруг значка каждой вкладки и подписи в элементе управления вкладками.  
  
##  <a name="settooltips"></a>  CTabCtrl::SetToolTips  
 Назначает всплывающая подсказка элемента управления tab.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndTip`  
 Дескриптор управления всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Вы можете получить управления всплывающей подсказки, связанный с элементом управления tab путем вызова `GetToolTips`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl-класс](../../mfc/reference/cheaderctrl-class.md)   
 [Класс CListCtrl](../../mfc/reference/clistctrl-class.md)
