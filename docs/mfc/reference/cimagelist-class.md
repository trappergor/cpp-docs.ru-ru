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
ms.openlocfilehash: 17cd2a94cb397e59e4622aea8ed7bb6fbe1eee43
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752686"
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
|[CImageList:CImageList](#cimagelist)|Формирует объект `CImageList`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CImageList::Добавить](#add)|Добавляет изображение или изображения в список изображений.|
|[CImageList::Прикрепите](#attach)|Прикрепляет список `CImageList` изображений к объекту.|
|[CImageList::BeginDrag](#begindrag)|Начинает перетаскивание изображения.|
|[CImageList::Copy](#copy)|Копирует изображение внутри `CImageList` объекта.|
|[CImageList::Создание](#create)|Инициализирует список изображений `CImageList` и прикрепляет его к объекту.|
|[CImageList::DeleteImageList](#deleteimagelist)|Удаляет список изображений.|
|[CImageList::DeleteTempMap](#deletetempmap)|Вызывается [CWinApp](../../mfc/reference/cwinapp-class.md) простоя обработчик `CImageList` удалить любой временный объект, созданный `FromHandle`.|
|[CImageList: :Detach](#detach)|Открепит объект списка изображений `CImageList` с объекта и возвращает ручку в список изображений.|
|[CImageList::DragEnter](#dragenter)|Блокировки обновляются во время операции перетаскивания и отображают изображение перетаскивания в заданном положении.|
|[CImageList::DragLeave](#dragleave)|Открывает окно и скрывает изображение перетаскивания, чтобы окно можно было обновить.|
|[CImageList::DragMove](#dragmove)|Перемещает изображение, которое перетаскивается во время операции перетаскивания.|
|[CImageList::DragShowNolock](#dragshownolock)|Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не запирая окно.|
|[CImageList: :Draw](#draw)|Рисует изображение, которое перетаскивается во время операции перетаскивания.|
|[CImageList::DrawEx](#drawex)|Рисует элемент списка изображений в указанном контексте устройства. Функция использует указанный стиль рисования и смешивает изображение с указанным цветом.|
|[CImagelist::DсырьеВая](#drawindirect)|Рисует изображение из списка изображений.|
|[CImageList::EndDrag](#enddrag)|Завершает операцию перетаскивания.|
|[CImageList:ExtractIcon](#extracticon)|Создает значок на основе изображения и маски в списке изображений.|
|[CImageList::FromHandle](#fromhandle)|Возвращает указатель объекту `CImageList` при вечке ручки в список изображений. Если объект `CImageList` не прикреплен к дескриптору, создается и прикрепляется временный объект `CImageList`.|
|[CImageList::FromTheПостоянный](#fromhandlepermanent)|Возвращает указатель объекту `CImageList` при вечке ручки в список изображений. Если `CImageList` объект не прикреплен к ручке, NULL возвращается.|
|[CImageList::GetBkColor](#getbkcolor)|Извлекает текущий фоновый цвет для списка изображений.|
|[CImageList:GetDragImage](#getdragimage)|Получает временный список изображений, который используется для перетаскивания.|
|[CImageList::GetImageCount](#getimagecount)|Извлекает количество изображений в списке изображений.|
|[CImageList::GetImageInfo](#getimageinfo)|Извлекает информацию об изображении.|
|[CImageList:GetSafeHandle](#getsafehandle)|Получает `m_hImageList`.|
|[CImageList::Читать](#read)|Читает список изображений из архива.|
|[CImageList::Удалить](#remove)|Удаляет изображение из списка изображений.|
|[CImageList::Заменить](#replace)|Заменяет изображение в списке изображений новым изображением.|
|[CImageList:SetBkColor](#setbkcolor)|Устанавливает цвет фона для списка изображений.|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|Создает новое изображение сопротивления.|
|[CImageList:SetImageCount](#setimagecount)|Сбрасывает количество изображений в списке изображений.|
|[CImageList:SetOverlayImage](#setoverlayimage)|Добавляет нулевой индекс изображения в список изображений, которые будут использоваться в качестве накладных масок.|
|[CImageList::Запись](#write)|Заражает список изображений в архив.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CImageList:Оператор HIMAGELIST](#operator_himagelist)|Возвращает HIMAGELIST прилагается `CImageList`к .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|Ручка, содержащая список изображений, прикрепленный к этому объекту.|

## <a name="remarks"></a>Remarks

"Список изображений" представляет собой набор изображений одинакового размера, на каждое из которых можно ссылаться по индексу с нулевым уровнем. Списки изображений используются для эффективного управления большими наборами иконок или бит-карт. Все изображения в списке изображений содержатся в единой широкой битовой карте в формате экранного устройства. Список изображений может также включать монохромную бит-карту, которая содержит маски, используемые для прозрачного рисования изображений (стиль иконы). Интерфейс программирования приложений Microsoft Win32 (API) предоставляет функции списка изображений, которые позволяют рисовать изображения, создавать и уничтожать списки изображений, добавлять и удалять изображения, заменять изображения, объединять изображения и перетаскивать изображения.

Этот элемент управления `CImageList` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Для получения дополнительной `CImageList`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CImageList](../../mfc/using-cimagelist.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cimagelistadd"></a><a name="add"></a>CImageList::Добавить

Вызовите эту функцию, чтобы добавить одно или несколько изображений или значок в список изображений.

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
Указатель на битную карту, содержащую изображение или изображения. Количество изображений выводимый из ширины битной карты.

*pbmMask*<br/>
Указатель на бит-карту, содержащую маску. Если в списке изображений не используется маска, этот параметр игнорируется.

*crMask*<br/>
Цвет, используемый для создания маски. Каждый пиксель этого цвета в данной битной карте изменяется на черный, а соответствующий бит в маске устанавливается на один.

*hIcon*<br/>
Ручка значка, содержащая бит-карту и маску для нового изображения.

### <a name="return-value"></a>Возвращаемое значение

Нулевой индекс первого нового изображения в случае успеха; в противном случае - 1.

### <a name="remarks"></a>Remarks

Вы несете ответственность за освобождение значок ручкой, когда вы сделали с ним.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>CImageList::Прикрепите

Вызовите эту функцию, `CImageList` чтобы прикрепить список изображений к объекту.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Ручка к объекту списка изображений.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вложение было успешным; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>CImageList::BeginDrag

Вызовите эту функцию, чтобы начать перетаскивание изображения.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения для перетаскивания.

*ptHotSpot*<br/>
Координаты исходного положения сопротивления (обычно, положение курсора). Координаты относительно верхнего левого угла изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция создает временный список изображений, который используется для перетаскивания. Изображение сочетает в себе указанное изображение и его маску с текущим курсором. В ответ на последующие сообщения WM_MOUSEMOVE можно переместить `DragMove` изображение перетаскивания с помощью функции члена. Чтобы закончить операцию перетаскивания, можно использовать функцию `EndDrag` члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>CImageList:CImageList

Формирует объект `CImageList`.

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>CImageList::Copy

Эта функция члена реализует поведение функции Win32 [ImageList_Copy,](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy)как описано в SDK Windows.

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
Индекс изображения с нулевым уровнем, который будет использоваться в качестве пункта назначения операции копирования.

*iSrc*<br/>
Индекс изображения с нулевым уровнем, который будет использоваться в качестве источника операции копирования.

*uФлаги*<br/>
Значение битового флага, описавававававаемый тип операции копирования. Этот параметр может быть одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|ILCF_MOVE|Исходное изображение скопировано в индекс изображения назначения. Эта операция приводит к нескольким экземплярам данного изображения. ILCF_MOVE по умолчанию.|
|ILCF_SWAP|Исходные изображения обмениваются позициями в списке изображений.|

*Psrc*<br/>
Указатель на `CImageList` объект, который является целью операции копирования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>CImageList::Создание

Инициализирует список изображений и прикрепляет его к объекту [CImageList.](../../mfc/reference/cimagelist-class.md)

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

*Cx*<br/>
Размеры каждого изображения, в пикселях.

*Cy*<br/>
Размеры каждого изображения, в пикселях.

*nФлаги*<br/>
Определяет тип списка изображений для создания. Этот параметр может быть комбинацией следующих значений, но `ILC_COLOR` он может включать только одно из значений.

|Значение|Значение|
|-----------|-------------|
|ILC_COLOR|Используйте поведение по умолчанию, если ни один из других ILC_COLOR флагов не указан. Как правило, по умолчанию ILC_COLOR4; но для старых драйверов отображения по умолчанию ILC_COLORDDB.|
|ILC_COLOR4|Используйте 4-битный (16 цвет) устройство-независимый bitmap (DIB) раздел в качестве бит-карты для списка изображений.|
|ILC_COLOR8|Используйте 8-битный раздел DIB. Цвета, используемые для цветовой таблицы, являются теми же цветами, что и палитры полутона.|
|ILC_COLOR16|Используйте 16-битный (32/64k цвет) DIB раздел.|
|ILC_COLOR24|Используйте 24-разрядный раздел DIB.|
|ILC_COLOR32|Используйте 32-битный раздел DIB.|
|ILC_COLORDDB|Используйте зависимую от устройства бит-карту.|
|ILC_MASK|Использует маску. Список изображений содержит две бит-карты, одна из которых представляет собой монохромную бит-карту, используемую в качестве маски. Если это значение не включено, список изображений содержит только одну битовую карту. Для получения дополнительной информации о замаскированных изображениях смотрите [изображения из списка изображений.](../../mfc/drawing-images-from-an-image-list.md)|

*nПервоначальный*<br/>
Количество изображений, которые первоначально содержит список изображений.

*nGrow*<br/>
Количество изображений, с помощью которых список изображений может расти, когда система должна изменить размер списка, чтобы освободить место для новых изображений. Этот параметр представляет количество новых изображений, которые может содержать список изображений с переразмерным размером.

*nBitmapID*<br/>
Идобыты ресурсов битной карты, связанные со списком изображений.

*crMask*<br/>
Цвет используется для создания маски. Каждый пиксель этого цвета в указанной битовой карте изменяется на черный, а соответствующий бит в маске устанавливается на один.

*lpszBitmapID*<br/>
Строка, содержащая идолресурсы ресурсов изображений.

*imagelist1*<br/>
Ссылка на объект `CImageList`.

*nImage1*<br/>
Индекс первого существующего изображения.

*imagelist2*<br/>
Ссылка на объект `CImageList`.

*nImage2*<br/>
Индекс второго существующего изображения.

*dx*<br/>
Смещение x-оси второго изображения в связи с первым изображением, в пикселях.

*Dy*<br/>
Смещение y-оси второго изображения в связи с первым изображением, в пикселях.

*pImageList*<br/>
Указатель на объект `CImageList`.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы строите `CImageList` в два этапа. Сначала позвоните в конструктор, `Create`а затем позвоните, который создает `CImageList` список изображений и прикрепляет его к объекту.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>CImageList::DeleteImageList

Вызовите эту функцию, чтобы удалить список изображений.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>CImageList::DeleteTempMap

Вызывается автоматически `CWinApp` обработчиком `DeleteTempMap` простоя, `CImageList` удаляет любые временные объекты, созданные [FromHandle,](#fromhandle)но не уничтожает никаких ручек (), `hImageList`временно связанных с `ImageList` объектами.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>CImageList: :Detach

Вызовите эту функцию, чтобы отделить `CImageList` объект списка изображений от объекта.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к объекту списка изображений.

### <a name="remarks"></a>Remarks

Эта функция возвращает ручку объекту списка изображений.

### <a name="example"></a>Пример

  Смотрите пример [для CImageList::Прикрепите](#attach).

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>CImageList::DragEnter

Во время операции перетаскивания блокирует обновление окна, указанного *pWndLock,* и отображает изображение перетаскивания в положении, указанном *по пункту.*

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*pWndLock*<br/>
Указатель на окно, которое владеет изображением перетаскивания.

*Точки*<br/>
Позиция, на которой отображается изображение перетаскивания. Координаты относительно верхнего левого угла окна (не область клиента).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Координаты относительно верхнего левого угла окна, поэтому при определении координат необходимо компенсировать ширину оконных элементов, таких как граница, заголовок и панель меню.

Если *pWndLock* является NULL, эта функция рисует изображение в контексте дисплея, связанном с окном рабочего стола, и координаты относительно верхнего левого угла экрана.

Эта функция блокирует все другие обновления данного окна во время операции перетаскивания. Если вам нужно сделать какой-либо рисунок во время операции перетаскивания, например, выделение цели операции перетаскивания, можно временно скрыть перетасканувное изображение с помощью функции [CImageList::DragLeave.](#dragleave)

### <a name="example"></a>Пример

  Смотрите пример [CImageList::BeginDrag](#begindrag).

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>CImageList::DragLeave

Открывает окно, указанное *pWndLock,* и скрывает изображение перетаскивания, позволяя обновлять окно.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>Параметры

*pWndLock*<br/>
Указатель на окно, которое владеет изображением перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [CImageList::EndDrag](#enddrag).

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>CImageList::DragMove

Вызовите эту функцию для перемещения изображения, которое перетаскивается во время операции перетаскивания.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Новая позиция сопротивления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается в ответ на WM_MOUSEMOVE сообщение. Чтобы начать операцию перетаскивания, используйте функцию `BeginDrag` члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>CImageList::DragShowNolock

Показывает или скрывает изображение перетаскивания во время операции перетаскивания, не запирая окно.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Определяет, будет ли отображаться изображение перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Функция [CImageList::DragEnter](#dragenter) блокирует все обновления в окне во время операции перетаскивания. Эта функция, однако, не блокирует окно.

## <a name="cimagelistdraw"></a><a name="draw"></a>CImageList: :Draw

Вызовите эту функцию, чтобы нарисовать изображение, которое перетаскивается во время операции перетаскивания.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства назначения.

*nИзображение*<br/>
Нулевой индекс изображения для рисования.

*пт*<br/>
Местонахождение, в котором можно рисовать в контексте указанного устройства.

*nStyle*<br/>
Пометить стиль чертежа. Это может быть одно или несколько из этих значений:

|Значение|Значение|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|Рисует изображение, смешивая 25 процентов с цветом выделения системы. Это значение не влияет, если список изображений не содержит маску.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|Рисует изображение, смешивая 50 процентов с цветом выделения системы. Это значение не влияет, если список изображений не содержит маску.|
|ILD_MASK|Рисует маску.|
|ILD_NORMAL|Рисует изображение с помощью фонового цвета для списка изображений. Если цвет фона является CLR_NONE значением, изображение нарисовано прозрачно с помощью маски.|
|ILD_TRANSPARENT|Рисует изображение прозрачно с помощью маски, независимо от цвета фона.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  Смотрите пример [Для CImageList::SetOverlayImage](#setoverlayimage).

## <a name="cimagelistdrawex"></a><a name="drawex"></a>CImageList::DrawEx

Рисует элемент списка изображений в указанном контексте устройства.

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
Указатель на контекст устройства назначения.

*nИзображение*<br/>
Нулевой индекс изображения для рисования.

*пт*<br/>
Местонахождение, в котором можно рисовать в контексте указанного устройства.

*Sz*<br/>
Размер части изображения для рисования относительно верхнего левого угла изображения. Смотрите *dx* и *dy* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*clrBk*<br/>
Фоновый цвет изображения. Смотрите *rgbBk* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*clrFg*<br/>
Цвет переднего плана изображения. Смотрите *rgbFg* в [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в Windows SDK.

*nStyle*<br/>
Пометить стиль чертежа. Смотрите *в* [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Функция использует указанный стиль рисования и смешивает изображение с указанным цветом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>CImagelist::DсырьеВая

Вызовите эту функцию участника, чтобы нарисовать изображение из списка изображений.

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
Указатель на структуру [IMAGELISTDRAWPARAMS,](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) содержащую информацию об операции рисования.

*pDC*<br/>
Указатель на контекст устройства назначения. Вы должны удалить этот объект [CDC,](../../mfc/reference/cdc-class.md) когда вы закончите с ним.

*nИзображение*<br/>
Нулевой индекс изображения, который будет нарисован.

*пт*<br/>
Структура [POINT,](/windows/win32/api/windef/ns-windef-point) содержащая x- и y-координаты, где будет нарисовано изображение.

*Sz*<br/>
Структура [СИЗЕ,](/windows/win32/api/windef/ns-windef-size) указывающая размер нарисованного изображения.

*ptOrigin*<br/>
Структура [POINT,](/windows/win32/api/windef/ns-windef-point) содержащая x- и y-координаты, указывающие верхний левый угол операции рисования по отношению к самому изображению. Пиксели изображения, которые находятся слева от X-координации и выше y-координации, не нарисованы.

*fСтиль*<br/>
Пометить, указав стиль чертежа и, по желанию, изображение наложения. Смотрите раздел Замечания для получения информации о изображении наложения. Реализация MFC по умолчанию, ILD_NORMAL, рисует изображение с помощью фонового цвета для списка изображений. Если цвет фона является CLR_NONE значением, изображение нарисовано прозрачно с помощью маски.

Другие возможные стили описаны под членом *fStyle* структуры [IMAGELISTDRAWPARAMS.](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams)

*dwRop*<br/>
Значение, определяющее код raster-operation. Эти коды определяют, как цветные данные для исходного прямоугольника будут сочетаться с цветными данными для прямоугольника назначения для достижения конечного цвета. Реализация MFC по умолчанию, SRCCOPY, копирует прямоугольник исходного кода непосредственно к прямоугольнику назначения. Этот параметр игнорируется, если параметр *fStyle* не включает ILD_ROP флаг.

Другие возможные значения описаны под *dwRop* членом структуры [IMAGELISTDRAWPARAMS.](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams)

*rgbBack*<br/>
Цвет фона изображения, по умолчанию CLR_DEFAULT. Этот параметр может быть значением RGB, определяемым приложением, или одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|По умолчанию фоновый цвет. Изображение нарисовано с помощью фонового цвета списка изображений.|
|CLR_NONE|Нет фонового цвета. Изображение нарисовано прозрачно.|

*rgbFore*<br/>
Изображение цвета переднего плана, по умолчанию CLR_DEFAULT. Этот параметр может быть значением RGB, определяемым приложением, или одним из следующих значений:

|Значение|Значение|
|-----------|-------------|
|CLR_DEFAULT|Цвет переднего плана по умолчанию. Изображение нарисовано с помощью цвета выделения системы в качестве цвета переднего плана.|
|CLR_NONE|Нет смеси цвета. Изображение смешивается с цветом контекста устройства назначения.|

Этот параметр используется только в том случае, если *fStyle* включает ILD_BLEND25 или ILD_BLEND50 флаг.

*fState*<br/>
Пометить состояние чертежа. Этот участник может содержать один или несколько флагов состояния списка изображений.

*Frame*<br/>
Влияет на поведение насыщенных и альфа-смешения эффектов.

При использовании с ILS_SATURATE, этот член имеет значение, которое добавляется к каждому цвету компонента триплет RGB для каждого пикселя в значке.

При использовании с ILS_APLHA, этот член имеет значение для альфа-канала. Это значение может быть от 0 до 255, при этом 0 является полностью прозрачным, а 255 - полностью непрозрачным.

*crEffect*<br/>
Значение [COLORREF,](/windows/win32/gdi/colorref) используемое для светящихся и теневых эффектов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если изображение успешно нарисовано; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Используйте первую версию, если вы хотите заполнить структуру Win32 самостоятельно. Используйте вторую версию, если вы хотите воспользоваться одним или более аргументами MFC по умолчанию или избежать управления структурой.

Накладное изображение — это изображение, нарисованное поверх основного изображения, указанное в этой функции члена параметром *nImage.* Нарисуйте маску наложения, используя функцию члена [Draw](#draw) с помощью однооснованного индекса маски наложения, указанного с помощью макроса [INDEXTOOVERLAYMASK.](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>CImageList::EndDrag

Вызовите эту функцию, чтобы закончить операцию перетаскивания.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Remarks

Чтобы начать операцию перетаскивания, используйте функцию `BeginDrag` члена.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>CImageList:ExtractIcon

Вызовите эту функцию, чтобы создать значок на основе изображения и связанных с ним маски в списке изображений.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения.

### <a name="return-value"></a>Возвращаемое значение

Ручка иконы в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Этот метод опирается на поведение [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) макроса для создания значка. Для получения дополнительной информации о создании и очистке значков обратитесь к [макросу ImageList_ExtractIcon.](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>CImageList::FromHandle

Возвращает указатель объекту `CImageList` при вечке ручки в список изображений.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Определяет список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CImageList` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Если `CImageList` a еще не прикреплен к ручке, создается и прикрепляется временный `CImageList` объект. Этот `CImageList` временный объект действителен только до следующего времени, когда приложение не будет проходить время простоя в цикле событий, после чего все временные объекты удаляются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>CImageList::FromTheПостоянный

Возвращает указатель объекту `CImageList` при вечке ручки в список изображений.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>Параметры

*hImageList*<br/>
Определяет список изображений.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CImageList` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Если `CImageList` объект не прикреплен к ручке, NULL возвращается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>CImageList::GetBkColor

Вызов ими функции для получения текущего фонового цвета для списка изображений.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB `CImageList` фонового цвета объекта.

### <a name="example"></a>Пример

  Смотрите пример [Для CImageList::SetBkColor](#setbkcolor).

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>CImageList:GetDragImage

Получает временный список изображений, который используется для перетаскивания.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>Параметры

*lpPoint*<br/>
Адрес структуры [POINT,](/windows/win32/api/windef/ns-windef-point) которая получает текущее положение сопротивления.

*lpPointHotSpot*<br/>
Адрес `POINT` структуры, которая получает смещение изображения перетаскивания относительно позиции перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на временный список изображений, который используется для перетаскивания; в противном случае, NULL.

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>CImageList::GetImageCount

Вызов ими функции для получения количества изображений в списке изображений.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество изображений.

### <a name="example"></a>Пример

  Смотрите пример [для CImageList::ExtractIcon](#extracticon).

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>CImageList::GetImageInfo

Вызовите эту функцию, чтобы получить информацию об изображении.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения.

*pImageInfo*<br/>
Указатель на структуру [IMAGEINFO,](/windows/win32/api/commctrl/ns-commctrl-imageinfo) которая получает информацию об изображении. Информация в этой структуре может быть использована для непосредственного манипулирования бит-картами для изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Структура `IMAGEINFO` содержит информацию об изображении в списке изображений.

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>CImageList:GetSafeHandle

Вызовите эту функцию для получения участника `m_hImageList` данных.

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к прилагаемому списку изображений; в противном случае NULL, если объект не прилагается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>CImageList::m_hImageList

Ручка списка изображений, прикрепленная к этому объекту.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Remarks

Член `m_hImageList` данных является общедоступной переменной типа HIMAGELIST.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>CImageList:Оператор HIMAGELIST

Используйте этот оператор, чтобы получить `CImageList` прилагаемую ручку объекта.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка в списке `CImageList` изображений, представленном объектом; в противном случае NULL.

### <a name="remarks"></a>Remarks

Этот оператор является оператором литья, который поддерживает прямое использование объекта HIMAGELIST.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>CImageList::Читать

Вызовите эту функцию, чтобы прочитать список изображений из архива.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*pArchive*<br/>
Указатель на `CArchive` объект, с которого должен быть прочитан список изображений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>CImageList::Удалить

Вызовите эту функцию, чтобы удалить изображение из объекта списка изображений.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Все элементы, следующие *за nImage* теперь двигаться вниз по одной позиции. Например, если список изображений содержит два элемента, исключение первого элемента приведет к тому, что оставшийся элемент будет теперь находиться в первой позиции. *nImage*No0 для элемента в первой позиции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>CImageList::Заменить

Вызовите эту функцию, чтобы заменить изображение в списке изображений новым изображением.

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

*nИзображение*<br/>
Нулевой индекс изображения для замены.

*pbmImage*<br/>
Указатель на битную карту, содержащую изображение.

*pbmMask*<br/>
Указатель на бит-карту, содержащую маску. Если в списке изображений не используется маска, этот параметр игнорируется.

*hIcon*<br/>
Ручка к значку, которая содержит битовую карту и маску для нового изображения.

### <a name="return-value"></a>Возвращаемое значение

Версия возвращения BOOL возвращается ненулевой, если успешно; в противном случае 0.

Версия, возвращающая **int,** возвращает нулевой индекс изображения в случае успеха; в противном случае - 1.

### <a name="remarks"></a>Remarks

Вызовите эту функцию участника после вызова [SetImageCount,](#setimagecount) чтобы присвоить новые, действительные изображения номерам индекса заполнителя.

### <a name="example"></a>Пример

  Смотрите пример [Для CImageList::SetImageCount](#setimagecount).

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>CImageList:SetBkColor

Вызовите эту функцию, чтобы установить цвет фона для списка изображений.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>Параметры

*Cr*<br/>
Цвет фона для установки. Это может быть CLR_NONE. В этом случае изображения нарисованы прозрачно с помощью маски.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет фона в случае успеха; в противном случае CLR_NONE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>CImageList::SetDragCursorImage

Создает новое изображение перетаскивания, комбинируя данное изображение (обычно изображение курсора мыши) с текущим изображением перетаскивания.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>Параметры

*nDrag*<br/>
Индекс нового изображения, который будет сочетаться с изображением перетаскивания.

*ptHotSpot*<br/>
Положение горячей точки в новом изображении.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Поскольку функции перетаскивания используют новое изображение во время операции перетаскивания, следует использовать функцию Windows [ShowCursor,](/windows/win32/api/winuser/nf-winuser-showcursor) чтобы скрыть фактический курсор мыши после вызова. `CImageList::SetDragCursorImage` В противном случае в системе может появиться два курсора мыши на время операции перетаскивания.

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>CImageList:SetImageCount

Вызов ифункции этого участника для сбросить количество изображений в объекте. `CImageList`

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>Параметры

*uNewCount*<br/>
Значение, определяющее новое общее количество изображений в списке изображений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Если вы называете эту функцию участника, чтобы увеличить количество изображений в списке изображений, затем позвоните [заменить](#replace) для каждого дополнительного изображения, чтобы назначить новые индексы действительным изображениям. Если не удается присвоить индексы действительным изображениям, нарисовать операции, создающие новые изображения, будет непредсказуемым.

Если с помощью этой функции уменьшить размер списка изображений, усеченные изображения освобождаются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>CImageList:SetOverlayImage

Вызовите эту функцию, чтобы добавить нулевой индекс изображения в список изображений, которые будут использоваться в качестве накладных масок.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>Параметры

*nИзображение*<br/>
Нулевой индекс изображения для использования в качестве маски наложения.

*nOverlay*<br/>
Одноединый индекс маски наложения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

В список можно добавить до четырех индексов.

Маска наложения — это изображение, нарисованное прозрачно над другим изображением. Нарисуйте маску наложения на изображение с помощью функции [cImageList::Draw-участника](#draw) с помощью однооснованного индекса маски наложения, указанного с помощью макроса INDEXTOOVERLAYMASK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>CImageList::Запись

Вызовите эту функцию, чтобы написать объект списка изображений в архив.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>Параметры

*pArchive*<br/>
Указатель на `CArchive` объект, в котором должен храниться список изображений.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CListCtrl](../../mfc/reference/clistctrl-class.md)<br/>
[Класс CTabCtrl](../../mfc/reference/ctabctrl-class.md)
