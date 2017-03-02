---
title: "CHeaderCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeaderCtrl
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class
- Windows common controls [C++], CHeaderCtrl
- header controls, CHeaderCtrl class
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
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
ms.openlocfilehash: ab3cef5d72bad004832cb85ca4b1b3604eb3a18c
ms.lasthandoff: 02/24/2017

---
# <a name="cheaderctrl-class"></a>CHeaderCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "заголовок" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Создает объект `CHeaderCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Удаляет все фильтры для заголовка элемента управления.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|Удаляет фильтр для заголовка элемента управления.|  
|[CHeaderCtrl::Create](#create)|Создает элемент управления заголовка и присоединяет его к `CHeaderCtrl` объекта.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Создает версию прозрачное изображение элемента в элементе управления заголовка.|  
|[CHeaderCtrl::CreateEx](#createex)|Создает элемент управления заголовка с указанным расширенные стили Windows и присоединяет его к `CListCtrl` объекта.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Удаляет элемент из заголовка элемента управления.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления "Заголовок".|  
|[CHeaderCtrl::EditFilter](#editfilter)|Запускает указанный фильтр заголовок элемента управления редактирования.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Получает ширину поля изображения в элементе управления заголовка.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Возвращает идентификатор элемента в текущий элемент управления заголовка, имеющий фокус.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Получает дескриптор список изображений, используемый для рисования элементов заголовка в элементе управления заголовка.|  
|[CHeaderCtrl::GetItem](#getitem)|Получает сведения об элементе в элементе управления заголовка.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Получает число элементов в элементе управления заголовка.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Возвращает ограничивающий прямоугольник сведения для указанной кнопки раскрывающегося списка в элементе управления заголовка.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник для заданного элемента в элементе управления заголовка.|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Возвращает порядок элементов в элементе управления заголовка слева направо.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Возвращает ограничивающий прямоугольник для кнопки переполнения для текущего элемента управления заголовка.|  
|[CHeaderCtrl::HitTest](#hittest)|Определяет, какой элемент заголовка, находится в заданной точке.|  
|[CHeaderCtrl::InsertItem](#insertitem)|Вставляет новый элемент в элемент управления заголовка.|  
|[CHeaderCtrl::Layout](#layout)|Получает размер и положение элемента управления заголовка в пределах заданного прямоугольника.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Получает значение индекса пункта порядка в элементе управления заголовка.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Задает ширину поля растрового изображения в элементе управления заголовка.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Задает интервал времени ожидания между моментом изменения вступят в силу в атрибуты фильтра и учета `HDN_FILTERCHANGE` уведомления.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Устанавливает фокус на элемент указанного заголовка в элементе управления текущего заголовка.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Перетащите разделитель между элементами заголовка для указания ручного изменения и удаления элемента заголовка.|  
|[CHeaderCtrl::SetImageList](#setimagelist)|Назначает списка изображений с элементом управления заголовка.|  
|[CHeaderCtrl::SetItem](#setitem)|Устанавливает атрибуты указанного элемента в элементе управления заголовка.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Задает слева направо порядок элементов в элементе управления заголовка.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления заголовка — окно, которое обычно находится выше набора столбцов текстовых или числовых значений. Он содержит заголовок для каждого столбца, и его можно разделить на части. Пользователь может перетащить разделители, отделяющие частей, чтобы задать ширину каждого столбца. Иллюстрация управления заголовка, в разделе [элементы управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Этот элемент управления (и, следовательно, `CHeaderCtrl` класса) доступны только для программ, выполняемых в среде Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Возможности, добавленные в элементах управления Windows 95 или Internet Explorer 4.0 включает в себя следующее:  
  
-   Заголовок настраиваемого упорядочение элементов.  
  
-   Элемент заголовка и перетащите для изменения порядка элементов заголовка. Используйте `HDS_DRAGDROP` стиля при создании `CHeaderCtrl` объекта.  
  
-   Текст заголовка столбца постоянно доступен для просмотра при изменении размера столбца. Используйте `HDS_FULLDRAG` стиля при создании `CHeaderCtrl` объекта.  
  
-   Заголовок отслеживание, который выделяет элемент заголовка, при наведении указателя мыши на его. Используйте `HDS_HOTTRACK` стиля при создании `CHeaderCtrl` объекта.  
  
-   Поддержка списка изображений. Элементы заголовка могут содержать изображения, хранящиеся в `CImageList` объект или текст.  
  
 Дополнительные сведения об использовании `CHeaderCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CHeaderCtrl с помощью](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namecheaderctrla--cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 Создает объект `CHeaderCtrl`.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#1;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="a-nameclearallfiltersa--cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 Удаляет все фильтры для заголовка элемента управления.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) со значением -1, как описано в столбце [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#2;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="a-nameclearfiltera--cheaderctrlclearfilter"></a><a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 Удаляет фильтр для заголовка элемента управления.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 `nColumn`  
 Столбец значение, указывающее, какой фильтр следует очистить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="a-namecreatea--cheaderctrlcreate"></a><a name="create"></a>CHeaderCtrl::Create  
 Создает элемент управления заголовка и присоединяет его к `CHeaderCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль заголовка элемента управления. Описание стили элемента управления заголовка, в разделе [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение заголовка элемента управления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает заголовок родительского окна элемента управления, обычно `CDialog`. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Создании `CHeaderCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает управления заголовка и присоединяет его к `CHeaderCtrl` объекта.  
  
 Помимо стилей элемента управления заголовка, можно использовать следующие общие стили элемента управления для определения, как элемент управления заголовка размещает и сам изменит свой размер (в разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) Дополнительные сведения):  
  
- `CCS_BOTTOM`Элемент управления располагаться в нижней части клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.  
  
- `CCS_NODIVIDER`Предотвращает подсветки пикселей два из которых выводится в верхней части элемента управления.  
  
- `CCS_NOMOVEY`Элемент управления для изменения размеров и перемещения самого по горизонтали, но не по вертикали, в ответ на `WM_SIZE` сообщение. Если `CCS_NORESIZE` используется стиль, этот стиль не применяется. Элементы управления заголовка имеют этот стиль по умолчанию.  
  
- `CCS_NOPARENTALIGN`Запрещает автоматическое перемещение в верхней или нижней части окна родительского элемента управления. Вместо этого элемент управления сохраняет ее положение в родительском окне, несмотря на изменения размера родительского окна. Если `CCS_TOP` или `CCS_BOTTOM` используется стиль, высота корректируется по умолчанию, но позиции и width остаются без изменений.  
  
- `CCS_NORESIZE`Предотвращает использование по умолчанию ширину и высоту, при задании начального размера или новый размер элемента управления. Вместо этого элемент управления использует ширины и высоты, определенное в запросе для создания или изменения размера.  
  
- `CCS_TOP`Элемент управления располагаться вверху клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.  
  
 Следующие стили окна также можно применить к элементу управления заголовка (см. [стили окна](../../mfc/reference/window-styles.md) подробнее):  
  
- **WS_CHILD** создает дочернего окна. Нельзя использовать с `WS_POPUP` стиль.  
  
- **WS_VISIBLE** создает окно, которое изначально является видимым.  
  
- **WS_DISABLED** создает окно, которое первоначально будет отключено.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления, в которых пользователь может перемещать из одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, определенные с помощью **WS_GROUP** стиля после первого элемента управления относятся к той же группе. Следующий элемент управления с **WS_GROUP** стиль завершает группы стилей и запускает следующей группы (то есть одна группа заканчивается начинается следующий).  
  
- **WS_TABSTOP** указывает один из любого количества элементов, по которым можно перемещаться с помощью клавиши TAB. Пользователь перемещается клавишей TAB к следующему элементу управления, определяемое **WS_TABSTOP** стиль.  
  
 Если вы хотите использовать с элементом управления windows расширенные стили, вызвать [CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="a-namecreateexa--cheaderctrlcreateex"></a><a name="createex"></a>CHeaderCtrl::CreateEx  
 Создает элемент управления (дочернего окна) и связать его с `CHeaderCtrl` объекта.  
  
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
 Стиль заголовка элемента управления. Описание стили элемента управления заголовка, в разделе [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В разделе [создать](#create) список дополнительных стилей.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namecreatedragimagea--cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 Создает версию прозрачное изображение элемента в элементе управления заголовка.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента в элементе управления заголовка. Изображения, назначенного для этого элемента является основой для прозрачное изображение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, если успешно; в противном случае **NULL**. Возвращаемый список содержит только один образ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку заголовок элемента операции перетаскивания.  
  
 `CImageList` Объект, к которому точек возвращаемого указателя является временным и будет удален в следующей обработки времени простоя.  
  
##  <a name="a-namedeleteitema--cheaderctrldeleteitem"></a><a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 Удаляет элемент из заголовка элемента управления.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Задает отсчитываемый от нуля индекс элемента для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#5;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="a-namedrawitema--cheaderctrldrawitem"></a><a name="drawitem"></a>CHeaderCtrl::DrawItem  
 Вызывается инфраструктурой при изменении внешнего вида изменения рисование владельцем заголовка элемента управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуры, описывающий элемент для рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CHeaderCtrl` объекта.  
  
 Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` перед этим членом завершении функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="a-nameeditfiltera--cheaderctrleditfilter"></a><a name="editfilter"></a>CHeaderCtrl::EditFilter  
 Начинает изменение указанного фильтра элемента управления заголовка.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>Параметры  
 `nColumn`  
 Чтобы изменить столбец.  
  
 `bDiscardChanges`  
 Значение, указывающее способ обработки пользователя редактирования изменения, если пользователь находится в процессе редактирования фильтра при [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) отправляется сообщение.  
  
 Укажите `true` для отмены изменений, внесенных пользователем, или `false` для сохранения изменений, внесенных пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#7;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="a-namegetbitmapmargina--cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 Получает ширину поля изображения в элементе управления заголовка.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина поля растрового изображения в точках.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl №&8;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="a-namegetfocuseditema--cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 Возвращает индекс элемента, который имеет фокус в текущий элемент управления заголовка.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента заголовка, имеющий фокус.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. Следующий пример задает и затем подтверждает заголовок последнего столбца как элемент фокус.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="a-namegetimagelista--cheaderctrlgetimagelist"></a><a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 Получает дескриптор список изображений, используемый для рисования элементов заголовка в элементе управления заголовка.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `CImageList` Объект, к которому точек возвращаемого указателя является временным и будет удален в следующей обработки времени простоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl №&9;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="a-namegetitema--cheaderctrlgetitem"></a><a name="getitem"></a>CHeaderCtrl::GetItem  
 Извлекает сведения о заголовка элемента управления.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Задает отсчитываемый от нуля индекс извлекаемого элемента.  
  
 `pHeaderItem`  
 Указатель на [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуру, которая получает новый элемент. Эта структура используется с `InsertItem` и `SetItem` функции-члены. Любые флаги **маска** элемента убедитесь, что значения в соответствующих элементах правильно заполняются при возврате. Если **маска** элемента устанавливается равным нулю, значения в других элементов структуры не имеют смысла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#10;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="a-namegetitemcounta--cheaderctrlgetitemcount"></a><a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 Получает число элементов в элементе управления заголовка.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов управления заголовка в случае успешного выполнения; в противном случае — значение 1.  
  
### <a name="example"></a>Пример  
  В примере показано [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="a-namegetitemdropdownrecta--cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 Возвращает прямоугольник, ограничивающий кнопку раскрывающегося списка для элемента заголовка в элементе управления текущего заголовка.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iItem`|Отсчитываемый от нуля индекс элемента заголовка, стиль которого является `HDF_SPLITBUTTON`. Дополнительные сведения см. в разделе `fmt` членом [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуры.|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры для получения информации о ограничивающего прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если эта функция успешна; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetItemDropDownRect` метод. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. В следующем примере кода Отрисовывает прямоугольник 3D вокруг расположение в первом столбце, зарезервированный для разворачивающейся кнопки заголовка.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="a-namegetitemrecta--cheaderctrlgetitemrect"></a><a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 Возвращает ограничивающий прямоугольник для заданного элемента в элементе управления заголовка.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента управления заголовка.  
  
 `lpRect`  
 Указатель на адрес [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetorderarraya--cheaderctrlgetorderarray"></a><a name="getorderarray"></a>CHeaderCtrl::GetOrderArray  
 Возвращает порядок элементов в элементе управления заголовка слева направо.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Параметры  
 `piArray`  
 Указатель на адрес буфера, который получает значения индекса элементов в элементе управления заголовка, в том порядке, в котором они отображаются слева направо.  
  
 `iCount`  
 Количество элементов управления заголовка. Должно быть неотрицательным числом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Оно предоставляется поддержка упорядочения элементов заголовка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&11;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="a-namegetoverflowrecta--cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 Возвращает ограничивающий прямоугольник для кнопки переполнения текущего заголовка элемента управления.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающего прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если эта функция успешна; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления заголовка содержит больше элементов, чем может одновременно отображаться, элемент управления может отображать кнопку переполнения, который прокручивается к элементам, которые не видны. Элемент управления Заголовок должен иметь `HDS_OVERFLOW` и `HDF_SPLITBUTTON` стили для отображения кнопки переполнения. Ограничивающий прямоугольник заключает кнопку переполнения и существует только в том случае, если отображается кнопка переполнения. Дополнительные сведения см. в разделе [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Этот метод отправляет [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetOverflowRect` метод. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. Если некоторые столбцы не видны, управления заголовка Рисует кнопку переполнения. В следующем примере кода рисует 3D прямоугольник вокруг расположение кнопки переполнения.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="a-namehittesta--cheaderctrlhittest"></a><a name="hittest"></a>CHeaderCtrl::HitTest  
 Определяет, какой элемент заголовка, находится в заданной точке.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in, out] `phdhti`|Указатель на [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) структура, которая указывает точку для тестирования и получать результаты теста.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента заголовка, если они имеются в заданной позиции; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `HitTest` метод. В предыдущем разделе этого примера кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. В этом примере определяется индекс столбца, если он является видимым и -1, если столбец не отображается.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="a-nameinsertitema--cheaderctrlinsertitem"></a><a name="insertitem"></a>CHeaderCtrl::InsertItem  
 Вставляет новый элемент в элемент управления "Заголовок" по указанному индексу.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Отсчитываемый от нуля индекс вставляемого элемента. Если значение равно нулю, элемент вставляется в начало элемента управления заголовка. Если значение превышает максимальное значение, элемент вставляется в конце заголовка элемента управления.  
  
 *phdi*  
 Указатель на [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуру, содержащую сведения о вставляемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс нового элемента в случае успешного выполнения; в противном случае — значение 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#12;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="a-namelayouta--cheaderctrllayout"></a><a name="layout"></a>CHeaderCtrl::Layout  
 Получает размер и положение элемента управления заголовка в пределах заданного прямоугольника.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Параметры  
 *pHeaderLayout*  
 Указатель на [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) структура, которая содержит сведения, используемые для задания размера и положения элемента управления заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для определения соответствующих измерений для нового элемента управления заголовка, который должен занимать данный прямоугольник.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#13;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="a-nameordertoindexa--cheaderctrlordertoindex"></a><a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 Получает значение индекса пункта порядка в элементе управления заголовка.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nOrder*  
 Отсчитываемый от нуля заказ, элемент отображается в элементе управления заголовка слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, на основании его заказ в элементе управления заголовка. Индекс отсчитывается от слева направо, начиная с 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение макроса Win32 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Оно предоставляется поддержка упорядочения элементов заголовка.  
  
##  <a name="a-namesetbitmapmargina--cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 Задает ширину поля растрового изображения в элементе управления заголовка.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Ширина задана в пикселах, поля, окружающие точечного рисунка в существующий элемент управления заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина поля растрового изображения в точках.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#14;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="a-namesetfilterchangetimeouta--cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 Задает интервал времени ожидания между моментом изменения вступят в силу в атрибуты фильтра и учета [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) уведомления.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>Параметры  
 *dwTimeOut*  
 Значение времени ожидания в миллисекундах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента управления фильтра изменяется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#15;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="a-namesetfocuseditema--cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 Устанавливает фокус на элемент указанного заголовка в элементе управления текущего заголовка.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iItem`|Отсчитываемый от нуля индекс элемента заголовка.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_headerCtrl`, который используется для доступа к текущим элементом управления заголовка. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 №&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетащить разделитель столбцов, чтобы столбец не отображается. Следующий пример задает и затем подтверждает заголовок последнего столбца как элемент фокус.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="a-namesethotdividera--cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 Перетащите разделитель между элементами заголовка для указания ручного изменения и удаления элемента заголовка.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Положение указателя. Заголовок элемента управления выделяется соответствующий разделитель, исходя из позиции курсора.  
  
 `nIndex`  
 Индекс выделенного разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выделенного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку заголовок элемента операции перетаскивания.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl №&16;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="a-namesetimagelista--cheaderctrlsetimagelist"></a><a name="setimagelist"></a>CHeaderCtrl::SetImageList  
 Назначает списка изображений с элементом управления заголовка.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий список изображений для назначения управления заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, ранее назначенные элементу управления заголовка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `CImageList` Объект, к которому точек возвращаемого указателя является временным и будет удален в следующей обработки времени простоя.  
  
### <a name="example"></a>Пример  
  В примере показано [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="a-namesetitema--cheaderctrlsetitem"></a><a name="setitem"></a>CHeaderCtrl::SetItem  
 Устанавливает атрибуты указанного элемента в элементе управления заголовка.  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Отсчитываемый от нуля индекс элемента для обработки.  
  
 `pHeaderItem`  
 Указатель на [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуру, содержащую сведения о новый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CHeaderCtrl::GetItem](#getitem).  
  
##  <a name="a-namesetorderarraya--cheaderctrlsetorderarray"></a><a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 Задает слева направо порядок элементов в элементе управления заголовка.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Параметры  
 `iCount`  
 Количество элементов управления заголовка.  
  
 `piArray`  
 Указатель на адрес буфера, который получает значения индекса элементов в элементе управления заголовка, в том порядке, в котором они отображаются слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение макроса Win32 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Оно предоставляется поддержка упорядочения элементов заголовка.  
  
### <a name="example"></a>Пример  
  В примере показано [CHeaderCtrl::GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CTabCtrl-класс](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)   
 [CImageList-класс](../../mfc/reference/cimagelist-class.md)

