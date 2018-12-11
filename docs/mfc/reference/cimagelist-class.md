---
title: Класс CImageList
ms.date: 11/04/2016
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
ms.openlocfilehash: 5bcf815fce4123ca1014e1679fd810c1ce321be4
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178594"
---
# <a name="cimagelist-class"></a>Класс CImageList

Предоставляет функциональные возможности стандартного элемента управления "список изображений" Windows.

## <a name="syntax"></a>Синтаксис

```
class CImageList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CImageList::CImageList](#cimagelist)|Создает объект `CImageList`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CImageList::Add](#add)|Добавляет изображения или изображения к списку изображений.|
|[CImageList::Attach](#attach)|Присоединяет список изображений для `CImageList` объекта.|
|[CImageList::BeginDrag](#begindrag)|Начинает перетаскивать изображение.|
|[CImageList::Copy](#copy)|Копирует изображение в пределах `CImageList` объекта.|
|[CImageList::Create](#create)|Инициализирует список изображений и присоединяет его к `CImageList` объекта.|
|[CImageList::DeleteImageList](#deleteimagelist)|Удаление списка изображений.|
|[CImageList::DeleteTempMap](#deletetempmap)|Вызывается средой [CWinApp](../../mfc/reference/cwinapp-class.md) обработчиком времени простоя, чтобы удалить какие-либо временные `CImageList` объект, созданный `FromHandle`.|
|[CImageList::Detach](#detach)|Отсоединяет объект списка image `CImageList` объекта и возвращает дескриптор списка изображений.|
|[CImageList::DragEnter](#dragenter)|Блокирует обновления во время операции перетаскивания и отображает изображение, перетащите в указанной позиции.|
|[CImageList::DragLeave](#dragleave)|Разблокирует окна и скрывает изображение перетаскивания, чтобы можно было обновить окно.|
|[CImageList::DragMove](#dragmove)|Перемещает изображения, перетаскиваемый во время операции перетаскивания и вставки.|
|[CImageList::DragShowNolock](#dragshownolock)|Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не блокируя окна.|
|[CImageList::Draw](#draw)|Рисует изображение, перетаскиваемый во время операции перетаскивания и вставки.|
|[CImageList::DrawEx](#drawex)|Рисует элемент списка изображений в заданном контексте устройства. Функция использует указанный стиль рисования и объединяет изображения с указанным цветом.|
|[CImageList::DrawIndirect](#drawindirect)|Рисует изображение в списке изображений.|
|[CImageList::EndDrag](#enddrag)|Завершает операцию перетаскивания.|
|[CImageList::ExtractIcon](#extracticon)|Создает значок на основе изображения и маски, в списке изображений.|
|[CImageList::FromHandle](#fromhandle)|Возвращает указатель на `CImageList` объект для заданного дескриптор к списку изображений. Если объект `CImageList` не прикреплен к дескриптору, создается и прикрепляется временный объект `CImageList`.|
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|Возвращает указатель на `CImageList` объект для заданного дескриптор к списку изображений. Если `CImageList` объект не присоединен к дескриптору, возвращается значение NULL.|
|[CImageList::GetBkColor](#getbkcolor)|Получает текущий цвет фона для списка изображений.|
|[CImageList::GetDragImage](#getdragimage)|Получает список временного изображения, который используется для перетаскивания.|
|[CImageList::GetImageCount](#getimagecount)|Получает число изображений в списке изображений.|
|[CImageList::GetImageInfo](#getimageinfo)|Извлекает сведения об образе.|
|[CImageList::GetSafeHandle](#getsafehandle)|Извлекает `m_hImageList`.|
|[CImageList::Read](#read)|Считывает список изображений из архива.|
|[CImageList::Remove](#remove)|Удаляет изображение из списка изображений.|
|[CImageList::Replace](#replace)|Заменяет изображение в списке изображений новый образ.|
|[CImageList::SetBkColor](#setbkcolor)|Задает цвет фона для списка изображений.|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Создает новый образ перетаскивания.|
|[CImageList::SetImageCount](#setimagecount)|Сбрасывает счетчик изображений в списке изображений.|
|[CImageList::SetOverlayImage](#setoverlayimage)|Добавляет в список изображений для использования в качестве маски наложения отсчитываемый от нуля индекс изображения.|
|[CImageList::Write](#write)|Записывает список изображений в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CImageList::operator HIMAGELIST](#operator_himagelist)|Возвращает HIMAGELIST подключен к `CImageList`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|Дескриптор, содержащий список изображений, присоединенного к этому объекту.|

## <a name="remarks"></a>Примечания

«Список изображений» — это коллекция изображений одного размера, каждый из которых можно ссылаться по его отсчитываемый от нуля индексу. Списки изображений используются эффективно управлять большими наборами значков и точечных рисунков. Все образы в списке изображений содержатся в единый ширину растрового изображения в формате экрана устройства. Список изображений может также включать монохромную битовую карту, содержащий маски, используемый для рисования изображения прозрачно (стиль значка). Приложение Microsoft Win32, программный интерфейс (API) предоставляет функции списка изображений, которые позволяют Рисование изображений, создания и уничтожения списков изображений, добавление и удаление изображений, Замена изображений, объединение изображений и перетащите изображения.

Этот элемент управления (и, следовательно `CImageList` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.

Дополнительные сведения об использовании `CImageList`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CImageList](../../mfc/using-cimagelist.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="add"></a>  CImageList::Add

Вызывайте эту функцию, чтобы добавить один или несколько образов или значка к списку изображений.

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

*pbmImage*<br/>
Указатель на растровое изображение, содержащее изображения или изображения. Число образов, будет определена на ширину точечного рисунка.

*pbmMask*<br/>
Указатель на растровое изображение, содержащий маску. Если маска не используется в списке изображений, этот параметр учитывается.

*crMask*<br/>
Цвет, используемый для создания маски. Каждый пиксель для этого цвета в данной битовой карте замещены черным фоном и соответствующий бит в битовой маске присваивается одно.

*hIcon*<br/>
Дескриптор значка, содержащий растровое изображение и маску для нового образа.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс первого новый образ, если выполнение прошло успешно; в противном случае - 1.

### <a name="remarks"></a>Примечания

Вы несете ответственность за освобождение дескриптор значка, когда вы закончите с ним.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

##  <a name="attach"></a>  CImageList::Attach

Вызывайте эту функцию для присоединения списка изображений для `CImageList` объекта.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Дескриптор объекта списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если вложение прошла успешно; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

##  <a name="begindrag"></a>  CImageList::BeginDrag

Вызывайте эту функцию, чтобы начать перетаскивать изображение.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для перетаскивания.

*ptHotSpot*<br/>
Координаты начальной позиции перетаскивания (как правило, позиция курсора). Координаты указываются относительно верхнего левого угла изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция создает список временного изображения, который используется для перетаскивания. Изображение объединяет указанное изображение и его маской с текущий курсор. В ответ на сообщение WM_MOUSEMOVE, можно переместить изображение перетаскивания с помощью `DragMove` функция-член. Чтобы завершить операцию перетаскивания, можно использовать `EndDrag` функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

##  <a name="cimagelist"></a>  CImageList::CImageList

Создает объект `CImageList`.

```
CImageList();
```

##  <a name="copy"></a>  CImageList::Copy

Эта функция-член реализует поведение функции Win32 [ImageList_Copy](/windows/desktop/api/commctrl/nf-commctrl-imagelist_copy), как описано в пакете Windows SDK.

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

*iDst*<br/>
Отсчитываемый от нуля индекс изображения для использования в качестве целевой для операции копирования.

*Код*<br/>
Отсчитываемый от нуля индекс изображения, используемого в качестве источника операции копирования.

*uFlags*<br/>
Значение флага бит, указывающий тип операции копирования должна быть выполнена. Этот параметр может принимать одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|ILCF_MOVE|Исходный образ копируется индекс конечного изображения. Эта операция приводит к несколько экземпляров данного изображения. ILCF_MOVE используется по умолчанию.|
|ILCF_SWAP|Источник и назначение изображений обмениваются позиции в списке изображений.|

*pSrc*<br/>
Указатель на `CImageList` объект, который является целевым объектом операции копирования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

##  <a name="create"></a>  CImageList::Create

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

*cx*<br/>
Размеры каждого изображения в пикселях.

*CY*<br/>
Размеры каждого изображения в пикселях.

*nFlags*<br/>
Указывает тип списка изображений для создания. Этот параметр может быть сочетанием следующих значений, но он может включать только один из `ILC_COLOR` значения.

|Значение|Значение|
|-----------|-------------|
|ILC_COLOR|Используйте поведение по умолчанию, если заданы другие ILC_COLOR * флаги. Как правило значение по умолчанию является ILC_COLOR4; но для более старые драйверы дисплея, по умолчанию ILC_COLORDDB.|
|ILC_COLOR4|Раздел 4-разрядное (16 цветов) аппаратно независимый точечный рисунок (DIB) как битовую карту можно используйте для списка изображений.|
|ILC_COLOR8|Используйте раздел DIB 8-разрядное. Цвета, используемые для таблицы цветов, цветовой полутоновой палитры.|
|ILC_COLOR16|Использование 16-разрядное (32 / 64k цвет) раздел DIB.|
|ILC_COLOR24|Используйте 24-разрядный раздел DIB.|
|ILC_COLOR32|Используйте раздел изображение DIB Размером 32-разрядной.|
|ILC_COLORDDB|Используйте аппаратно зависимая Битовая карта.|
|ILC_MASK|Использует маску. Список изображений содержит два точечных рисунков, один из которых является монохромную битовую карту, используемой в качестве маски. Если это значение не указан, список изображений содержит единственный точечного рисунка. См. в разделе [Рисование изображений из списка изображений](../../mfc/drawing-images-from-an-image-list.md) Дополнительные сведения об образах маской.|

*nInitial*<br/>
Число образов, которые изначально содержит в списке изображений.

*nGrow*<br/>
Число образов, на которое может возрастать список изображений, при необходимости изменить размер списка, чтобы освободить место для новых образов системы. Этот параметр представляет количество новых образов, которые может содержать список изображение с измененным размером.

*nBitmapID*<br/>
Идентификаторы ресурсов растрового изображения должны быть сопоставлены списка изображений.

*crMask*<br/>
Цвет, используемый для создания маски. Каждый пиксель для этого цвета в указанном точечном рисунке замещены черным фоном, а соответствующий бит в битовой маске присваивается одно.

*lpszBitmapID*<br/>
Строка, содержащая идентификаторы изображений ресурсов.

*imageList1*<br/>
Ссылка на объект `CImageList`.

*nImage1*<br/>
Индекс первого существующий образ.

*imagelist2*<br/>
Ссылка на объект `CImageList`.

*nImage2*<br/>
Индекс второго существующий образ.

*DX*<br/>
Смещение для оси х второе изображение в связи с первого изображения в пикселях.

*dy*<br/>
Смещение ось y второе изображение в связи с первого изображения в пикселях.

*pImageList*<br/>
Указатель на объект `CImageList` .

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

При создании `CImageList` в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает список изображений и присоединяет его к `CImageList` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList

Вызывайте эту функцию для удаления списка изображений.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap

Автоматически вызывается `CWinApp` обработчиком времени простоя, `DeleteTempMap` удаляет все временные `CImageList` объекты, создаваемые [FromHandle](#fromhandle), но не уничтожает все дескрипторы ( `hImageList`) временно связанный с помощью `ImageList` объектов.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

##  <a name="detach"></a>  CImageList::Detach

Вызывайте эту функцию для отсоединения объект списка image `CImageList` объекта.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор объекта списка изображений.

### <a name="remarks"></a>Примечания

Эта функция возвращает дескриптор объекта списка изображений.

### <a name="example"></a>Пример

  См. в примере [CImageList::Attach](#attach).

##  <a name="dragenter"></a>  CImageList::DragEnter

Во время операции перетаскивания, блокировки обновления с окном, заданным параметром *pWndLock* и отображает изображение перетаскивания в позиции, заданной параметром *точки*.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWndLock*<br/>
Указатель на окно, которому принадлежит изображение перетаскивания.

*point*<br/>
Позиция, в котором будет отображаться изображение перетаскивания. Координаты указываются относительно верхнего левого угла окна (не клиентской области).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Координаты указываются относительно верхнего левого угла окна, чтобы компенсировать ширину окна элементы, такие как границу, заголовок и меню, при указании координаты.

Если *pWndLock* имеет значение NULL, эта функция выводит изображение в контексте отображения, связанный с окном рабочего стола и координаты указываются относительно верхнего левого угла экрана.

Эта функция блокирует все другие обновления для заданного окна во время операции перетаскивания. Если необходимо выполнить любое изображение во время операции перетаскивания, например выделение целевого объекта для операции перетаскивания и вставки, можно временно скрыть перетаскиваемого изображения с помощью [CImageList::DragLeave](#dragleave) функции.

### <a name="example"></a>Пример

  См. в примере [CImageList::BeginDrag](#begindrag).

##  <a name="dragleave"></a>  CImageList::DragLeave

Разблокирует окном, заданным параметром *pWndLock* и скрывает изображение перетаскивания, позволяя обновить окно.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Параметры

*pWndLock*<br/>
Указатель на окно, которому принадлежит изображение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CImageList::EndDrag](#enddrag).

##  <a name="dragmove"></a>  CImageList::DragMove

Вызывайте эту функцию, чтобы переместить изображение перетаскиваемый во время операции перетаскивания и вставки.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Новое положение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Как правило, эта функция вызывается в ответ на сообщение WM_MOUSEMOVE. Чтобы начать операцию перетаскивания, используйте `BeginDrag` функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

##  <a name="dragshownolock"></a>  CImageList::DragShowNolock

Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не блокируя окна.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, является ли изображение перетаскивания для отображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

[CImageList::DragEnter](#dragenter) функция блокирует все обновления в окно во время операции перетаскивания. Тем не менее, эта функция не блокирует окна.

##  <a name="draw"></a>  CImageList::Draw

Эта функция используется для рисования изображения, перетаскиваемый во время операции перетаскивания и вставки.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель контекста устройства назначения.

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для рисования.

*pt*<br/>
Место, в котором для рисования в заданном контексте устройства.

*nStyle*<br/>
Флаг, указывающий стиль рисования. Это может быть один или несколько из следующих значений:

|Значение|Значение|
|-----------|-------------|
|ILD_BLEND25 ILD_FOCUS|Рисует изображение наложения 25 процентов с системным цветом выделения. Если список изображений не содержит маску, это значение игнорируется.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Рисует изображение наложения 50 процентов с системным цветом выделения. Если список изображений не содержит маску, это значение игнорируется.|
|ILD_MASK|Рисует маски.|
|ILD_NORMAL|Рисует изображение, используя цвет фона для списка изображений. Если цвет фона имеет значение CLR_NONE, рисуется изображение явным образом с помощью маски.|
|ILD_TRANSPARENT|Рисует изображение явным образом с помощью маски, независимо от того, цвет фона.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CImageList::SetOverlayImage](#setoverlayimage).

##  <a name="drawex"></a>  CImageList::DrawEx

Рисует элемент списка изображений в заданном контексте устройства.

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

*pDC*<br/>
Указатель контекста устройства назначения.

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для рисования.

*pt*<br/>
Место, в котором для рисования в заданном контексте устройства.

*sz*<br/>
Размер части изображения для рисования, относительно верхнего левого угла изображения. См. в разделе *dx* и *dy* в [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) в пакете Windows SDK.

*clrBk*<br/>
Цвет фона изображения. См. в разделе *rgbBk* в [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) в пакете Windows SDK.

*clrFg*<br/>
Основной цвет изображения. См. в разделе *rgbFg* в [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) в пакете Windows SDK.

*nStyle*<br/>
Флаг, указывающий стиль рисования. См. в разделе *fStyle* в [ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) в пакете Windows SDK.

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

*pimldp*<br/>
Указатель на [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) структуру, содержащую сведения об операции рисования.

*pDC*<br/>
Указатель на контексте устройства назначения. Необходимо удалить это [CDC](../../mfc/reference/cdc-class.md) объекта, когда вы закончите с ним.

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для отрисовки.

*pt*<br/>
Объект [ТОЧКИ](https://msdn.microsoft.com/library/windows/desktop/dd162805) структура, содержащая координаты x и y-где рисуется изображение.

*sz*<br/>
Объект [размер](/windows/desktop/api/windef/ns-windef-tagsize) структура, указывающая размер изображения для отрисовки.

*ptOrigin*<br/>
Объект [ТОЧКИ](https://msdn.microsoft.com/library/windows/desktop/dd162805) структура, содержащая координаты x и y-указание верхнего левого угла операции рисования по отношению к само изображение. Изображения, которые расположены слева координаты x и более поздних версий координату по оси y не пикселов.

*fStyle*<br/>
Флаг, указывающий стиль рисования и, возможно, изображение для наложения. В разделе "Примечания" сведения на изображение для наложения. Реализация по умолчанию MFC, ILD_NORMAL, Рисует изображение, используя цвет фона для списка изображений. Если цвет фона имеет значение CLR_NONE, рисуется изображение явным образом с помощью маски.

В разделе описаны другие возможные стили *fStyle* членом [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) структуры.

*dwRop*<br/>
Значение, указывающее код растровая операция. Эти коды определяют, как будут объединены данные о цвете для исходного прямоугольника с помощью данных о цвете для прямоугольника назначения для достижения с окончательным цветом. Реализация по умолчанию MFC, SRCCOPY, копирует исходного прямоугольника непосредственно целевого прямоугольника. Этот параметр учитывается, если *fStyle* не содержит флаг ILD_ROP.

Другие возможные значения описаны в разделе *dwRop* членом [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) структуры.

*rgbBack*<br/>
Цвет фона изображения по умолчанию CLR_DEFAULT. Этот параметр может иметь значение определяется приложением RGB или одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|Цвет фона по умолчанию. Цветом фона списка изображение рисуется изображение.|
|CLR_NONE|Нет цвета фона. Изображение является прозрачным.|

*rgbFore*<br/>
Цвет переднего плана изображения по умолчанию CLR_DEFAULT. Этот параметр может иметь значение определяется приложением RGB или одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|По умолчанию цвет переднего плана. При этом рисуется изображение, используя системный цвет выделения цветом переднего плана.|
|CLR_NONE|Нет цвета blend. Изображение смешивается с цвет в контексте устройства назначения.|

Этот параметр используется только в том случае, если *fStyle* включает флаг ILD_BLEND25 или ILD_BLEND50.

*fState*<br/>
Флаг, указывающий состояние рисования. Этот элемент может содержать один или несколько флагов состояния списка изображений.

*Frame*<br/>
Влияет на поведение эффекты saturate и альфа смешения.

При использовании с ILS_SATURATE, этот элемент содержит значение, которое добавляется для каждого компонента цвета RGB триплета для каждого пикселя в значок.

При использовании с ILS_APLHA, этот элемент содержит значение альфа-канала. Это значение может быть от 0 до 255, 0 остается полностью прозрачным и 255, полностью непрозрачными.

*crEffect*<br/>
Объект [COLORREF](/windows/desktop/gdi/colorref) значение, используемое для свечения и теневых эффектов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно рисуется изображение; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте первую версию, если вы хотите заполнить структуру Win32 самостоятельно. Если вы хотите воспользоваться преимуществами один или несколько аргументов по умолчанию MFC или избежать управления структурой, используйте второй версии.

Наложение изображения — это изображение, рисуется поверх основного образа, указанные в этой функцией-членом, *изображение* параметра. Рисование с помощью маски наложения [рисования](#draw) функцию-член с отсчитываемый от единицы индекс маски наложения, указанные с помощью [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) макрос.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

##  <a name="enddrag"></a>  CImageList::EndDrag

Вызывайте эту функцию, чтобы завершить операцию перетаскивания.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Примечания

Чтобы начать операцию перетаскивания, используйте `BeginDrag` функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

##  <a name="extracticon"></a>  CImageList::ExtractIcon

Вызывайте эту функцию для создания значка на основе образа и его связанных маски, в списке изображений.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Параметры

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор значка, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Этот метод использует поведение [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) макрос для значка. Ссылаться на [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon) макрос Дополнительные сведения о создании значок и очистки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

##  <a name="fromhandle"></a>  CImageList::FromHandle

Возвращает указатель на `CImageList` объект для заданного дескриптор к списку изображений.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Задает список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CImageList` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CImageList` еще не присоединен к дескриптору, временный `CImageList` созданный и присоединенный объект. Этот временный `CImageList` объект является допустимым, только пока очередном приложение время простоя в свой цикл событий, после чего все временные объекты удаляются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent

Возвращает указатель на `CImageList` объект для заданного дескриптор к списку изображений.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Задает список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CImageList` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CImageList` объект не присоединен к дескриптору, возвращается значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

##  <a name="getbkcolor"></a>  CImageList::GetBkColor

Вызывайте эту функцию, чтобы получить текущий цвет фона для списка изображений.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB `CImageList` цвет фона объекта.

### <a name="example"></a>Пример

  См. в примере [CImageList::SetBkColor](#setbkcolor).

##  <a name="getdragimage"></a>  CImageList::GetDragImage

Получает список временного изображения, который используется для перетаскивания.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Параметры

*lpPoint*<br/>
Адрес [ТОЧКИ](https://msdn.microsoft.com/library/windows/desktop/dd162805) структуры, который получает текущий перетащите позиции.

*lpPointHotSpot*<br/>
Адрес `POINT` структуру, которая получает смещение изображение перетаскивания относительно положения перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения указатель на образе временный список, используемый для перетаскивания; в противном случае — значение NULL.

##  <a name="getimagecount"></a>  CImageList::GetImageCount

Вызывайте эту функцию для извлечения нескольких изображений в списке изображений.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число изображений.

### <a name="example"></a>Пример

  См. в примере [CImageList::ExtractIcon](#extracticon).

##  <a name="getimageinfo"></a>  CImageList::GetImageInfo

Вызывайте эту функцию для получения сведений об образе.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Параметры

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения.

*pImageInfo*<br/>
Указатель на [IMAGEINFO](/windows/desktop/api/commctrl/ns-commctrl-_imageinfo) структуры, получающий сведения об образе. Сведения в этой структуре можно использовать для прямого управления для изображения, точечные рисунки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`IMAGEINFO` Структура содержит сведения об изображении в списке изображений.

##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle

Вызывайте эту функцию для получения `m_hImageList` элемент данных.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор к списку прикрепленного изображения; в противном случае — значение NULL, если объект не присоединен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

##  <a name="m_himagelist"></a>  CImageList::m_hImageList

Дескриптор списка изображений, присоединенного к этому объекту.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Примечания

`m_hImageList` Данные-член — это открытая переменная типа HIMAGELIST.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST

Этот оператор используется для получения присоединенного дескриптор `CImageList` объекта.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения дескриптор списка изображений, представленных `CImageList` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот оператор — оператор приведения, который поддерживает непосредственное использование объекта HIMAGELIST.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

##  <a name="read"></a>  CImageList::Read

Вызывайте эту функцию для списка изображений для чтения из архива.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*pArchive*<br/>
Указатель на `CArchive` объект, из которого будет продолжаться чтение списка изображений.

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

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения, которое требуется удалить.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Все элементы, следующие *изображение* теперь перейти на одну позицию вниз. Например если список изображений содержит два элемента, удаление первого элемента приведет к оставшиеся элемент теперь на первом месте. *Изображение*= 0 в первой позиции элемента.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

##  <a name="replace"></a>  CImageList::Replace

Вызывайте эту функцию, чтобы заменить изображение в списке изображений новый образ.

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

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для замены.

*pbmImage*<br/>
Указатель на растровое изображение, содержащий изображение.

*pbmMask*<br/>
Указатель на растровое изображение, содержащий маску. Если маска не используется в списке изображений, этот параметр учитывается.

*hIcon*<br/>
Дескриптор для значка, который содержит растровое изображение и маску для нового образа.

### <a name="return-value"></a>Возвращаемое значение

Версия, возвращая BOOL возвращает ненулевое значение, если выполнение прошло успешно; в противном случае 0.

Возвращает версию **int** возвращает отсчитываемый от нуля индекс изображения в том случае, если успешно; в противном случае — значение - 1.

### <a name="remarks"></a>Примечания

Это функция-член вызывается после вызова метода [SetImageCount](#setimagecount) для назначения новому, допустимых изображений заполнитель изображения порядковых номеров.

### <a name="example"></a>Пример

  См. в примере [CImageList::SetImageCount](#setimagecount).

##  <a name="setbkcolor"></a>  CImageList::SetBkColor

Вызывайте эту функцию, чтобы задать цвет фона для списка изображений.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*CR*<br/>
Цвет фона для задания. Это может быть CLR_NONE. В этом случае изображения отображаются прозрачно с помощью маски.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет фона, если выполнение прошло успешно; в противном случае CLR_NONE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage

Создает новый образ перетаскивания путем объединения с текущего изображения перетащите заданного изображения (обычно изображения курсора мыши).

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*nDrag*<br/>
Индекс нового образа необходимо использовать вместе с изображение перетаскивания.

*ptHotSpot*<br/>
Положение активной зоны в новый образ.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Так как функции перетаскивания используют новый образ во время операции перетаскивания, следует использовать Windows [функция ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor) функции, чтобы скрыть курсор мыши после вызова метода `CImageList::SetDragCursorImage`. В противном случае система может показаться имеют два курсора мыши в течение операции перетаскивания.

##  <a name="setimagecount"></a>  CImageList::SetImageCount

Вызовите эту функцию-член для сброса количеству изображений в `CImageList` объекта.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Параметры

*uNewCount*<br/>
Значение, указывающее новое общее количество изображений в списке изображений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Если вы вызываете эту функцию-член для увеличения числа изображений в списке изображений, затем вызвать [замените](#replace) для каждого дополнительные изображения для назначения новых индексов допустимых изображений. Если не указывать индексы для допустимых изображений, операции рисования, которые создают новые образы будут непредсказуемыми.

Если уменьшить размер списка изображений с помощью этой функции, усеченное образы будут освобождены.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage

Вызывайте эту функцию, добавляемый в список изображений для использования в качестве маски наложения отсчитываемый от нуля индекс изображения.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Параметры

*Изображение*<br/>
Отсчитываемый от нуля индекс изображения для использования в качестве маски наложения.

*nOverlay*<br/>
Отсчитываемый от единицы индекс маски наложения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Не более четырех индексов можно добавить в список.

Маски наложения — это образ, прозрачным через другое изображение. Отображение маски наложения поверх изображения с помощью [CImageList::Draw](#draw) функцию-член с отсчитываемый от единицы индекс маски наложения, указанный с помощью макроса INDEXTOOVERLAYMASK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

##  <a name="write"></a>  CImageList::Write

Вызывайте эту функцию для записи объекта списка изображений в архив.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*pArchive*<br/>
Указатель на `CArchive` объект, в котором будет храниться списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)
