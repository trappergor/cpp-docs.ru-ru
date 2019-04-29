---
title: Класс CBitmap
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: 11e210680bdf68f1a1dcbfaed18ae56ce006c8ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388453"
---
# <a name="cbitmap-class"></a>Класс CBitmap

Инкапсулирует растровое изображение интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим растровым изображением.

## <a name="syntax"></a>Синтаксис

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CBitmap::CBitmap](#cbitmap)|Создает объект `CBitmap`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|Инициализирует объект с зависящие от устройства памяти растрового изображения, который имеет заданную ширину, высоту и битовый шаблон.|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Инициализирует объект с точечным рисунком ширину, высоту и битовый шаблон (если оно указано), заданный в `BITMAP` структуры.|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Инициализирует объект с растровым изображением, чтобы она стала совместима с указанным устройством.|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Инициализирует объект с удаляемое точечного рисунка, который совместим с указанным устройством.|
|[CBitmap::FromHandle](#fromhandle)|Возвращает указатель на `CBitmap` объект для заданного дескриптора для Windows `HBITMAP` растрового изображения.|
|[CBitmap::GetBitmap](#getbitmap)|Заполняет `BITMAP` структуру сведениями о растрового изображения.|
|[CBitmap::GetBitmapBits](#getbitmapbits)|Копирует биты указанного растрового изображения в указанный буфер.|
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Возвращает ширину и высоту растрового изображения. Высота и ширина предполагается, что заданные ранее [SetBitmapDimension](#setbitmapdimension) функция-член.|
|[CBitmap::LoadBitmap](#loadbitmap)|Инициализирует объект путем загрузки ресурса именованного точечного рисунка из исполняемого файла приложения и присоединение точечного рисунка на объект.|
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Загружает растровый рисунок и сопоставляется текущей цветовой палитры цветов.|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Инициализирует объект путем загрузки предопределенные точечный рисунок Windows и присоединение точечного рисунка на объект.|
|[CBitmap::SetBitmapBits](#setbitmapbits)|Задает биты растрового изображения для указанного бита значения.|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Присваивает ширину и высоту растрового изображения в единицах 0,1 миллиметр.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Возвращает дескриптор Windows, подключенный к `CBitmap` объекта.|

## <a name="remarks"></a>Примечания

Чтобы использовать `CBitmap` объекта, создать объект, к ней с помощью одного из функции-члены инициализации подключить дескриптор точечного рисунка и затем вызов функций-членов объекта.

Дополнительные сведения об использовании графических объектов, таких как `CBitmap`, см. в разделе [график объектов](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cbitmap"></a>  CBitmap::CBitmap

Создает объект `CBitmap`.

```
CBitmap();
```

### <a name="remarks"></a>Примечания

Полученный объект необходимо инициализировать с помощью одной из функций инициализации элемента.

##  <a name="createbitmap"></a>  CBitmap::CreateBitmap

Инициализируется аппаратно зависимая битовая карта памяти, имеющая заданную ширину, высоту и битовый шаблон.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Задается ширина (в пикселях) битовой карты.

*nHeight*<br/>
Задается высота (в пикселях) битовой карты.

*nPlanes*<br/>
Задается число цветовых плоскостей в битовой карте.

*nBitcount*<br/>
Задается число цветовых битов на пиксель отображения.

*lpBits*<br/>
Указывается массив байтов, содержащий исходные значения битов битовой карты. Если он имеет значение NULL, новая Битовая карта остается неинициализированной.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Для цветовой битовой карты либо *nPlanes* или *nBitcount* параметра должно быть установлено в 1. Если оба этих параметра имеют значение 1, `CreateBitmap` создает монохромную битовую карту.

Несмотря на то, что нельзя напрямую выбрать битовую карту для устройства отображения, ее можно выбрать как текущую битовую карту для "контекста устройства памяти" с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и скопировать в любой совместимый контекст устройства с помощью функции [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) .

После завершения работы с объектом `CBitmap` , созданным функцией `CreateBitmap` , сначала выберите битовую карту из контекста устройства, а затем удалите объект `CBitmap` .

Дополнительные сведения см. в описании `bmBits` в `BITMAP` структуры. Структура [BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) рассматривается в описании функции-члена [CBitmap::CreateBitmapIndirect](#createbitmapindirect) .

##  <a name="createbitmapindirect"></a>  CBitmap::CreateBitmapIndirect

Инициализирует точечный рисунок, ширину, высоту и битовый шаблон (если оно указано) в структуре, на которые указывают *lpBitmap*.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Параметры

*lpBitmap*<br/>
Указывает на [точечного РИСУНКА](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) структуру, содержащую сведения о растрового изображения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Несмотря на то, что точечный рисунок невозможно напрямую выбрать для устройства отображения, ее можно выбрать как текущую битовую карту для контекста устройства памяти с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и скопировать в любой совместимый контекст устройства с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) функции. ( [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) функции можно скопировать растрового изображения для текущей кисти непосредственно для контекста устройства отображения.)

Если `BITMAP` структуры, на которые указывают *lpBitmap* параметр будет заполнен с помощью `GetObject` функция, биты растрового изображения не указаны и растровое изображение не инициализирована. Для инициализации растрового изображения, приложение может использовать функции например [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits) Копировать биты из растрового изображения, идентифицируемый первый параметр `CGdiObject::GetObject` к растровому изображению, созданные `CreateBitmapIndirect`.

После завершения работы с `CBitmap` объект, созданный с помощью `CreateBitmapIndirect` функцию, сначала выберите битовую карту из контекста устройства, а затем удалить `CBitmap` объекта.

##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap

Инициализирует точечного рисунка, который совместим с устройстве с *pDC*.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает контекст устройства.

*nWidth*<br/>
Задается ширина (в пикселях) битовой карты.

*nHeight*<br/>
Задается высота (в пикселях) битовой карты.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Растровое изображение имеет одинаковое число цветовых плоскостей или же формат бит на пиксель, что указанный контекст устройства. Ее можно выбрать как текущую битовую карту для любого устройства памяти, которая совместима с, указанного параметром *pDC*.

Если *pDC* является контекста устройства памяти, растровое изображение возвращается имеет тот же формат, как текущий выбранный битовую карту в этом контексте устройства. «Контекста устройства памяти» представляет собой блок памяти, представляющий поверхность отображения. Его можно использовать для подготовки образов в памяти перед их копированием на поверхность отображения совместимое устройство.

При создании контекста устройства памяти GDI автоматически выбирает для него монохромную битовую карту акций.

Поскольку контекста устройства памяти цвет может иметь цвета или выбранные монохромный точечные рисунки, формат растрового изображения, возвращаемые `CreateCompatibleBitmap` функции не всегда соответствует; тем не менее, формат, совместимый растрового изображения для контекста устройства nonmemory всегда находится в Формат устройства.

После завершения работы с `CBitmap` объект, созданный с помощью `CreateCompatibleBitmap` функцию, сначала выберите битовую карту из контекста устройства, а затем удалить `CBitmap` объекта.

##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap

Инициализирует удаляемое точечного рисунка, который совместим с контекст устройства, определяемый *pDC*.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Определяет контекст устройства.

*nWidth*<br/>
Ширина растрового изображения (в битах).

*nHeight*<br/>
Высота растрового изображения (в битах).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Растровое изображение имеет одинаковое число цветовых плоскостей или же формат бит на пиксель, что указанный контекст устройства. Приложение может выбрать этим растровым изображением, как текущую битовую карту памяти устройства, совместимого с, указанного параметром *pDC*.

Windows можно отменить растрового изображения, созданного при помощи этой функции только в том случае, если приложение не выбрала его в контексте отображения. Если Windows отбрасывает точечного рисунка, если он не выбран, и его позже пытается выделить ее, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) функция вернет значение NULL.

После завершения работы с `CBitmap` объект, созданный с помощью `CreateDiscardableBitmap` функцию, сначала выберите битовую карту из контекста устройства, а затем удалить `CBitmap` объекта.

##  <a name="fromhandle"></a>  CBitmap::FromHandle

Возвращает указатель на `CBitmap` объект для заданного дескриптора точечного рисунка Windows GDI.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Указывает точечного рисунка Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CBitmap` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CBitmap` объект еще не присоединен к дескриптору, временный `CBitmap` созданный и присоединенный объект. Этот временный `CBitmap` объект является допустимым, только пока очередном приложение время простоя в свой цикл событий, после чего график все временные объекты будут удалены. Другими словами — это что временный объект допустима только во время обработки сообщения одного окна.

##  <a name="getbitmap"></a>  CBitmap::GetBitmap

Извлекает свойства изображения для присоединенного растрового изображения.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Параметры

*pBitMap*<br/>
Указатель на [точечного РИСУНКА](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) структуры, который будет получать свойства изображения. Этот параметр не должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод был выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits

Копирует битовым шаблоном присоединенного растровое изображение в указанный буфер.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Параметры

*dwCount*<br/>
Число байтов для копирования в буфер.

*lpBits*<br/>
Указатель на буфер, который будет получать растрового изображения.

### <a name="return-value"></a>Возвращаемое значение

Число байтов, копируемых в буфер, если метод был выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Используйте [CBitmap::GetBitmap](#getbitmap) чтобы определить необходимый размер буфера.

##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension

Возвращает ширину и высоту растрового изображения.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина и Высота растрового изображения, измеряемая в единицах 0,1 миллиметр. Высота находится в `cy` членом `CSize` , а ширина — в `cx` член. Если точечный рисунок ширина и высота не были установлены с помощью `SetBitmapDimension`, возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Высота и ширина предполагается, что заданные ранее с помощью [SetBitmapDimension](#setbitmapdimension) функция-член.

##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap

Загружает растровое изображение ресурсом, *lpszResourceName* или идентифицируемый номер идентификатора в *nIDResource* из исполняемого файла приложения.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя ресурса точечного рисунка.

*nIDResource*<br/>
Указывает идентификатор ресурса точечного рисунка ресурса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Загрузить точечный рисунок присоединяется к `CBitmap` объекта.

Если точечный рисунок, определяемая параметром *lpszResourceName* не существует или если недостаточно памяти для загрузки точечного рисунка, функция возвращает значение 0.

Можно использовать [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) функцию для удаления растрового изображения, загруженные `LoadBitmap` функция, или `CBitmap` деструктор будет удалить объект.

> [!CAUTION]
>  Прежде чем удалить объект, убедитесь, что он не установлен в контексте устройства.

К 3.1 и более поздних версиях Windows были добавлены следующие растровых изображений:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Эти точечные рисунки не найдены в драйверы устройств для Windows версии 3.0 и более ранних версий. Полный список растровых изображений, а также их внешнего вида см. в Windows SDK.

##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap

Вызов этой функции-члена для загрузки точечного рисунка и сопоставления для текущей цветовой палитры цветов.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Параметры

*nIDBitmap*<br/>
Идентификатор ресурса точечного рисунка.

*nFlags*<br/>
Флаг для растрового изображения. Может содержать ноль или CMB_MASKED.

*lpColorMap*<br/>
Указатель на `COLORMAP` структуру, содержащую цвет сведения, необходимые для сопоставления точечных рисунков. Если этот параметр имеет значение NULL, функция использует карта цветов по умолчанию.

*nMapSize*<br/>
Число карт цветов, на которые указывают *lpColorMap*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

По умолчанию `LoadMappedBitmap` сопоставит цветов, обычно используемых в кнопку глифов.

Сведения о создании сопоставленной точечного рисунка, см. в разделе Windows функция [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) и [COLORMAP](/windows/desktop/api/commctrl/ns-commctrl-_colormap) структуры в пакете Windows SDK.

##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap

Загружает предварительно определенных растровое изображение, используемые Windows.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Параметры

*nIDBitmap*<br/>
Идентификационный номер предопределенные растрового изображения Windows. Ниже перечислены возможные значения из WINDOWS. H:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Точечный рисунок, имена которых начинаются с OBM_OLD представляют собой точечные рисунки, используемые версии Windows до версии 3.0.

Обратите внимание на то, что константа OEMRESOURCE должно быть задано до включения WINDOWS. H, чтобы использовать любой из **OBM_** константы.

##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP

Этот оператор используется для получения присоединенного дескриптор Windows GDI `CBitmap` объекта.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения дескриптор объекта Windows GDI, представленных `CBitmap` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот оператор — оператор приведения, которая поддерживает прямое использование `HBITMAP` объекта.

Дополнительные сведения об использовании графических объектов см. в разделе [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits

Задает биты растрового изображения для битовых значений, предоставляемых *lpBits*.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Параметры

*dwCount*<br/>
Указывает число байтов, на которые указывают *lpBits*.

*lpBits*<br/>
Указывает на массив БАЙТОВ, содержащий значения пикселей для копирования `CBitmap` объекта. Чтобы точечный рисунок, который не может правильно отобразить изображения значения форматируются в соответствии с высота, ширина и цвет глубины значения, которые были заданы при создании экземпляра CBitmap. Дополнительные сведения см. в разделе [CBitmap::CreateBitmap](#createbitmap).

### <a name="return-value"></a>Возвращаемое значение

Число байтов, которые применяются при настройке биты растрового изображения; 0, если функция завершается с ошибкой.

##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension

Присваивает ширину и высоту растрового изображения в единицах 0,1 миллиметр.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина растрового изображения (в единицах 0,1 мм).

*nHeight*<br/>
Высота растрового изображения (в единицах 0,1 мм).

### <a name="return-value"></a>Возвращаемое значение

Предыдущие размеры точечного рисунка. Высота находится в `cy` переменной-члена `CSize` , а ширина — в `cx` переменной-члена.

### <a name="remarks"></a>Примечания

GDI не использует эти значения, за исключением того, чтобы вернуть их, как когда приложение вызывает [GetBitmapDimension](#getbitmapdimension) функция-член.

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
