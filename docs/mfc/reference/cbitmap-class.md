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
ms.openlocfilehash: 9a33a6e1bea601422e043d7f2a80029c72d97e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352747"
---
# <a name="cbitmap-class"></a>Класс CBitmap

Инкапсулирует растровое изображение интерфейса графических устройств Windows (GDI) и предоставляет функции-члены для манипулирования этим растровым изображением.

## <a name="syntax"></a>Синтаксис

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBitmap::CBitmap](#cbitmap)|Формирует объект `CBitmap`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|Инициализирует объект с помощью бидорожной карты памяти, зависящей от устройства памяти, которая имеет заданную ширину, высоту и битовой узор.|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Инициализирует объект битовой картой с шириной, высотой и рисунком бита (если указано), приведенным в структуре. `BITMAP`|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Инициализирует объект битной картой так, чтобы он был совместим с указанным устройством.|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Инициализирует объект с помощью отбрасываемой битовой карты, совместимой с указанным устройством.|
|[CBitmap::FromHandle](#fromhandle)|Возвращает указатель объекту `CBitmap` при отваге ручки на битную карту Windows. `HBITMAP`|
|[CBitmap:GetBitmap](#getbitmap)|Заполняет `BITMAP` структуру информацией о бит-карте.|
|[CBitmap:GetBitmapBits](#getbitmapbits)|Копирует биты указанной битовой карты в указанный буфер.|
|[CBitmap:GetBitmapDimension](#getbitmapdimension)|Возвращает ширину и высоту битной карты. Высота и ширина, как предполагается, были установлены ранее функцией члена [SetBitmapDimension.](#setbitmapdimension)|
|[CBitmap:LoadBitmap](#loadbitmap)|Инициализирует объект, загрузив именный ресурс биткарты из исполняемого файла приложения и прикрепив битную карту к объекту.|
|[CBitmap:LoadMappedBitmap](#loadmappedbitmap)|Загружает битную карту и отображает цвета в текущие цвета системы.|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Инициализирует объект, загружая заданную битную карту Windows и прикрепляя битную карту к объекту.|
|[CBitmap::SetBitmapBits](#setbitmapbits)|Устанавливает бит битовой карты на указанные значения бита.|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Присваивает ширину и высоту биткарте в 0,1-миллиметровых единицах.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CBitmap:оператор HBITMAP](#operator_hbitmap)|Возвращает ручку Windows, `CBitmap` прикрепленную к объекту.|

## <a name="remarks"></a>Remarks

Чтобы использовать `CBitmap` объект, постройте объект, прикрепите к нему рукоятку биткарты с одной из функций члена инициализации, а затем вызовите функции члена объекта.

Для получения дополнительной информации `CBitmap`об использовании графических объектов, таких как, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cbitmapcbitmap"></a><a name="cbitmap"></a>CBitmap::CBitmap

Формирует объект `CBitmap`.

```
CBitmap();
```

### <a name="remarks"></a>Remarks

Полученный объект должен быть инициализирован с одной из функций члена инициализации.

## <a name="cbitmapcreatebitmap"></a><a name="createbitmap"></a>CBitmap::CreateBitmap

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

*nВысота*<br/>
Задается высота (в пикселях) битовой карты.

*nСамолеты*<br/>
Задается число цветовых плоскостей в битовой карте.

*nBitcount*<br/>
Задается число цветовых битов на пиксель отображения.

*lpBits*<br/>
Указывается массив байтов, содержащий исходные значения битов битовой карты. Если указывается значение NULL, новая битовая карта остается неинициализированной.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Для цветовой битной карты параметр *nPlanes* или *nBitcount* должен быть установлен на 1. Если оба этих параметра имеют значение 1, `CreateBitmap` создает монохромную битовую карту.

Несмотря на то, что нельзя напрямую выбрать битовую карту для устройства отображения, ее можно выбрать как текущую битовую карту для "контекста устройства памяти" с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и скопировать в любой совместимый контекст устройства с помощью функции [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) .

После завершения работы с объектом `CBitmap` , созданным функцией `CreateBitmap` , сначала выберите битовую карту из контекста устройства, а затем удалите объект `CBitmap` .

Для получения дополнительной информации, `bmBits` см `BITMAP` описание поля в структуре. Структура [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) рассматривается в описании функции-члена [CBitmap::CreateBitmapIndirect](#createbitmapindirect) .

## <a name="cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect

Инициализирует битовую карту, которая имеет ширину, высоту и битшаблон (если указано), приведенную в структуре, указанной *lpBitmap.*

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Параметры

*lpBitmap*<br/>
Указывает на структуру [BITMAP,](/windows/win32/api/wingdi/ns-wingdi-bitmap) содержащую информацию о бит-карте.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Хотя бит-карта не может быть выбрана непосредственно для устройства отображения, она может быть выбрана в качестве текущей битовой карты для контекста устройства памяти с помощью [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) и скопирована на любой совместимый контекст устройства с помощью [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) функции. (Функция [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) может скопировать битовую карту для текущей кисти непосредственно в контексте устройства дисплея.)

Если `BITMAP` структура, указанная параметром *lpBitmap,* была `GetObject` заполнена с помощью функции, биты битной карты не указаны и битная карта не является первоначальной. Для инициализации бит-карты приложение может использовать функцию, такую как [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) или [SetDIBits,](/windows/win32/api/wingdi/nf-wingdi-setdibits) `CGdiObject::GetObject` чтобы скопировать биты `CreateBitmapIndirect`из битовой карты, идентифицированной первым параметром к битной карте, созданной .

Закончив объект, созданный `CBitmap` с `CreateBitmapIndirect` функцией, сначала выберите битную `CBitmap` карту из контекста устройства, а затем удалите объект.

## <a name="cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap

Инициализирует битную карту, совместимую с устройством, указанным *pDC.*

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Определяет контекст устройства.

*nWidth*<br/>
Задается ширина (в пикселях) битовой карты.

*nВысота*<br/>
Задается высота (в пикселях) битовой карты.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Бит-карта имеет такое же количество цветных плоскостей или тот же формат битов на пиксель, что и указанный контекст устройства. Он может быть выбран в качестве текущей битовой карты для любого устройства памяти, совместимого с устройством, указанным *pDC.*

Если *pDC* является контекстом устройства памяти, возвращается биткарта имеет тот же формат, что и выбранная в настоящее время битовая карта в этом контексте устройства. "Контекст устройства памяти" представляет собой блок памяти, представляющий поверхность дисплея. Он может быть использован для подготовки изображений в памяти, прежде чем копировать их на фактическую поверхность дисплея совместимого устройства.

При создании контекста устройства памяти GDI автоматически выбирает для него монохромную битную карту.

Поскольку контекст устройства цветной памяти может быть выбран как цветные, так `CreateCompatibleBitmap` и монохромные бит-карты, формат битной карты, возвращенной функцией, не всегда одинаков; однако формат совместимой битовой карты для контекста устройства непамяти всегда находится в формате устройства.

Закончив объект, `CBitmap` созданный `CreateCompatibleBitmap` с функцией, сначала выберите битную карту `CBitmap` из контекста устройства, а затем удалите объект.

## <a name="cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap

Инициализирует отбрасываемую битную карту, совместимую с контекстом устройства, идентифицированным *pDC.*

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
Определяет ширину (в битах) битной карты.

*nВысота*<br/>
Определяет высоту (в битах) бит-карты.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Бит-карта имеет такое же количество цветных плоскостей или тот же формат битов на пиксель, что и указанный контекст устройства. Приложение может выбрать эту бит-карту в качестве текущей битовой карты для устройства памяти, совместимого с тем, которое *указываетp.pDC.*

Windows может отбросить битную карту, созданную этой функцией, только в том случае, если приложение не выбрало ее в контекст отображения. Если Windows отбрасывает битную карту, когда она не выбрана, и приложение позже попытается выбрать ее, функция [CDC:SelectObject](../../mfc/reference/cdc-class.md#selectobject) вернет NULL.

Закончив объект, `CBitmap` созданный `CreateDiscardableBitmap` с функцией, сначала выберите битную карту `CBitmap` из контекста устройства, а затем удалите объект.

## <a name="cbitmapfromhandle"></a><a name="fromhandle"></a>CBitmap::FromHandle

Возвращает указатель объекту `CBitmap` при отваге ручки на битную карту GDI с Windows.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Определяет бит-карту Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CBitmap` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Если `CBitmap` объект еще не прикреплен к ручке, создается и прикрепляется временный `CBitmap` объект. Этот `CBitmap` временный объект действителен только до следующего времени, когда приложение не будет проходить время в цикле событий, после чего все временные графические объекты удаляются. Другой способ сказать это заключается в том, что временный объект действителен только при обработке одного окна сообщения.

## <a name="cbitmapgetbitmap"></a><a name="getbitmap"></a>CBitmap:GetBitmap

Извлекает свойства изображения для прикрепленной битовой карты.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Параметры

*pBitMap*<br/>
Указатель на структуру [BITMAP,](/windows/win32/api/wingdi/ns-wingdi-bitmap) которая будет получать свойства изображения. Этот параметр не должен быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод был успешным; в противном случае 0.

### <a name="remarks"></a>Remarks

## <a name="cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a>CBitmap:GetBitmapBits

Копирует битовый узор прикрепленной битовой карты в указанный буфер.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Параметры

*dwCount*<br/>
Число байтов для копирования в буфер.

*lpBits*<br/>
Указатель на буфер, который получит битовую карту.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, скопированных в буфер, если метод был успешным; в противном случае 0.

### <a name="remarks"></a>Remarks

Используйте [CBitmap:GetBitmap](#getbitmap) для определения требуемого размера буфера.

## <a name="cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a>CBitmap:GetBitmapDimension

Возвращает ширину и высоту битной карты.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина и высота бит-карты, измеренной в 0,1-миллиметровых единицах. Высота находится в `cy` члене `CSize` объекта, а ширина `cx` — в члене. Если ширина и высота биткарты не `SetBitmapDimension`были установлены с помощью, значение возврата составляет 0.

### <a name="remarks"></a>Remarks

Высота и ширина, как предполагается, были установлены ранее с помощью функции члена [SetBitmapDimension.](#setbitmapdimension)

## <a name="cbitmaploadbitmap"></a><a name="loadbitmap"></a>CBitmap:LoadBitmap

Загружает ресурс bitmap, названный *lpszResourceName* или идентифицированный по идентификационному номеру в *nIDResource,* из исполняемого файла приложения.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указывает на нулевую строку, содержащую имя ресурса bitmap.

*nIDResource*<br/>
Упоняет идентификационный номер ресурса ресурса ресурса bitmap.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Загруженная битная карта прикрепляется к объекту. `CBitmap`

Если бит-карта, идентифицированная *lpszResourceName,* не существует или если не хватает памяти для загрузки бит-карты, функция возвращает 0.

Вы можете использовать функцию [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) для удаления `LoadBitmap` битовой `CBitmap` карты, загруженной функцией, или деструктор удалит объект для вас.

> [!CAUTION]
> Перед удалением объекта убедитесь, что он не выбран в контексте устройства.

Следующие бит-карты были добавлены в версии Windows 3.1 и позже:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Эти бит-карты не встречаются в драйверах устройств для версий Windows 3.0 и ранее. Полный список бит-карт и отображение их внешнего вида можно узнать в Windows SDK.

## <a name="cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a>CBitmap:LoadMappedBitmap

Вызов исчерпайте эту функцию участника, чтобы загрузить битную карту и сопоставить цвета с текущими цветами системы.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Параметры

*nIDBitmap*<br/>
Идентификатор ресурса bitmap.

*nФлаги*<br/>
Флаг для бит-карты. Может быть ноль или CMB_MASKED.

*lpColorMap*<br/>
Указатель на `COLORMAP` структуру, содержащую цветовую информацию, необходимую для картирования битовых карт. Если этот параметр NULL, функция использует цветную карту по умолчанию.

*nMapSize*<br/>
Количество цветных карт, на которые указывает *lpColorMap*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

По умолчанию будет отображаться цвета, `LoadMappedBitmap` обычно используемые в глифах кнопок.

Для получения информации о создании отображаемых битовой [COLORMAP](/windows/win32/api/commctrl/ns-commctrl-colormap) карты см. [CreateMappedBitmap](https://go.microsoft.com/fwlink/p/?linkid=230562)

## <a name="cbitmaploadoembitmap"></a><a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap

Загружает предопределенную бит-карту, используемую Windows.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Параметры

*nIDBitmap*<br/>
Идентификационный номер предопределенной битовой карты Windows. Возможные значения перечислены ниже из WINDOWS. H:

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

### <a name="remarks"></a>Remarks

Имена Bitmap, которые начинаются с OBM_OLD представляют bitmaps, используемые версиями Windows до 3.0.

Обратите внимание, что постоянный OEMRESOURCE должен быть определен до включения WINDOWS. H для того, чтобы использовать любой из **OBM_** констант.

## <a name="cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a>CBitmap:оператор HBITMAP

Используйте этот оператор, чтобы получить прилагаемую ручку Windows GDI `CBitmap` объекта.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха ручка для объекта Windows `CBitmap` GDI, представленная объектом; в противном случае NULL.

### <a name="remarks"></a>Remarks

Этот оператор является оператором литья, `HBITMAP` который поддерживает прямое использование объекта.

Для получения дополнительной информации об использовании графических объектов [см.](/windows/win32/gdi/graphic-objects)

## <a name="cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a>CBitmap::SetBitmapBits

Устанавливает бит битной карты на значения бита, приведенные *lpBits.*

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Параметры

*dwCount*<br/>
Определяет количество байтов, на которые указывают *lpBits.*

*lpBits*<br/>
Указывает на массив BYTE, содержащий значения пикселей, `CBitmap` которые должны быть скопированы с объектом. Для того, чтобы биткарта могла правильно сделать свое изображение, значения должны быть отформатированы в соответствии с значениями высоты, ширины и глубины цвета, которые были указаны при создании экземпляра CBitmap. Для получения дополнительной информации [см. CBitmap::CreateBitmap](#createbitmap).

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, используемых при настройке битовой карты; 0, если функция выходит из строя.

## <a name="cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension

Присваивает ширину и высоту биткарте в 0,1-миллиметровых единицах.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Определяет ширину бит-карты (в 0,1-миллиметровых единиц).

*nВысота*<br/>
Определяет высоту бит-карты (в 0,1-миллиметровых единиц).

### <a name="return-value"></a>Возвращаемое значение

Предыдущие размеры биткарты. Высота находится `cy` в переменной `CSize` члена объекта, а `cx` ширина — в переменной члена.

### <a name="remarks"></a>Remarks

GDI не использует эти значения, за исключением их возврата, когда приложение вызывает функцию члена [GetBitmapDimension.](#getbitmapdimension)

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
