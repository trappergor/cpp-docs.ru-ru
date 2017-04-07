---
title: "CImageList-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CImageList
- image lists [C++], CImageList class
- CImageList class
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 19
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
ms.openlocfilehash: e61d99d6d68b1c68cd5e306dd0fcd10d6fe4324d
ms.lasthandoff: 02/24/2017

---
# <a name="cimagelist-class"></a>CImageList-класс
Предоставляет функциональные возможности стандартного элемента управления "список изображений" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|Создает объект `CImageList`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::Add](#add)|Добавляет список изображений изображения или изображения.|  
|[CImageList::Attach](#attach)|Присоединяет списка изображений для `CImageList` объекта.|  
|[CImageList::BeginDrag](#begindrag)|Начинает перетаскивать изображения.|  
|[CImageList::Copy](#copy)|Копирование изображения в `CImageList` объекта.|  
|[CImageList::Create](#create)|Инициализирует список изображений и присоединяет его к `CImageList` объекта.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Удаление списка изображений.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Вызывается методом [CWinApp](../../mfc/reference/cwinapp-class.md) обработчик времени простоя для удаления любой временный `CImageList` объект, созданный `FromHandle`.|  
|[CImageList::Detach](#detach)|Отсоединяет объект image список `CImageList` объекта и возвращает дескриптор списка изображений.|  
|[CImageList::DragEnter](#dragenter)|Блокировки обновления во время операции перетаскивания и отображает изображение перетаскивания в заданной позиции.|  
|[CImageList::DragLeave](#dragleave)|Разблокирует окна и скрывает изображение перетаскивания, чтобы можно было обновить окно.|  
|[CImageList::DragMove](#dragmove)|Перемещение, перетаскиваемого во время операции и перетащите изображение.|  
|[CImageList::DragShowNolock](#dragshownolock)|Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не блокируя окна.|  
|[CImageList::Draw](#draw)|Рисует изображение, перетаскиваемого во время операции перетаскивания и drop.|  
|[CImageList::DrawEx](#drawex)|Рисует изображение элемента списка в заданном контексте устройства. Функция использует указанный стиль рисования и объединяет изображения с указанным цветом.|  
|[CImageList::DrawIndirect](#drawindirect)|Рисует изображение в списке изображений.|  
|[CImageList::EndDrag](#enddrag)|Завершает операцию перетаскивания.|  
|[CImageList::ExtractIcon](#extracticon)|Создает значок на основе образа и маска в списке изображений.|  
|[CImageList::FromHandle](#fromhandle)|Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений. Если объект `CImageList` не прикреплен к дескриптору, создается и прикрепляется временный объект `CImageList`.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений. Если `CImageList` объект не присоединен к дескриптору **NULL** возвращается.|  
|[CImageList::GetBkColor](#getbkcolor)|Получает текущий цвет фона для списка изображений.|  
|[CImageList::GetDragImage](#getdragimage)|Возвращает список временный образ, который используется для перетаскивания.|  
|[CImageList::GetImageCount](#getimagecount)|Получает число изображений в списке изображений.|  
|[CImageList::GetImageInfo](#getimageinfo)|Извлекает сведения об образе.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Извлекает **m_hImageList**.|  
|[CImageList::Read](#read)|Считывает список изображений из архива.|  
|[CImageList::Remove](#remove)|Удаляет изображение из списка изображений.|  
|[CImageList::Replace](#replace)|Заменяет изображение в списке изображений новый образ.|  
|[CImageList::SetBkColor](#setbkcolor)|Задает цвет фона для списка изображений.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Создает новый образ перетаскивания.|  
|[CImageList::SetImageCount](#setimagecount)|Сбрасывает счетчик изображений в списке изображений.|  
|[CImageList::SetOverlayImage](#setoverlayimage)|Добавляет список изображений для использования в качестве маски наложения отсчитываемый от нуля индекс изображения.|  
|[CImageList::Write](#write)|Записывает список изображений в архив.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Возвращает `HIMAGELIST` подключен к `CImageList`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Дескриптор, содержащий список изображений, подключенные к данному объекту.|  
  
## <a name="remarks"></a>Примечания  
 «Список изображений» — это совокупность одного размера изображения, каждое из которых можно ссылаться по его индексу (с нуля). Списки изображений используются для эффективного управления большими наборами значков и точечных рисунков. Все изображения в списке изображений находятся в одной ширину растрового изображения в формате экрана устройства. Список изображений может также включать монохромный точечный рисунок, который содержит маски, используемый для рисования изображения прозрачно (стиль значка). Приложение Microsoft Win32, программный интерфейс (API) предоставляет функции списка изображений для изображения, создание и уничтожить списков изображений, добавление и удаление изображений, Замена изображений, объединение изображений и перетащите изображения.  
  
 Этот элемент управления (и, следовательно, `CImageList` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Дополнительные сведения об использовании `CImageList`, в разделе [управления](../../mfc/controls-mfc.md) и [использование класса CImageList](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="add"></a>CImageList::Add  
 Эта функция вызывается для добавления одно или несколько изображений или значка для списка изображений.  
  
```  
int Add(
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Add(
    CBitmap* pbmImage,  
    COLORREF crMask);  
  
int Add(HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `pbmImage`  
 Указатель на растровое изображение, содержащее изображения или изображения. Число образов, определяется Ширина растрового изображения.  
  
 `pbmMask`  
 Указатель на точечный рисунок, содержащий маску. Если не маска используется список изображений, этот параметр учитывается.  
  
 `crMask`  
 Цвет, используемый для создания маски. Каждый пиксель этого цвета в данной битовой карте замещены черным и соответствующий бит в маске присваивается одно.  
  
 `hIcon`  
 Дескриптор значка, содержащий растровое изображение и маску для нового образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого нового изображения в случае успешного выполнения; в противном случае — значение 1.  
  
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за Освобождение дескриптора значок в том случае, когда вы завершили работу с ним.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#1;](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>CImageList::Attach  
 Эта функция вызывается для присоединения списка изображений для `CImageList` объекта.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `hImageList`  
 Дескриптор объекта списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если вложения завершилась успешно; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#2;](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>CImageList::BeginDrag  
 Эта функция вызывается для начните перетаскивать изображения.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для перетаскивания.  
  
 `ptHotSpot`  
 Координаты начальной позиции перетаскивания (как правило, позиция курсора). Координаты указываются относительно верхнего левого угла изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает список временный образ, который используется для перетаскивания. Изображение объединяет указанное изображение и его маской с курсора. В ответ на последующие `WM_MOUSEMOVE` сообщений, перетащите изображение можно перемещать с помощью `DragMove` функции-члена. Чтобы завершить операцию перетаскивания, можно использовать `EndDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#3;](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>CImageList::CImageList  
 Создает объект `CImageList`.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>CImageList::Copy  
 Эта функция-член реализует поведение функции Win32 [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL Copy(
    int iDst,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);

 
BOOL Copy(
    int iDst,  
    CImageList* pSrc,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);
```  
  
### <a name="parameters"></a>Параметры  
 *iDst*  
 Отсчитываемый от нуля индекс изображения для использования в качестве целевой для операции копирования.  
  
 `iSrc`  
 Отсчитываемый от нуля индекс изображения для использования в качестве источника операции копирования.  
  
 `uFlags`  
 Значение флага бит, указывающий тип операции копирования должна быть выполнена. Этот параметр может принимать одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`ILCF_MOVE`|Индекс образа назначения копируются исходного изображения. Эта операция приводит к несколько экземпляров заданного изображения. Значение по умолчанию — `ILCF_MOVE`.|  
|`ILCF_SWAP`|Исходное и конечное изображения exchange позиции в списке изображений.|  
  
 `pSrc`  
 Указатель на `CImageList` объект, который является целевым объектом операции копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList №&6;](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>CImageList::Create  
 Инициализирует список изображений и присоединяет его к [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
```  
BOOL Create(
    int cx,  
    int cy,  
    UINT nFlags,  
    int nInitial,  
    int nGrow);

 
BOOL Create(
    UINT nBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    LPCTSTR lpszBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    CImageList& imagelist1,  
    int nImage1,  
    CImageList& imagelist2,  
    int nImage2,  
    int dx,  
    int dy);  
  
BOOL Create(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Размеры каждого изображения в пикселях.  
  
 `cy`  
 Размеры каждого изображения в пикселях.  
  
 `nFlags`  
 Указывает тип списка изображений для создания. Этот параметр может быть сочетанием следующих значений, но он может содержать только один из `ILC_COLOR` значения.  
  
|Значение|Значение|  
|-----------|-------------|  
|`ILC_COLOR`|Использовать поведение по умолчанию, если ни один из других `ILC_COLOR`* указанные флаги. Как правило, значение по умолчанию — `ILC_COLOR4`, но для более старых видеодрайверы по умолчанию `ILC_COLORDDB`.|  
|`ILC_COLOR4`|Раздел 4-разрядное (16 цветов) аппаратно независимым точечным рисунком (DIB) как точечный рисунок можно используйте для списка изображений.|  
|`ILC_COLOR8`|Используйте раздел 8-битовое изображение DIB. Цвета, используемые для таблицы цветов являются цветовой палитры полутонов.|  
|`ILC_COLOR16`|Использование 16-разрядное (32 / 64k цвета) раздела DIB.|  
|`ILC_COLOR24`|Используйте 24-разрядный DIB раздела.|  
|`ILC_COLOR32`|Используйте раздел DIB 32-разрядной.|  
|`ILC_COLORDDB`|Используйте аппаратно зависимый растровое изображение.|  
|`ILC_MASK`|Использует маску. Список изображений содержит два массива битов, один из которых — монохромный точечный рисунок, используемой в качестве маски. Если это значение не указан, список изображений содержит только одно растровое изображение. В разделе [Рисование изображений из списка изображений](../../mfc/drawing-images-from-an-image-list.md) Дополнительные сведения о Маскированные изображения.|  
  
 `nInitial`  
 Число образов, которые изначально содержит список изображений.  
  
 `nGrow`  
 Число образов, по которым список изображений может увеличиваться при необходимости изменить размер списка, чтобы освободить место для новых образов системы. Этот параметр представляет число новых образов, которые может содержать список размеров изображений.  
  
 `nBitmapID`  
 Идентификаторы ресурсов растрового изображения для списка изображений.  
  
 `crMask`  
 Цвет, используемый для создания маски. Каждый пиксель этого цвета в указанном точечном рисунке замещены черным, а соответствующий бит в маске присваивается одно.  
  
 `lpszBitmapID`  
 Строка, содержащая идентификаторы ресурса изображений.  
  
 `imagelist1`  
 Ссылка на объект `CImageList`.  
  
 `nImage1`  
 Индекс первого существующий образ.  
  
 `imagelist2`  
 Ссылка на объект `CImageList`.  
  
 `nImage2`  
 Индекс второго существующий образ.  
  
 `dx`  
 Смещение по оси x второе изображение в связи с первого изображения в пикселях.  
  
 `dy`  
 Смещение по оси y от второго изображения в связи с первого изображения в точках.  
  
 `pImageList`  
 Указатель на объект `CImageList`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CImageList` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает список изображений и присоединяет его к `CImageList`объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#7;](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>CImageList::DeleteImageList  
 Эта функция вызывается для удаления списка изображений.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList №&8;](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>CImageList::DeleteTempMap  
 Вызывается автоматически `CWinApp` обработчик времени простоя `DeleteTempMap` удаляет все временные `CImageList` объектов, созданных [FromHandle](#fromhandle), но не уничтожает все дескрипторы ( `hImageList`) временно связанный с **ImageList** объектов.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList №&9;](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>CImageList::Detach  
 Эта функция вызывается для отсоединения объект image список `CImageList` объекта.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта списка изображений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает дескриптор объекта списка изображений.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>CImageList::DragEnter  
 Во время операции перетаскивания, блокировка обновления окном, заданным параметром `pWndLock` и отображает изображение перетаскивания в позиции, указанной параметром `point`.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndLock`  
 Указатель на окно, которому принадлежит изображение перетаскивания.  
  
 `point`  
 Место для отображения изображения перетащите. Координаты указываются относительно верхнего левого угла окна (не клиентской области).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Координаты указываются относительно верхнего левого угла окна, чтобы компенсировать ширину окна элементов, таких как граница, заголовок окна и меню, указывая координаты.  
  
 Если `pWndLock` — **NULL**, эта функция выводит изображение в контексте отображения, связанные с окном рабочего стола и координаты указываются относительно верхнего левого угла экрана.  
  
 Эта функция блокирует все обновления для данного окна во время операции перетаскивания. Если необходимо сделать любое изображение во время операции перетаскивания, такие как выделение целевой объект операции и перетащите можно временно скрыть перетаскиваемого изображение с помощью [CImageList::DragLeave](#dragleave) функции.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>CImageList::DragLeave  
 Разблокирует окном, заданным параметром `pWndLock` и скрывает изображение перетаскивания, что позволяет обновить окно.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndLock`  
 Указатель на окно, которому принадлежит изображение перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::EndDrag](#enddrag).  
  
##  <a name="dragmove"></a>CImageList::DragMove  
 Эта функция вызывается для перемещения, перетаскиваемого во время операции и перетащите изображение.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Новое положение перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается в ответ на `WM_MOUSEMOVE` сообщение. Чтобы начать операцию перетаскивания, используйте `BeginDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#4;](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>CImageList::DragShowNolock  
 Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не блокируя окна.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, является ли изображение перетаскивания для отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 [CImageList::DragEnter](#dragenter) функция блокирует все обновления окна во время операции перетаскивания. Эта функция окна не блокируется.  
  
##  <a name="draw"></a>CImageList::Draw  
 Эта функция вызывается для рисования изображения, перетаскиваемого во время операции перетаскивания и drop.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель контекста устройства назначения.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для рисования.  
  
 `pt`  
 Расположение, в которой будет создан в рамках заданного контекста устройств.  
  
 `nStyle`  
 Флаг, указывающий стиль рисования. Это может быть один или несколько из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`ILD_BLEND25`, **ILD_FOCUS**|Рисует изображение, смешение 25 процентов с системным цветом. Если список изображений не содержит маску, это значение игнорируется.|  
|`ILD_BLEND50`, **ILD_SELECTED**, **ILD_BLEND**|Рисует изображение, смешение 50 процентов с системным цветом. Если список изображений не содержит маску, это значение игнорируется.|  
|**ILD_MASK**|Рисует маски.|  
|`ILD_NORMAL`|Рисует изображение, используя цвет фона для списка изображений. Если цвет фона `CLR_NONE` значение изображение рисуется прозрачно с помощью маски.|  
|`ILD_TRANSPARENT`|Рисует изображение, прозрачно с помощью маски, независимо от того, цвет фона.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::SetOverlayImage](#setoverlayimage).  
  
##  <a name="drawex"></a>CImageList::DrawEx  
 Рисует изображение элемента списка в заданном контексте устройства.  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    COLORREF clrBk,  
    COLORREF clrFg,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель контекста устройства назначения.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для рисования.  
  
 `pt`  
 Расположение, в которой будет создан в рамках заданного контекста устройств.  
  
 `sz`  
 Размер части изображения для рисования, относительно верхнего левого угла изображения. В разделе `dx` и *dy* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 *clrBk*  
 Фоновый цвет изображения. В разделе *rgbBk* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 *clrFg*  
 Цвет изображения. В разделе *rgbFg* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 `nStyle`  
 Флаг, указывающий стиль рисования. В разделе *fStyle* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция использует указанный стиль рисования и объединяет изображения с указанным цветом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#10;](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>CImageList::DrawIndirect  
 Вызовите эту функцию-член для рисования изображения в списке изображений.  
  
```  
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

 
BOOL DrawIndirect(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    POINT ptOrigin,  
    UINT fStyle = ILD_NORMAL,  
    DWORD dwRop = SRCCOPY,  
    COLORREF rgbBack = CLR_DEFAULT,  
    COLORREF rgbFore = CLR_DEFAULT,  
    DWORD fState = ILS_NORMAL,  
    DWORD Frame = 0,  
    COLORREF crEffect = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>Параметры  
 *pimldp*  
 Указатель на [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) структуру, содержащую сведения об операции рисования.  
  
 `pDC`  
 Указатель контекста устройства назначения. Необходимо удалить это [CDC](../../mfc/reference/cdc-class.md) объекта, когда вы завершили работу с ним.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для отрисовки.  
  
 `pt`  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую- и y координаты x положением изображения.  
  
 `sz`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры, указывающее размер изображения для отрисовки.  
  
 *ptOrigin*  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, содержащую — и y координаты x указания верхней левой части операции рисования, относительно самого изображения. Изображения, слева — координаты x и выше координату y — не пикселов.  
  
 `fStyle`  
 Флаг, указывающий стиль рисования и, возможно, изображение перекрытия. Сведения в образе наложения см. Реализация по умолчанию MFC, `ILD_NORMAL`, Рисует изображение, используя цвет фона для списка изображений. Если цвет фона `CLR_NONE` значение изображение рисуется прозрачно с помощью маски.  
  
 Другие возможные стили, описаны в разделе **fStyle** членом [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) структуры.  
  
 *dwRop*  
 Значение, указывающее код растровая операция. Эти коды определяют, как данные о цвете для исходного прямоугольника будут объединены с данными цвета для прямоугольника назначения для достижения окончательного цвета. Реализация, по умолчанию MFC **SRCCOPY**, копирует исходного прямоугольника в прямоугольник назначения. Этот параметр учитывается, если `fStyle` параметр включает в себя **ILD_ROP** флаг.  
  
 Другие возможные значения описаны в разделе **dwRop** членом [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) структуры.  
  
 *rgbBack*  
 Цвет фона изображения по умолчанию `CLR_DEFAULT`. Этот параметр может иметь определяемые приложением значения RGB или одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`CLR_DEFAULT`|По умолчанию цвет фона. Изображение отображается цветом фона списка изображений.|  
|`CLR_NONE`|Без цвета фона. Изображение является прозрачным.|  
  
 *rgbFore*  
 Изображения по умолчанию цвет переднего плана, `CLR_DEFAULT`. Этот параметр может иметь определяемые приложением значения RGB или одно из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`CLR_DEFAULT`|Цвет по умолчанию. Отрисовывается в качестве цвета переднего плана системным цветом.|  
|`CLR_NONE`|Нет цвета blend. Изображение смешивается с цветом контекста устройства назначения.|  
  
 Этот параметр используется только в том случае, если `fStyle` включает `ILD_BLEND25` или `ILD_BLEND50` флаг.  
  
 *fState*  
 Флаг, указывающий состояние рисования. Этот член может содержать один или несколько флагов состояния списка изображений.  
  
 *Кадр*  
 Влияет на поведение эффектов saturate и альфа смешения.  
  
 При использовании с **ILS_SATURATE**, этот элемент содержит значение, которое добавляется для каждого компонента цвета тройка RGB для каждого пиксела в значок.  
  
 При использовании с **ILS_APLHA**, этот член содержит значение альфа-канала. Это значение может быть от 0 до 255, причем 0 соответствует полной прозрачности, а 255, полностью непрозрачным.  
  
 *crEffect*  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, используемое для эффекты свечения и тени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если изображение успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Первая версия следует используйте, если требуется заполнить структуру Win32 самостоятельно. Если вы хотите воспользоваться преимуществами один или несколько аргументов по умолчанию MFC или избежать управления структуры, используйте второй версии.  
  
 Наложение изображения — это изображение, рисуется поверх основного изображения, в эту функцию-член, `nImage` параметр. Рисование с помощью маски наложения [рисовать](#draw) от единицы индекс маску наложения, указанные с помощью этой функции [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&11;](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>CImageList::EndDrag  
 Эта функция вызывается для завершения операции перетаскивания.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы начать операцию перетаскивания, используйте `BeginDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#5;](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>CImageList::ExtractIcon  
 Эта функция вызывается для создания значка на основе образа и его связанных маску в списке изображений.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует поведение [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) макроса для создания значка. Обратитесь к [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) макрос подробнее на значок создания и очистки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#12;](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>CImageList::FromHandle  
 Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `hImageList`  
 Задает список изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CImageList` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CImageList` еще не присоединен к дескриптору временный `CImageList` объект создается и прикрепляется. Этот временный `CImageList` допустимо только до следующей приложение имеет время простоя в свой цикл событий, в этот момент все временные объекты удаляются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#13;](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>CImageList::FromHandlePermanent  
 Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `hImageList`  
 Задает список изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CImageList` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `CImageList` объект не присоединен к дескриптору **NULL** возвращается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#14;](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>CImageList::GetBkColor  
 Эта функция вызывается для получения текущего цвет фона для списка изображений.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB `CImageList` цвет фона объекта.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>CImageList::GetDragImage  
 Возвращает список временный образ, который используется для перетаскивания.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPoint`  
 Адрес [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, которая получает текущий перетащите позиции.  
  
 *lpPointHotSpot*  
 Адрес **ТОЧКИ** структуру, которая получает смещение относительно положения перетащите изображение перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, указатель на образе временный список, который используется для перетаскивания; в противном случае — **NULL**.  
  
##  <a name="getimagecount"></a>CImageList::GetImageCount  
 Эта функция вызывается для получения числа изображений в списке изображений.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число изображений.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>CImageList::GetImageInfo  
 Эта функция вызывается для получения сведений об образе.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс изображения.  
  
 *pImageInfo*  
 Указатель на [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) структуры, который получает сведения об образе. Сведения в этой структуре можно использовать для непосредственного управления растровых изображений для изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `IMAGEINFO` Структура содержит сведения об изображении в списке изображений.  
  
##  <a name="getsafehandle"></a>CImageList::GetSafeHandle  
 Эта функция вызывается для получения **m_hImageList** данные-член.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор списка подключенных изображений; в противном случае **NULL** , если объект не присоединен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#15;](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>CImageList::m_hImageList  
 Дескриптор списка изображений, подключенные к данному объекту.  
  
 **HIMAGELIST m_hImageList;**  
  
### <a name="remarks"></a>Примечания  
 **M_hImageList** член данных — это открытая переменная типа `HIMAGELIST`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#23;](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>CImageList::operator HIMAGELIST  
 Этот оператор используется для получения вложенных дескриптор `CImageList` объекта.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор списка изображений, представленных `CImageList` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает непосредственное использование `HIMAGELIST` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList №&16;](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>CImageList::Read  
 Эта функция вызывается для чтения списка изображений из архива.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Параметры  
 `pArchive`  
 Указатель на `CArchive` объект, из которого считываются списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&18;](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>CImageList::Remove  
 Вызовите эту функцию, чтобы удалить изображение из объекта списка изображений.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Все элементы `nImage` теперь вниз на одну позицию. Например если список изображений содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первой позиции. `nImage`=&0; в позиции первого элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&19;](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>CImageList::Replace  
 Эта функция используется для замены изображений в списке изображений новый образ.  
  
```  
BOOL Replace(
    int nImage,  
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Replace(
    int nImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для замены.  
  
 `pbmImage`  
 Указатель на точечный рисунок, содержащий изображение.  
  
 `pbmMask`  
 Указатель на точечный рисунок, содержащий маску. Если не маска используется список изображений, этот параметр учитывается.  
  
 `hIcon`  
 Дескриптор для значка, который содержит растровое изображение и маску для нового образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает версию **BOOL** возвращает ненулевое значение, если успешно; в противном случае — 0.  
  
 Возвращает версию `int` возвращает отсчитываемый от нуля индекс изображения, если успешно; в противном случае — значение 1.  
  
### <a name="remarks"></a>Примечания  
 Это функция-член вызывается после вызова метода [SetImageCount](#setimagecount) назначается новый, допустимых изображений заполнитель изображения номера индекса.  
  
### <a name="example"></a>Пример  
  В примере показано [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>CImageList::SetBkColor  
 Вызывайте эту функцию, чтобы задать цвет фона для списка изображений.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Параметры  
 `cr`  
 Цвет фона для задания. Он может быть `CLR_NONE`. В этом случае изображения отображаются прозрачно с помощью маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий цвет фона в случае успешного выполнения; в противном случае `CLR_NONE`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&20;](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>CImageList::SetDragCursorImage  
 Создает новый образ перетаскивания путем объединения с текущего изображения перетащите заданного изображения (обычно изображение курсора мыши).  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 *nDrag*  
 Индекс нового образа для объединения с изображение перетаскивания.  
  
 `ptHotSpot`  
 Позиция гиперобъект в новый образ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Поскольку функции перетаскивания использования нового образа во время операции перетаскивания, следует использовать Windows [функция ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) функции, чтобы скрыть курсор мыши после вызова метода `CImageList::SetDragCursorImage`. В противном случае система может быть два курсора мыши на время операции перетаскивания.  
  
##  <a name="setimagecount"></a>CImageList::SetImageCount  
 Вызовите эту функцию-член для сброса число изображений в `CImageList` объекта.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Параметры  
 *uNewCount*  
 Значение, указывающее общее число новых изображений в списке изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции-члена для увеличения числа изображений в списке изображений, затем вызовите [заменить](#replace) для каждое дополнительное изображение назначить новые индексы допустимых изображений. Если не указывать индексы для действительных изображений, операции рисования, которые создают новые образы будет непредсказуемым.  
  
 Если уменьшить размер списка изображений с помощью этой функции, усеченное образы будут освобождены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#21;](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>CImageList::SetOverlayImage  
 Вызовите эту функцию, чтобы добавить в список изображений для использования в качестве маски наложения отсчитываемый от нуля индекс изображения.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для использования в качестве маски наложения.  
  
 *nOverlay*  
 От единицы индекс маску наложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 До четырех индексы могут добавляться в список.  
  
 Наложение маска — изображение с прозрачным через другое изображение. Рисование маски наложение на изображение с помощью [CImageList::Draw](#draw) от единицы индекс маску наложения, указанные с помощью этой функции **INDEXTOOVERLAYMASK** макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&#22;](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>CImageList::Write  
 Эта функция вызывается для записи объекта списка изображений в архив.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Параметры  
 `pArchive`  
 Указатель на `CArchive` объект, в котором будет храниться список изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList&17;](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl-класс](../../mfc/reference/ctabctrl-class.md)

