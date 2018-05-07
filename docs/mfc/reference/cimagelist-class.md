---
title: CImageList-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54804ff4c6b2410aa47ea4d7cf5f5d3ab48316f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CImageList::Add](#add)|Добавляет изображение или изображения для списка изображений.|  
|[CImageList::Attach](#attach)|Присоединяет списка изображений для `CImageList` объекта.|  
|[CImageList::BeginDrag](#begindrag)|Начинает перетаскивать изображение.|  
|[CImageList::Copy](#copy)|Копирование изображения в `CImageList` объекта.|  
|[CImageList::Create](#create)|Инициализирует списка изображений и прикрепляет его к `CImageList` объекта.|  
|[CImageList::DeleteImageList](#deleteimagelist)|Удаление списка изображений.|  
|[CImageList::DeleteTempMap](#deletetempmap)|Вызывается методом [CWinApp](../../mfc/reference/cwinapp-class.md) обработчиком времени простоя, чтобы удалить все временные `CImageList` объект, созданный `FromHandle`.|  
|[CImageList::Detach](#detach)|Отсоединяет объект списка image `CImageList` объекта и возвращает дескриптор для списка изображений.|  
|[CImageList::DragEnter](#dragenter)|Блокирует обновлений во время операции перетаскивания и отображает изображение перетаскивания в указанной позиции.|  
|[CImageList::DragLeave](#dragleave)|Разблокирует окна и скрыть изображение перетаскивания, чтобы можно было обновить окно.|  
|[CImageList::DragMove](#dragmove)|Перемещение образа, перетаскиваемый во время операции перетаскивания и вставки.|  
|[CImageList::DragShowNolock](#dragshownolock)|Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не блокируя окна.|  
|[CImageList::Draw](#draw)|Формирует изображение, перетаскиваемый во время операции перетаскивания и вставки.|  
|[CImageList::DrawEx](#drawex)|Рисует изображение элемента списка в заданном контексте устройства. Функция использует указанный стиль рисования и объединяет изображения с указанным цветом.|  
|[CImageList::DrawIndirect](#drawindirect)|Рисует изображение из списка изображений.|  
|[CImageList::EndDrag](#enddrag)|Завершает операцию перетаскивания.|  
|[CImageList::ExtractIcon](#extracticon)|Создает на основе образа и маски в список изображений значка.|  
|[CImageList::FromHandle](#fromhandle)|Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений. Если объект `CImageList` не прикреплен к дескриптору, создается и прикрепляется временный объект `CImageList`.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Возвращает указатель на `CImageList` объект для заданного дескриптора для списка изображений. Если `CImageList` объект не присоединен к дескриптору, **NULL** возвращается.|  
|[CImageList::GetBkColor](#getbkcolor)|Получает текущий цвет фона для списка изображений.|  
|[CImageList::GetDragImage](#getdragimage)|Получает список временного изображения, используемый для перетаскивания.|  
|[CImageList::GetImageCount](#getimagecount)|Возвращает число изображений в списке изображений.|  
|[CImageList::GetImageInfo](#getimageinfo)|Извлекает сведения об изображении.|  
|[CImageList::GetSafeHandle](#getsafehandle)|Извлекает **m_hImageList**.|  
|[CImageList::Read](#read)|Считывает список изображений из архива.|  
|[CImageList::Remove](#remove)|Удаление изображения из списка изображений.|  
|[CImageList::Replace](#replace)|Заменяет изображение в список изображений новый образ.|  
|[CImageList::SetBkColor](#setbkcolor)|Задает цвет фона для списка изображений.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Создает новое изображение перетаскивания.|  
|[CImageList::SetImageCount](#setimagecount)|Сбрасывает счетчик изображений в списке изображений.|  
|[CImageList::SetOverlayImage](#setoverlayimage)|Добавляет список изображений для использования в качестве маски наложения отсчитываемый от нуля индекс изображения.|  
|[CImageList::Write](#write)|Записывает список изображений в архив.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Возвращает `HIMAGELIST` присоединяется к `CImageList`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|Дескриптор, содержащий список изображений, присоединенного к данному объекту.|  
  
## <a name="remarks"></a>Примечания  
 «Список изображений» — это совокупность аналогичного размера изображения, каждый из которых можно идентифицировать по его отсчитываемый от нуля индекс. Списки изображений используются для эффективного управления большими наборами значков и точечных рисунков. Все образы в список изображений, содержатся в один расширенный точечного рисунка в формате экрана устройства. Список изображений может также включать монохромный точечный рисунок, содержащий маски, используемый для рисования изображения прозрачно (стиль значка). Приложение Microsoft Win32, программный интерфейс (API) предоставляет функции списка изображений, позволяющие Рисование изображений, создать и уничтожить списков изображений, добавление и удаление изображений из, замены изображений, объединение изображений и перетащите изображения.  
  
 Этот элемент управления (и, следовательно, `CImageList` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Дополнительные сведения об использовании `CImageList`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CImageList](../../mfc/using-cimagelist.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="add"></a>  CImageList::Add  
 Вызывайте эту функцию, чтобы добавить одно или несколько изображений или значка для списка изображений.  
  
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
 Указатель к растровому изображению, содержащий маску. Если используется список изображений не маска, этот параметр учитывается.  
  
 `crMask`  
 Цвет, используемый для создания маски. Каждая точка этого цвета в данной битовой карте черный цвет и соответствующий бит в битовой маске присваивается одно.  
  
 `hIcon`  
 Дескриптор значка, который содержит точечный рисунок и маски для нового образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс первого нового изображения в случае успешного выполнения; в противном случае - 1.  
  
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за Освобождение дескриптора значок в том случае, когда вы завершили работу с ним.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>  CImageList::Attach  
 Эта функция вызывается для списка изображений для присоединения `CImageList` объекта.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Параметры  
 `hImageList`  
 Дескриптор объекта списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подключение выполнено успешно; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>  CImageList::BeginDrag  
 Эта функция вызывается для начните перетаскивать изображение.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для перетаскивания.  
  
 `ptHotSpot`  
 Координаты начальной позиции перетащите (как правило, позиция курсора). Координаты указываются относительно верхнего левого угла изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает список временного изображения, используемый для перетаскивания. Изображение объединяет указанного образа и его маской с текущий курсор. В ответ на последующие `WM_MOUSEMOVE` сообщений, перетащите изображение можно перемещаться с помощью `DragMove` функции-члена. Чтобы завершить операцию перетаскивания, можно использовать `EndDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>  CImageList::CImageList  
 Создает объект `CImageList`.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>  CImageList::Copy  
 Эта функция-член реализует поведение функции Win32 [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520), как описано в Windows SDK.  
  
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
 Отсчитываемый от нуля индекс образа для использования в качестве целевой для операции копирования.  
  
 `iSrc`  
 Отсчитываемый от нуля индекс образа для использования в качестве источника операции копирования.  
  
 `uFlags`  
 Значение флага бит, указывающий тип операции копирования будет выполняться. Этот параметр может принимать одно из следующих значений:  
  
|Значение|Смысл|  
|-----------|-------------|  
|`ILCF_MOVE`|Исходный образ копируется индекс образа назначения. Эта операция приводит к несколько экземпляров заданного изображения. Значение по умолчанию — `ILCF_MOVE`.|  
|`ILCF_SWAP`|Исходное и конечное изображения обмена позиций в списке изображений.|  
  
 `pSrc`  
 Указатель на `CImageList` объект, который является целевым объектом операции копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>  CImageList::Create  
 Инициализирует списка изображений и прикрепляет его к [CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
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
 Измерения каждого изображения в пикселях.  
  
 `cy`  
 Измерения каждого изображения в пикселях.  
  
 `nFlags`  
 Указывает тип списка изображений для создания. Этот параметр может быть сочетанием следующих значений, но он может включать только один из `ILC_COLOR` значения.  
  
|Значение|Смысл|  
|-----------|-------------|  
|`ILC_COLOR`|Использовать поведение по умолчанию, если ни один из других `ILC_COLOR`* указаны флаги. Как правило, значение по умолчанию — `ILC_COLOR4`; но старые драйверы отображения по умолчанию принимается `ILC_COLORDDB`.|  
|`ILC_COLOR4`|Раздел 4-разрядное (16 цветов) аппаратно независимый точечный рисунок (DIB) как растровое изображение можно используйте для списка изображений.|  
|`ILC_COLOR8`|Используйте раздел DIB 8-разрядное. Цвета, используемые для таблицы цветов, цветовой полутоновой палитры.|  
|`ILC_COLOR16`|Использовать 16-разрядное (32 / 64k цвет) раздела DIB.|  
|`ILC_COLOR24`|Используйте 24-разрядный раздел DIB.|  
|`ILC_COLOR32`|Используйте раздел DIB 32-разрядной.|  
|`ILC_COLORDDB`|Используйте аппаратно зависимая Битовая карта.|  
|`ILC_MASK`|Использует маску. Список изображений содержит два точечные рисунки, один из которых является монохромный растровое изображение, используемое в качестве маски. Если это значение не указан, список изображений содержит только один точечный рисунок. В разделе [Рисование изображений из списка изображений](../../mfc/drawing-images-from-an-image-list.md) Дополнительные сведения об образах маской.|  
  
 `nInitial`  
 Число образов, которые изначально содержит список изображений.  
  
 `nGrow`  
 Количество изображений, по которым может увеличиваться список изображений, когда системе необходимо изменить размер списка, чтобы освободить место для новых образов. Этот параметр представляет количество новых образов, которые может содержать список изображений с измененным размером.  
  
 `nBitmapID`  
 Идентификаторы ресурсов растрового изображения для списка изображений.  
  
 `crMask`  
 Цвет, используемый для создания маски. Каждая точка этого цвета в указанном точечном рисунке черный цвет, и соответствующий бит в битовой маске присваивается одно.  
  
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
 Смещение по оси x второй изображения по отношению к первому изображению в пикселях.  
  
 `dy`  
 Смещение по оси y второй изображения по отношению к первому изображению в пикселях.  
  
 `pImageList`  
 Указатель на объект `CImageList`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CImageList` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает список изображений и прикрепляет его к `CImageList` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList  
 Эта функция вызывается для удаления списка изображений.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap  
 Автоматически вызывается `CWinApp` обработчиком времени простоя `DeleteTempMap` удаляет все временные `CImageList` объектов, созданных [FromHandle](#fromhandle), но не уничтожает все дескрипторы ( `hImageList`) временно связанный с **ImageList** объектов.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>  CImageList::Detach  
 Эта функция вызывается для отсоединения объект списка image `CImageList` объекта.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор объекта списка изображений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает дескриптор объекта списка изображений.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::Attach](#attach).  
  
##  <a name="dragenter"></a>  CImageList::DragEnter  
 При выполнении операции перетаскивания блокировки обновления окном, заданным параметром `pWndLock` и отображает изображение перетаскивания в позиции, указанной параметром `point`.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndLock`  
 Указатель на окно, которому принадлежит изображение перетаскивания.  
  
 `point`  
 Место для отображения изображения перетаскивания. Координаты указываются относительно верхнего левого угла окна (не клиентской области).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Координаты указываются относительно верхнего левого угла окна, чтобы компенсировать ширины окна элементов, таких как граница, строку заголовка и меню, при указании координаты.  
  
 Если `pWndLock` — **NULL**, эта функция выводит изображение в контексте отображения, связанные с окном рабочего стола и координаты указываются относительно верхнего левого угла экрана.  
  
 Эта функция блокирует все обновления для заданного окна во время операции перетаскивания. Если необходимо выполнить любой рисунок во время операции перетаскивания, например выделение целевого объекта для операции перетаскивания и вставки, можно временно скрыть перетаскиваемого изображения с помощью [CImageList::DragLeave](#dragleave) функции.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::BeginDrag](#begindrag).  
  
##  <a name="dragleave"></a>  CImageList::DragLeave  
 Разблокирует окном, заданным параметром `pWndLock` и скрывает изображение перетаскивания, позволяя обновить окно.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndLock`  
 Указатель на окно, которому принадлежит изображение перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::EndDrag](#enddrag).  
  
##  <a name="dragmove"></a>  CImageList::DragMove  
 Вызывайте эту функцию, чтобы переместить изображение, перетаскиваемый во время операции перетаскивания и вставки.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Новая позиция перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается в ответ на `WM_MOUSEMOVE` сообщение. Чтобы начать операцию перетаскивания, используйте `BeginDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>  CImageList::DragShowNolock  
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
 [CImageList::DragEnter](#dragenter) функция блокирует все обновления в окно во время операции перетаскивания. Однако эта функция не блокирует окна.  
  
##  <a name="draw"></a>  CImageList::Draw  
 Эта функция вызывается для отрисовки изображения, перетаскиваемый во время операции перетаскивания и вставки.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства назначения.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для рисования.  
  
 `pt`  
 Расположение, в котором будет размещено в заданном контексте устройства.  
  
 `nStyle`  
 Флаг, указывающий, стиль рисования. Может быть один или несколько из следующих значений:  
  
|Значение|Смысл|  
|-----------|-------------|  
|`ILD_BLEND25`, **ILD_FOCUS**|Рисует изображение наложения 25 процентов с системным цветом. Если список изображений не содержит маску, это значение игнорируется.|  
|`ILD_BLEND50`, **ILD_SELECTED**, **ILD_BLEND**|Рисует изображение наложения 50 процентов с системным цветом. Если список изображений не содержит маску, это значение игнорируется.|  
|**ILD_MASK**|Рисует маски.|  
|`ILD_NORMAL`|Рисует изображение, используя цвет фона для списка изображений. Если цвет фона — `CLR_NONE` значение изображения отображаются прозрачно с помощью маски.|  
|`ILD_TRANSPARENT`|Рисует изображение прозрачно с помощью маски, независимо от того, цвет фона.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::SetOverlayImage](#setoverlayimage).  
  
##  <a name="drawex"></a>  CImageList::DrawEx  
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
 Указатель на контекст устройства назначения.  
  
 `nImage`  
 Отсчитываемый от нуля индекс изображения для рисования.  
  
 `pt`  
 Расположение, в котором будет размещено в заданном контексте устройства.  
  
 `sz`  
 Размер части изображения для рисования, относительно верхнего левого угла изображения. В разделе `dx` и *dy* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в Windows SDK.  
  
 *clrBk*  
 Фоновый цвет изображения. В разделе *rgbBk* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в Windows SDK.  
  
 *clrFg*  
 Основной цвет изображения. В разделе *rgbFg* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в Windows SDK.  
  
 `nStyle`  
 Флаг, указывающий, стиль рисования. В разделе *fStyle* в [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция использует указанный стиль рисования и объединяет изображения с указанным цветом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>  CImageList::DrawIndirect  
 Вызовите эту функцию-член для рисования изображения из списка изображений.  
  
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
 Указатель на контекст устройства назначения. Необходимо удалить этот [CDC](../../mfc/reference/cdc-class.md) объекта, когда вы завершили работу с ним.  
  
 `nImage`  
 Отсчитываемый от нуля индекс образа для отрисовки.  
  
 `pt`  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, содержащая координаты x и y-положением изображения.  
  
 `sz`  
 Объект [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуры, определяющее размер изображения для отрисовки.  
  
 *ptOrigin*  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, содержащая координаты x и y-указание верхнего левого угла операции рисования, относительно само изображение. Изображения, до левой координаты x и более поздних версий координату по оси y не пикселов.  
  
 `fStyle`  
 Флаг, определяющий стиль рисования и, возможно, изображение перекрытия. В разделе примечаний сведения на изображение перекрытия. Реализация по умолчанию MFC, `ILD_NORMAL`, Рисует изображение, используя цвет фона для списка изображений. Если цвет фона — `CLR_NONE` значение изображения отображаются прозрачно с помощью маски.  
  
 Другие возможные стили, описаны в разделе **fStyle** членом [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) структуры.  
  
 *dwRop*  
 Значение, указывающее код выполнению растровую операцию. Эти коды определяют, как данные о цвете для исходного прямоугольника будет добавляться к данные о цвете для достижения на окончательный цвет прямоугольника назначения. Реализация, по умолчанию MFC **SRCCOPY**, копирует исходного прямоугольника в прямоугольник назначения. Этот параметр учитывается, если `fStyle` параметр включает в себя **ILD_ROP** флаг.  
  
 Другие возможные значения описаны в разделе **dwRop** членом [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) структуры.  
  
 *rgbBack*  
 Цвет фона изображения по умолчанию `CLR_DEFAULT`. Этот параметр может иметь определяемые приложением значения RGB или одно из следующих значений:  
  
|Значение|Смысл|  
|-----------|-------------|  
|`CLR_DEFAULT`|Цвет фона по умолчанию. Цвет фона для списка изображений с помощью рисуется изображение.|  
|`CLR_NONE`|Без цвета фона. Изображение является прозрачным.|  
  
 *rgbFore*  
 Изображения по умолчанию цвет переднего плана, `CLR_DEFAULT`. Этот параметр может иметь определяемые приложением значения RGB или одно из следующих значений:  
  
|Значение|Смысл|  
|-----------|-------------|  
|`CLR_DEFAULT`|Цвет по умолчанию. С помощью системным цветом выделения цветом переднего плана, рисуется изображение.|  
|`CLR_NONE`|Нет цвета blend. Изображение смешивается с цветом контекста устройства назначения.|  
  
 Этот параметр используется только в том случае, если `fStyle` включает `ILD_BLEND25` или `ILD_BLEND50` флаг.  
  
 *fState*  
 Флаг, указывающий состояние рисования. Этот член может содержать один или несколько флагов состояния списка изображений.  
  
 *Frame*  
 Влияет на поведение эффектов saturate и альфа смешения.  
  
 При использовании с **ILS_SATURATE**, этот член содержит значение, которое добавляется для каждого компонента цвета RGB треугольник для каждой точки на значке.  
  
 При использовании с **ILS_APLHA**, этот член содержит значение альфа-канала. Это значение может быть от 0 до 255, где 0 соответствует полностью прозрачным, а 255, полностью непрозрачный.  
  
 *crEffect*  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, используемое для эффекта свечения и тени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если изображение успешно формируемого; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите заполнить структуру Win32 самостоятельно, используйте первой версии. Используйте второй версии, чтобы воспользоваться преимуществами один или несколько аргументов по умолчанию MFC или избежать управление структуры.  
  
 Изображение перекрытия — это изображение, рисуется поверх основного образа, указанного в эту функцию-член с `nImage` параметра. Нарисовать с помощью маски наложения [нарисовать](#draw) функцию-член с единицы индекс маски наложение, указанный с помощью [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>  CImageList::EndDrag  
 Эта функция вызывается для завершения операции перетаскивания.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы начать операцию перетаскивания, используйте `BeginDrag` функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>  CImageList::ExtractIcon  
 Эта функция вызывается для создания на основе образа и его связанные маски, в список изображений значка.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значка в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует поведение [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) макрос для значка. Ссылаться на [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) макрос Дополнительные сведения о значок создания и очистки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>  CImageList::FromHandle  
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
 Если `CImageList` уже не присоединен к дескриптору, временный `CImageList` объект создается и прикрепляется. Этот временный `CImageList` , допустимо только до следующей приложение имеет время простоя в его цикл событий, после чего все временные объекты удаляются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent  
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
 Если `CImageList` объект не присоединен к дескриптору, **NULL** возвращается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>  CImageList::GetBkColor  
 Эта функция вызывается для получения текущего цвета фона для списка изображений.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение цвета RGB `CImageList` объекта цвет фона.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::SetBkColor](#setbkcolor).  
  
##  <a name="getdragimage"></a>  CImageList::GetDragImage  
 Получает список временного изображения, используемый для перетаскивания.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 `lpPoint`  
 Адрес [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуры, который получает текущий перетащите позиции.  
  
 *lpPointHotSpot*  
 Адрес **ТОЧКИ** структуру, которая получает смещение относительно положения перетащите изображение перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, указатель на образе временный список, который используется для перетаскивания; в противном случае **NULL**.  
  
##  <a name="getimagecount"></a>  CImageList::GetImageCount  
 Вызывайте эту функцию для извлечения нескольких изображений в списке изображений.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество изображений.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::ExtractIcon](#extracticon).  
  
##  <a name="getimageinfo"></a>  CImageList::GetImageInfo  
 Эта функция вызывается для получения сведений об образе.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа.  
  
 *pImageInfo*  
 Указатель на [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) структуры, который получает сведения об образе. Сведения в этой структуре можно использовать для прямого управления для изображения, точечные рисунки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `IMAGEINFO` Структура содержит сведения об изображении в списка изображений.  
  
##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle  
 Эта функция вызывается для получения **m_hImageList** члена данных.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор список подключенных изображений; в противном случае **NULL** Если объект не подключен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>  CImageList::m_hImageList  
 Дескриптор списка изображений, присоединенного к данному объекту.  
  
 **HIMAGELIST m_hImageList;**  
  
### <a name="remarks"></a>Примечания  
 **M_hImageList** член данных — это открытая переменная типа `HIMAGELIST`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST  
 Этот оператор используется для получения вложенного дескриптор `CImageList` объекта.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если успешно, дескриптор для списка изображений, представленных `CImageList` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор — оператор приведения, который поддерживает прямое использование `HIMAGELIST` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>  CImageList::Read  
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
 [!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>  CImageList::Remove  
 Вызывайте эту функцию, чтобы удалить изображение из объекта списка изображений.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>Параметры  
 `nImage`  
 Отсчитываемый от нуля индекс образа для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Все элементы, следующие `nImage` теперь перемещаются на одну позицию вниз. Например если списка изображений содержит два элемента, удаление первого элемента приведет оставшиеся элемента: теперь в первую позицию. `nImage`= 0 в первую позицию элемента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>  CImageList::Replace  
 Вызывайте эту функцию, чтобы заменить изображение в список изображений заменяется новым изображением.  
  
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
 Отсчитываемый от нуля индекс образа для замены.  
  
 `pbmImage`  
 Указатель к растровому изображению, содержащий изображение.  
  
 `pbmMask`  
 Указатель к растровому изображению, содержащий маску. Если используется список изображений не маска, этот параметр учитывается.  
  
 `hIcon`  
 Дескриптор значка, который содержит точечный рисунок и маски для нового образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает версию **BOOL** возвращает ненулевое значение, если успешно; в противном случае — 0.  
  
 Возвращает версию `int` возвращает отсчитываемый от нуля индекс изображения, если успешно; в противном случае значение - 1.  
  
### <a name="remarks"></a>Примечания  
 Это функция-член вызывается после вызова метода [SetImageCount](#setimagecount) назначается новый, допустимых изображений заполнитель изображения порядковых номеров.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CImageList::SetImageCount](#setimagecount).  
  
##  <a name="setbkcolor"></a>  CImageList::SetBkColor  
 Вызывайте эту функцию, чтобы задать цвет фона для списка изображений.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>Параметры  
 `cr`  
 Цвет фона для задания. Это может быть `CLR_NONE`. В этом случае изображения отображаются прозрачно с помощью маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущий цвет фона в случае успешного выполнения; в противном случае `CLR_NONE`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage  
 Создает новое изображение перетаскивания путем объединения с текущего изображения перетащите заданного изображения (обычно изображение курсора мыши).  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>Параметры  
 *nDrag*  
 Индекс нового образа для объединения с изображение перетаскивания.  
  
 `ptHotSpot`  
 Положение активной зоны в новый образ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Поскольку перетаскивания функции используют новый образ во время операции перетаскивания, следует использовать Windows [функция ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) функция скрыть курсор мыши после вызова `CImageList::SetDragCursorImage`. В противном случае система может показаться имеют два курсора мыши на время операции перетаскивания.  
  
##  <a name="setimagecount"></a>  CImageList::SetImageCount  
 Вызовите эту функцию-член для сброса число образов в `CImageList` объекта.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>Параметры  
 *uNewCount*  
 Значение, указывающее новое общее количество изображений в списке изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если вызвать эту функцию-член для увеличения числа изображений в списке изображений, затем вызовите [заменить](#replace) для каждого дополнительные изображения назначить новые индексы допустимых изображений. Если не указывать индексы для допустимых изображений, операции рисования, которые создают новые образы будут непредсказуемыми.  
  
 Если уменьшить размер списка изображений с помощью этой функции, усеченных образы будут освобождены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage  
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
 От единицы индекс маски наложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Не более четырех индексы можно добавить в список.  
  
 Маска наложения является прозрачным на другой рисунок изображения. Нарисовать маски наложения на изображение с помощью [CImageList::Draw](#draw) функцию-член с единицы индекс маски наложение, указанный с помощью **INDEXTOOVERLAYMASK** макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>  CImageList::Write  
 Эта функция используется для записи объекта списка изображений в архив.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>Параметры  
 `pArchive`  
 Указатель на `CArchive` объект, в котором будет храниться списка изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListCtrl-класс](../../mfc/reference/clistctrl-class.md)   
 [Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)
