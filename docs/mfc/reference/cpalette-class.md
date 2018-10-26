---
title: Класс CPalette | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28c12e2c462061604398ab5283374e74bcad810e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071905"
---
# <a name="cpalette-class"></a>Класс CPalette

Инкапсулирует цветовую палитру Windows.

## <a name="syntax"></a>Синтаксис

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPalette::CPalette](#cpalette)|Создает `CPalette` объект с присоединенного палитры Windows. Необходимо инициализировать `CPalette` объекта с одним из функции-члены инициализации, прежде чем он может использоваться.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|Заменяет записей в логическую палитру, идентифицируемый `CPalette` объекта. Приложения не требуется обновить свою клиентскую область, поскольку Windows сопоставляет новые записи в системной палитре немедленно.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Создает полутоновой палитры для контекста устройства и присоединяет его к `CPalette` объекта.|
|[CPalette::CreatePalette](#createpalette)|Создает цветовую палитру Windows и присоединяет его к `CPalette` объекта.|
|[CPalette::FromHandle](#fromhandle)|Возвращает указатель на `CPalette` объект для заданного дескриптора в объект палитры Windows.|
|[CPalette::GetEntryCount](#getentrycount)|Возвращает число элементы палитры в логическую палитру.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Возвращает индекс элемента в логическую палитру, который наиболее полно соответствует значение цвета.|
|[CPalette::GetPaletteEntries](#getpaletteentries)|Получает диапазон элементы палитры в логическую палитру.|
|[CPalette::ResizePalette](#resizepalette)|Изменяет размер логической палитры, определяемое `CPalette` объект на указанное число записей.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|Задает значения цвета RGB и флаги в диапазоне элементов в логическую палитру.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CPalette::operator HPALETTE](#operator_hpalette)|Возвращает HPALETTE подключен к `CPalette`.|

## <a name="remarks"></a>Примечания

Палитра интерфейс между приложением и цвет устройство вывода (например, устройство отображения). Этот интерфейс позволяет приложение, чтобы воспользоваться всеми преимуществами цветовые возможности устройства вывода без важности влияния цвета, отображаемые в других приложениях. Windows использует логическую палитру приложения (список необходимых цветов) и в Системная палитра (который определяет доступные цвета), чтобы определить используемые цвета.

Объект `CPalette` объект предоставляет функции-члены для управления палитры ссылается объект. Создать `CPalette` и использовать его функции-члены для создания фактического палитры, графический интерфейс (GDI) объект устройства и управлять его записи и другие свойства.

Дополнительные сведения об использовании `CPalette`, см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="animatepalette"></a>  CPalette::AnimatePalette

Заменяет записей в логическую палитру, подключенный к `CPalette` объекта.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*nStartIndex*<br/>
Указывает первый элемент в палитре анимировать.

*nNumEntries*<br/>
Указывает количество записей в палитре анимировать.

*lpPaletteColors*<br/>
Указывает на первый элемент массива [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) структур для замены элементы палитры, идентифицируемый *nStartIndex* и *nNumEntries*.

### <a name="remarks"></a>Примечания

Если приложение вызывает `AnimatePalette`, его не требуется обновлять свою клиентскую область, поскольку Windows сопоставляет новые записи в системной палитре немедленно.

`AnimatePalette` Функции будет только изменить записи с флагом PC_RESERVED значение в соответствующем `palPaletteEntry` членом [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) структуры, к которой подключен `CPalette` объекта. См. в разделе LOGPALETTE в пакете SDK для Windows, Дополнительные сведения об этой структуре.

##  <a name="cpalette"></a>  CPalette::CPalette

Создает объект `CPalette`.

```
CPalette();
```

### <a name="remarks"></a>Примечания

Объект не имеет подключенных палитры до вызова метода `CreatePalette` один связываемое.

##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette

Создает полутоновой палитры для контекста устройств.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Определяет контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если имеет значение ПОЛУТОНОВЫЕ режим растягивания контекста устройства, приложения следует создать полутоновой палитры. Логические полутоновой палитры, возвращенный [CreateHalftonePalette](/windows/desktop/api/wingdi/nf-wingdi-createhalftonepalette) функция-член должна затем выбран и понял, в контексте устройства перед [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) или [ StretchDIBits](/windows/desktop/api/wingdi/nf-wingdi-stretchdibits) функция вызывается.

Пакет SDK Windows, Дополнительные сведения см. в разделе `CreateHalftonePalette` и `StretchDIBits`.

##  <a name="createpalette"></a>  CPalette::CreatePalette

Инициализирует `CPalette` объекта путем создания логической цветовую палитру Windows и подключите его к `CPalette` объекта.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Параметры

*lpLogPalette*<br/>
Указывает на [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) структуру, содержащую сведения о логической палитры цветов.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Пакет SDK Windows, Дополнительные сведения см. в разделе `LOGPALETTE` структуры.

##  <a name="fromhandle"></a>  CPalette::FromHandle

Возвращает указатель на `CPalette` объект для заданного дескриптора в объект палитры Windows.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Параметры

*hPalette*<br/>
Дескриптор палитры Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CPalette` объекта, если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если `CPalette` объект еще не присоединен к палитре Windows временный `CPalette` созданный и присоединенный объект. Этот временный `CPalette` объект является допустимым, только пока очередном приложение время простоя в свой цикл событий, после чего график все временные объекты будут удалены. Другими словами временный объект допустим только во время обработки сообщения одного окна.

##  <a name="getentrycount"></a>  CPalette::GetEntryCount

Вызовите эту функцию-член для получения числа записей в данной логической палитры.

```
int GetEntryCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей в логическую палитру.

##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex

Возвращает индекс элемента в логическую палитру, который наиболее близко соответствует значению указанного цвета.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Параметры

*crColor*<br/>
Задает цвет для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Индекс записи в логической палитры. Запись содержит цвет, наиболее точно соответствующий указанному цвету.

##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries

Получает диапазон элементы палитры в логическую палитру.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Параметры

*nStartIndex*<br/>
Указывает первый элемент в логической палитры требуется получить.

*nNumEntries*<br/>
Указывает количество записей в логической палитры требуется получить.

*lpPaletteColors*<br/>
Указывает на массив из [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) структур данных для получения элементы палитры. Этот массив должен содержать по крайней мере столько структур данных в соответствии с *nNumEntries*.

### <a name="return-value"></a>Возвращаемое значение

Число записей, полученных из логической палитры; 0, если сбой функции.

##  <a name="operator_hpalette"></a>  CPalette::operator HPALETTE

Этот оператор используется для получения присоединенного дескриптор Windows GDI `CPalette` объекта.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если в случае успешного выполнения дескриптор объекта Windows GDI, представленных `CPalette` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот оператор — оператор приведения, который поддерживает непосредственное использование объекта HPALETTE.

Дополнительные сведения об использовании графических объектов см. в статье [объектов график](/windows/desktop/gdi/graphic-objects) в пакете Windows SDK.

##  <a name="resizepalette"></a>  CPalette::ResizePalette

Изменяет размер логической палитры, подключенный к `CPalette` объектом количество записей, указанных *nNumEntries*.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Параметры

*nNumEntries*<br/>
Указывает количество записей в палитре, после их изменять.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если палитре был успешно изменен; в противном случае 0.

### <a name="remarks"></a>Примечания

Если приложение вызывает `ResizePalette` для уменьшения размера палитры, операций, оставшихся в палитре измененным размером ничем не отличаются. Если приложение вызывает `ResizePalette` увеличить палитру, дополнительная палитра записи задаются на черный (значения красного, зеленого и синего: 0), и флаги для всех дополнительных записей устанавливаются в значение 0.

Дополнительные сведения о Windows API `ResizePalette`, см. в разделе [ResizePalette](/windows/desktop/api/wingdi/nf-wingdi-resizepalette) в пакете Windows SDK.

##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries

Задает значения цвета RGB и флаги в диапазоне элементов в логическую палитру.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*nStartIndex*<br/>
Указывает первый элемент в логическую палитру устанавливаемое значение.

*nNumEntries*<br/>
Указывает количество записей в логическую палитру устанавливаемое значение.

*lpPaletteColors*<br/>
Указывает на массив из [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) структур данных для получения элементы палитры. Этот массив должен содержать по крайней мере столько структур данных в соответствии с *nNumEntries*.

### <a name="return-value"></a>Возвращаемое значение

Число записей в логическую палитру; 0, если сбой функции.

### <a name="remarks"></a>Примечания

Если логическую палитру выбирается в контексте устройства, когда приложение вызывает `SetPaletteEntries`, изменения не вступят в силу пока приложение не вызовет [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).

Дополнительные сведения о структуре Windows `PALETTEENTRY`, см. в разделе [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Пример MFC DIBLOOK](../../visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)

