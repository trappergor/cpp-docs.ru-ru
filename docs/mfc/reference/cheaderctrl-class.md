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
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: faa23ea6f28c2643c9bee090ea150e37d0add97c
ms.lasthandoff: 04/01/2017

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
|[CHeaderCtrl::ClearFilter](#clearfilter)|Очистка фильтра для заголовка элемента управления.|  
|[CHeaderCtrl::Create](#create)|Создает элемент управления заголовком и прикрепляет его к `CHeaderCtrl` объекта.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Создает прозрачный версию изображения элемента в элемент управления заголовком.|  
|[CHeaderCtrl::CreateEx](#createex)|Создает элемент управления заголовок с указанным расширенные стили Windows и прикрепляет его к `CListCtrl` объекта.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Удаляет элемент из заголовка элемента управления.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Рисует указанный элемент управления заголовка.|  
|[CHeaderCtrl::EditFilter](#editfilter)|Запускает указанный фильтр для заголовка элемента управления редактирования.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Получает ширину поля растрового изображения в элемент управления заголовком.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Возвращает идентификатор элемента в элементе управления текущего заголовка, который находится в фокусе.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Извлекает маркер из списка изображений, используемый для рисования элементов заголовка в элементе управления заголовка.|  
|[CHeaderCtrl::GetItem](#getitem)|Извлекает сведения об элементе в элемент управления заголовком.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Получает число элементов в элемент управления заголовком.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Возвращает ограничивающий прямоугольник сведения для указанной кнопки раскрывающегося списка в элементе управления заголовка.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Возвращает ограничивающий прямоугольник для данного элемента в элемент управления заголовком.|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Получает порядок элементов в элементе управления заголовка справа налево.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Возвращает ограничивающий прямоугольник кнопки переполнения для текущего заголовка элемента управления.|  
|[CHeaderCtrl::HitTest](#hittest)|Определяет, какой элемент заголовка, расположенный в указанной точке.|  
|[CHeaderCtrl::InsertItem](#insertitem)|Вставляет элемент в элемент управления заголовком.|  
|[CHeaderCtrl::Layout](#layout)|Извлекает размер и положение элемента управления "Заголовок" в пределах заданного прямоугольника.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Получает значение индекса для элемента в зависимости от порядка в элементе управления заголовка.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Задает ширину поля растрового изображения в элемент управления заголовком.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Задает интервал времени ожидания в период между изменение происходит в атрибуты фильтра и учет `HDN_FILTERCHANGE` уведомления.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Устанавливает фокус на указанный заголовочный элемент в текущий элемент управления заголовка.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Перетащите разделитель между элементов заголовка для указания ручного изменения и удаления элемента заголовка.|  
|[CHeaderCtrl::SetImageList](#setimagelist)|Назначает заголовок элемента управления списка изображений.|  
|[CHeaderCtrl::SetItem](#setitem)|Устанавливает атрибуты указанного элемента в элемент управления заголовком.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Задает слева направо порядок элементов в элемент управления заголовком.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления заголовка — окно, которое обычно находится выше набор столбцов текстовых или числовых значений. Она содержит заголовок для каждого столбца, и его можно разделить на части. Пользователь может перетаскивать разделитель, разделяющий элементы, чтобы задать ширину каждого столбца. Иллюстрация управления заголовка, в разделе [элементы управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Этот элемент управления (и, следовательно, `CHeaderCtrl` класс) доступен только для программ, выполняемых в среде Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Возможности, добавленные в стандартные элементы управления Windows 95/Internet Explorer 4.0 включает следующее:  
  
-   Заголовок пользовательского упорядочение элементов.  
  
-   Элемент заголовка путем перетаскивания, для переупорядочения элементов заголовка. Используйте `HDS_DRAGDROP` стиля при создании `CHeaderCtrl` объекта.  
  
-   Текст заголовка столбца постоянно для просмотра при изменении размера столбца. Используйте `HDS_FULLDRAG` стиля при создании `CHeaderCtrl` объекта.  
  
-   Заголовок отслеживание, который выделяет элемент заголовка при наведении указателя мыши на его. Используйте `HDS_HOTTRACK` стиля при создании `CHeaderCtrl` объекта.  
  
-   Поддержка списков изображений. Заголовок элементы могут содержать изображения, хранимые в `CImageList` объект или текст.  
  
 Дополнительные сведения об использовании `CHeaderCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 Создает объект `CHeaderCtrl`.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 Удаляет все фильтры для заголовка элемента управления.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) со значением -1, как описано в столбце [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 Очистка фильтра для заголовка элемента управления.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Параметры  
 `nColumn`  
 Значение столбца, позволяющее определить, какой фильтр следует удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>CHeaderCtrl::Create  
 Создает элемент управления заголовком и прикрепляет его к `CHeaderCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль заголовка элемента управления. Описание стили заголовка элемента управления см. [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Задает размер и положение заголовка элемента управления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указывает заголовок родительского окна элемента управления, обычно `CDialog`. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор заголовка элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Создании `CHeaderCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает заголовок элемента управления и прикрепляет его к `CHeaderCtrl` объекта.  
  
 Помимо стили элемента управления заголовка, можно использовать следующие общие стили элемента управления для определения, как элемент управления заголовка размещает и изменять свои размеры (в разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) подробнее):  
  
- `CCS_BOTTOM`Заставляет элемент управления для размещения себя в нижней части клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.  
  
- `CCS_NODIVIDER`Запрещает выделение двух точек отрисовывается в верхней части элемента управления.  
  
- `CCS_NOMOVEY`Заставляет элемент управления для изменения размера и перемещения самого по горизонтали, но не по вертикали, в ответ на `WM_SIZE` сообщение. Если `CCS_NORESIZE` используется стиль, этот стиль не применяется. Элементы управления заголовка имеют этот стиль по умолчанию.  
  
- `CCS_NOPARENTALIGN`Запрещает автоматическое перемещение в верхней или нижней части родительского окна элемента управления. Вместо этого элемент управления сохраняет его положение в родительском окне независимо от изменений размера родительского окна. Если `CCS_TOP` или `CCS_BOTTOM` используется стиль, высота корректируется по умолчанию, но также положение и ширины остаются неизменными.  
  
- `CCS_NORESIZE`Запрещает использовать стандартную ширину и высоту, при задании его исходный размер или новый размер элемента управления. Вместо этого элемент управления использует ширины и высоты, указанный в запросе для создания или изменения размера.  
  
- `CCS_TOP`Заставляет элемент управления для размещения себя в верхней части клиентской области родительского окна и задает ширину должен совпадать с родительским ширина окна.  
  
 Также можно применить следующие стили окна заголовка в элемент управления (см. [стили окна](../../mfc/reference/window-styles.md) подробнее):  
  
- **WS_CHILD** создает дочернее окно. Нельзя использовать с `WS_POPUP` стиля.  
  
- **WS_VISIBLE** создает окно, которое изначально является видимым.  
  
- **WS_DISABLED** создает окно, которое изначально отключены.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления, в которых пользователь может перемещать из одного элемента управления к другому с помощью клавиш со стрелками. Все элементы управления, имеющий **WS_GROUP** стиль после первого элемента управления принадлежать одной группе. Следующий элемент управления с **WS_GROUP** стиль завершает стиль группы и запуске следующей группы (то есть одна группа заканчивается до начала следующего).  
  
- **WS_TABSTOP** указывает один из любое число элементов управления с помощью которых можно перемещаться с помощью клавиши TAB. Пользователь перемещается клавишей TAB к следующему элементу управления, определяемое **WS_TABSTOP** стиля.  
  
 Если вы хотите использовать с элементом управления windows расширенных стилей, вызовите [CreateEx](#createex) вместо **создать**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="createex"></a>CHeaderCtrl::CreateEx  
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
 Стиль заголовка элемента управления. Описание стили заголовка элемента управления см. [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В разделе [создать](#create) список дополнительные стили.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо **создать** для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 Создает прозрачный версию изображения элемента в элемент управления заголовком.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента в элементе управления заголовка. Изображения, назначенный данному элементу является основой для прозрачное изображение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, если успешно; в противном случае **NULL**. Возвращаемый список содержит только один образ.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку перетащите заголовок элемента.  
  
 `CImageList` Объекта, к которому точек возвращенный указатель является временным и будет удалена в следующей обработки времени простоя.  
  
##  <a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
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
 [!code-cpp[NVC_MFC_CHeaderCtrl #5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>CHeaderCtrl::DrawItem  
 Вызывается платформой при изменении внешнего вида изменения рисуемый владельцем заголовка элемента управления.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуры, описывающий элемент для рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено.  
  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CHeaderCtrl` объекта.  
  
 Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` до этого элемента, функция завершается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>CHeaderCtrl::EditFilter  
 Начинает изменить указанный фильтр для заголовка элемента управления.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>Параметры  
 `nColumn`  
 Чтобы изменить столбец.  
  
 `bDiscardChanges`  
 Если пользователь находится в процессе редактирования фильтра значение, указывающее способ обработки пользователь Правка изменения при [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) отправляется сообщение.  
  
 Укажите `true` для отмены изменений, внесенных пользователем, или `false` для принятия изменений, внесенных пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 Получает ширину поля растрового изображения в элемент управления заголовком.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина поля растрового изображения в точках.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 Возвращает индекс элемента, который имеет фокус в текущий элемент управления заголовка.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента заголовка, который находится в фокусе.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущего заголовка элемента управления. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетаскивать разделитель столбцов, чтобы столбец не отображается. Следующий пример задает и затем подтверждает заголовок последнего столбца как элемент фокус ввода.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 Извлекает маркер из списка изображений, используемый для рисования элементов заголовка в элементе управления заголовка.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `CImageList` Объекта, к которому точек возвращенный указатель является временным и будет удалена в следующей обработки времени простоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>CHeaderCtrl::GetItem  
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
 Указатель на [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуру, которая получает новый элемент. Эта структура используется с `InsertItem` и `SetItem` функции-члены. Все флаги установлены **маска** элемента убедитесь, что значения в соответствующих элементах правильно заполняются при возврате. Если **маска** элемента устанавливается равным нулю, значения в других элементах структуры не имеют смысла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 Получает число элементов в элемент управления заголовком.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов управления заголовка в случае успешного выполнения; в противном случае - 1.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 Возвращает прямоугольник, ограничивающий кнопку раскрывающегося списка для элемента заголовка в элементе управления текущего заголовка.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iItem`|Отсчитываемый от нуля индекс заголовочный элемент, стиль `HDF_SPLITBUTTON`. Дополнительные сведения см. в разделе `fmt` членом [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуры.|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры получать сведения ограничивающего прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если эта функция прошла успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущего заголовка элемента управления. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetItemDropDownRect` метод. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. В следующем примере кода рисует прямоугольник 3D вокруг расположение в первом столбце, зарезервированный для разворачивающейся кнопки заголовка.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 Возвращает ограничивающий прямоугольник для данного элемента в элемент управления заголовком.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс заголовка элемента управления.  
  
 `lpRect`  
 Указатель на адрес [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающего прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод реализует поведение сообщения Win32 [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getorderarray"></a>CHeaderCtrl::GetOrderArray  
 Получает порядок элементов в элементе управления заголовка справа налево.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Параметры  
 `piArray`  
 Указатель на адрес буфера, который получает значения индекса элементов в элементе управления "Заголовок", в том порядке, в котором они появляются в направлении слева направо.  
  
 `iCount`  
 Количество элементов заголовка элемента управления. Должно быть неотрицательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку упорядочение элементов заголовка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl № 11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 Возвращает ограничивающий прямоугольник кнопки переполнения текущего заголовка элемента управления.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая получает данные ограничивающего прямоугольника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если эта функция прошла успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления заголовка содержит больше элементов, чем может быть отображено одновременно, элемент управления может отображать кнопки переполнения прокручиваемом к элементам, которые не видны. Элемент управления Заголовок должен иметь `HDS_OVERFLOW` и `HDF_SPLITBUTTON` стили для отображения кнопки переполнения. Ограничивающий прямоугольник заключает кнопку переполнения и существует только в том случае, если отображается кнопка переполнения. Дополнительные сведения см. в разделе [стили элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Этот метод отправляет [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущего заголовка элемента управления. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetOverflowRect` метод. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетаскивать разделитель столбцов, чтобы столбец не отображается. Если некоторые столбцы не видны, элемент управления заголовка рисует кнопки переполнения. В следующем примере кода рисует 3D прямоугольник вокруг расположение кнопки переполнения.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>CHeaderCtrl::HitTest  
 Определяет, какой элемент заголовка, расположенный в указанной точке.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in, out] `phdhti`|Указатель на [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) структура, которая указывает точки для проверки и получает результаты теста.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента заголовка, если таковая имеется, в указанной позиции; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущего заголовка элемента управления. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `HitTest` метод. В предыдущем разделе этого примера кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетаскивать разделитель столбцов, чтобы столбец не отображается. В этом примере определяется индекс столбца, если он видим и -1, если столбец не отображается.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>CHeaderCtrl::InsertItem  
 Вставляет элемент в элемент управления "Заголовок" по указанному индексу.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Отсчитываемый от нуля индекс вставляемого элемента. Если значение равно нулю, элемент вставляется в начало заголовка элемента управления. Если значение превышает максимальное значение, элемент вставляется в конце заголовка элемента управления.  
  
 *phdi*  
 Указатель на [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) структуру, содержащую сведения о вставляемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс нового элемента в случае успешного выполнения; в противном случае - 1.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>CHeaderCtrl::Layout  
 Извлекает размер и положение элемента управления "Заголовок" в пределах заданного прямоугольника.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Параметры  
 *pHeaderLayout*  
 Указатель на [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) структуру, которая содержит сведения, используемые для задания, размер и положение заголовка элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для определения соответствующего измерения для нового элемента управления, заголовок, который должен занимать заданного прямоугольника.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 Получает значение индекса для элемента в зависимости от порядка в элементе управления заголовка.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nOrder*  
 Отсчитываемый от нуля заказ, элемент отображается в элементе управления заголовка слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс элемента, в зависимости от порядка в элементе управления заголовка. Индекс подсчитывает слева направо, начиная с 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение макроса Win32 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку упорядочение элементов заголовка.  
  
##  <a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 Задает ширину поля растрового изображения в элемент управления заголовком.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Ширина в пикселях вокруг растрового изображения в существующий элемент управления заголовок поля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина поля растрового изображения в точках.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl #14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 Задает интервал времени ожидания в период между изменение происходит в атрибуты фильтра и учет [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) уведомления.  
  
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
 [!code-cpp[NVC_MFC_CHeaderCtrl #15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 Устанавливает фокус на указанный заголовочный элемент в текущий элемент управления заголовка.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `iItem`|Отсчитываемый от нуля индекс заголовочный элемент.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) сообщение, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_headerCtrl`, который используется для доступа к текущего заголовка элемента управления. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `SetFocusedItem` и `GetFocusedItem` методы. В предыдущем разделе кода мы создали управления заголовка с пятью столбцами. Тем не менее можно перетаскивать разделитель столбцов, чтобы столбец не отображается. Следующий пример задает и затем подтверждает заголовок последнего столбца как элемент фокус ввода.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 Перетащите разделитель между элементов заголовка для указания ручного изменения и удаления элемента заголовка.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Положение указателя. Элемент управления заголовка выделяет соответствующую разделитель, исходя из позиции курсора.  
  
 `nIndex`  
 Индекс выделенной разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс выделенной разделителя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку перетащите заголовок элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CHeaderCtrl № 16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>CHeaderCtrl::SetImageList  
 Назначает заголовок элемента управления списка изображений.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `pImageList`  
 Указатель на `CImageList` объект, содержащий список изображений для назначения заголовка элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CImageList](../../mfc/reference/cimagelist-class.md) объекта, ранее назначенные управления заголовка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `CImageList` Объекта, к которому точек возвращенный указатель является временным и будет удалена в следующей обработки времени простоя.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="setitem"></a>CHeaderCtrl::SetItem  
 Устанавливает атрибуты указанного элемента в элемент управления заголовком.  
  
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
  Далее приведен пример [CHeaderCtrl::GetItem](#getitem).  
  
##  <a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 Задает слева направо порядок элементов в элемент управления заголовком.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Параметры  
 `iCount`  
 Количество элементов заголовка элемента управления.  
  
 `piArray`  
 Указатель на адрес буфера, который получает значения индекса элементов в элементе управления "Заголовок", в том порядке, в котором они появляются в направлении слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение макроса Win32 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Он обеспечивает поддержку упорядочение элементов заголовка.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CHeaderCtrl::GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CTabCtrl-класс](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)   
 [Класс CImageList](../../mfc/reference/cimagelist-class.md)

