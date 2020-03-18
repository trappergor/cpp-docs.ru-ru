---
title: Класс Кпалетте
ms.date: 11/04/2016
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
ms.openlocfilehash: 27f4f14c9e93091728e256c890dcffee26a43de4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426975"
---
# <a name="cpalette-class"></a>Класс Кпалетте

Инкапсулирует цветовую палитру Windows.

## <a name="syntax"></a>Синтаксис

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кпалетте:: Кпалетте](#cpalette)|Конструирует объект `CPalette` без присоединенной палитры Windows. Необходимо инициализировать объект `CPalette` с одной из функций элемента инициализации, прежде чем его можно будет использовать.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кпалетте:: Аниматепалетте](#animatepalette)|Заменяет записи в логической палитре, определяемой объектом `CPalette`. Приложению не нужно обновлять клиентскую область, так как Windows немедленно сопоставляет новые записи в системной палитре.|
|[Кпалетте:: Креатехалфтонепалетте](#createhalftonepalette)|Создает палитру полутонов для контекста устройства и прикрепляет ее к объекту `CPalette`.|
|[Кпалетте:: Креатепалетте](#createpalette)|Создает цветовую палитру Windows и прикрепляет ее к объекту `CPalette`.|
|[Кпалетте:: FromHandle](#fromhandle)|Возвращает указатель на `CPalette` объект при наличии маркера для объекта палитры Windows.|
|[Кпалетте:: Жетентрикаунт](#getentrycount)|Возвращает число записей палитры в логической палитре.|
|[Кпалетте:: Жетнеарестпалеттеиндекс](#getnearestpaletteindex)|Возвращает индекс записи в логической палитре, наиболее точно соответствующий значению цвета.|
|[Кпалетте:: Жетпалеттинтриес](#getpaletteentries)|Извлекает диапазон записей палитры в логической палитре.|
|[Кпалетте:: Ресизепалетте](#resizepalette)|Изменяет размер логической палитры, заданной объектом `CPalette`, на указанное число записей.|
|[Кпалетте:: Сетпалеттинтриес](#setpaletteentries)|Задает значения цвета и флаги RGB в диапазоне записей в логической палитре.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кпалетте:: operator ХПАЛЕТТЕ](#operator_hpalette)|Возвращает ХПАЛЕТТЕ, присоединенный к `CPalette`.|

## <a name="remarks"></a>Remarks

Палитра предоставляет интерфейс между приложением и устройством вывода цветов (например, устройство вывода). Интерфейс позволяет приложению воспользоваться всеми преимуществами цветовых возможностей выходного устройства, не мешая цветам, отображаемым другими приложениями. Windows использует логическую палитру приложения (список требуемых цветов) и системную палитру (которая определяет доступные цвета) для определения используемых цветов.

Объект `CPalette` предоставляет функции-члены для управления палитрой, на которую ссылается объект. Создайте объект `CPalette` и используйте его функции-члены, чтобы создать реальную палитру, объект интерфейса графических устройств (GDI) и управлять его записями и другими свойствами.

Дополнительные сведения об использовании `CPalette`см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кгдиобжект](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="animatepalette"></a>Кпалетте:: Аниматепалетте

Заменяет записи в логической палитре, прикрепленной к объекту `CPalette`.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*нстартиндекс*<br/>
Задает первую запись в палитре для анимации.

*ннументриес*<br/>
Указывает количество элементов в палитре для анимации.

*лппалеттеколорс*<br/>
Указывает на первый элемент массива структур [палеттинтри](/previous-versions/dd162769\(v=vs.85\)) для замены записей палитры, определенных *нстартиндекс* и *ннументриес*.

### <a name="remarks"></a>Remarks

Когда приложение вызывает `AnimatePalette`, ему не нужно обновлять его клиентскую область, так как Windows немедленно сопоставляет новые записи в системной палитре.

Функция `AnimatePalette` изменит только записи с флагом PC_RESERVED, установленным в соответствующем `palPaletteEntry` члене структуры [логпалетте](/windows/win32/api/wingdi/ns-wingdi-logpalette) , присоединенной к объекту `CPalette`. Дополнительные сведения об этой структуре см. в разделе ЛОГПАЛЕТТЕ в Windows SDK.

##  <a name="cpalette"></a>Кпалетте:: Кпалетте

Формирует объект `CPalette`.

```
CPalette();
```

### <a name="remarks"></a>Remarks

Объект не имеет присоединенной палитры, пока вы не вызовите `CreatePalette`, чтобы присоединить ее.

##  <a name="createhalftonepalette"></a>Кпалетте:: Креатехалфтонепалетте

Создает палитру полутонов для контекста устройства.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Определяет контекст устройства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Приложение должно создать палитру полутонов, если режим растяжения для контекста устройства установлен в ПОЛУТОНА. Логическая палитра полутонов, возвращаемая функцией-членом [креатехалфтонепалетте](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) , должна затем быть выбрана и реализована в контексте устройства перед вызовом функции [CDC:: стретчблт](../../mfc/reference/cdc-class.md#stretchblt) или [стретчдибитс](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) .

Дополнительные сведения о `CreateHalftonePalette` и `StretchDIBits`см. в Windows SDK.

##  <a name="createpalette"></a>Кпалетте:: Креатепалетте

Инициализирует объект `CPalette`, создавая логическую цветовую палитру Windows и присоединяя ее к объекту `CPalette`.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Параметры

*лплогпалетте*<br/>
Указывает на структуру [логпалетте](/windows/win32/api/wingdi/ns-wingdi-logpalette) , содержащую сведения о цветах в логической палитре.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Дополнительные сведения о структуре `LOGPALETTE` см. в Windows SDK.

##  <a name="fromhandle"></a>Кпалетте:: FromHandle

Возвращает указатель на `CPalette` объект при наличии маркера для объекта палитры Windows.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Параметры

*хпалетте*<br/>
Маркер цветовой палитры Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CPalette` в случае успеха; в противном случае — NULL.

### <a name="remarks"></a>Remarks

Если объект `CPalette` еще не присоединен к палитре Windows, создается и прикрепляется временный объект `CPalette`. Этот временный объект `CPalette` действителен только до тех пор, пока приложение не найдет время простоя в цикле событий, во время которого все временные графические объекты будут удалены. Иными словами, временный объект действителен только во время обработки одного сообщения окна.

##  <a name="getentrycount"></a>Кпалетте:: Жетентрикаунт

Вызовите эту функцию-член для получения числа записей в заданной логической палитре.

```
int GetEntryCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число записей в логической палитре.

##  <a name="getnearestpaletteindex"></a>Кпалетте:: Жетнеарестпалеттеиндекс

Возвращает индекс записи в логической палитре, наиболее точно соответствующий указанному значению цвета.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Параметры

*крколор*<br/>
Задает цвет для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Индекс записи в логической палитре. Запись содержит цвет, наиболее близкий к указанному цвету.

##  <a name="getpaletteentries"></a>Кпалетте:: Жетпалеттинтриес

Извлекает диапазон записей палитры в логической палитре.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Параметры

*нстартиндекс*<br/>
Задает первую запись в логической палитре для извлечения.

*ннументриес*<br/>
Указывает количество записей в логической палитре для извлечения.

*лппалеттеколорс*<br/>
Указывает на массив структур данных [палеттинтри](/previous-versions/dd162769\(v=vs.85\)) для получения записей палитры. Массив должен содержать по меньшей мере столько структур данных, сколько указано в *ннументриес*.

### <a name="return-value"></a>Возвращаемое значение

Число записей, полученных из логической палитры; 0, если функция завершилась ошибкой.

##  <a name="operator_hpalette"></a>Кпалетте:: operator ХПАЛЕТТЕ

Используйте этот оператор, чтобы получить прикрепленный маркер GDI Windows к объекту `CPalette`.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха — обработчик для объекта Windows GDI, представленного объектом `CPalette`; в противном случае — NULL.

### <a name="remarks"></a>Remarks

Этот оператор является оператором приведения, который поддерживает прямое использование объекта ХПАЛЕТТЕ.

Дополнительные сведения об использовании графических объектов см. в разделе [графические объекты](/windows/win32/gdi/graphic-objects) статьи Windows SDK.

##  <a name="resizepalette"></a>Кпалетте:: Ресизепалетте

Изменяет размер логической палитры, присоединенной к `CPalette` объекту, на число записей, заданное параметром *ннументриес*.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Параметры

*ннументриес*<br/>
Указывает число записей в палитре после изменения ее размера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если размер палитры успешно изменен. в противном случае — 0.

### <a name="remarks"></a>Remarks

Если приложение вызывает `ResizePalette` для уменьшения размера палитры, записи, оставшиеся в палитре с измененным размером, не меняются. Если приложение вызывает `ResizePalette` для увеличения палитры, дополнительные записи палитры устанавливаются в черный цвет (значения красного, зеленого и синего равны 0), а флаги для всех дополнительных записей устанавливаются в 0.

Дополнительные сведения о `ResizePalette`Windows API см. в разделе [ресизепалетте](/windows/win32/api/wingdi/nf-wingdi-resizepalette) в Windows SDK.

##  <a name="setpaletteentries"></a>Кпалетте:: Сетпалеттинтриес

Задает значения цвета и флаги RGB в диапазоне записей в логической палитре.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Параметры

*нстартиндекс*<br/>
Задает первую запись в логической палитре для установки.

*ннументриес*<br/>
Указывает количество записей в логической палитре, которое необходимо задать.

*лппалеттеколорс*<br/>
Указывает на массив структур данных [палеттинтри](/previous-versions/dd162769\(v=vs.85\)) для получения записей палитры. Массив должен содержать по меньшей мере столько структур данных, сколько указано в *ннументриес*.

### <a name="return-value"></a>Возвращаемое значение

Число записей, заданных в логической палитре; 0, если функция завершилась ошибкой.

### <a name="remarks"></a>Remarks

Если логическая палитра выбрана в контексте устройства, когда приложение вызывает `SetPaletteEntries`, изменения вступят в силу только после вызова приложением [CDC:: реализепалетте](../../mfc/reference/cdc-class.md#realizepalette).

Дополнительные сведения см. в разделе [палеттинтри](/previous-versions/dd162769\(v=vs.85\)) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Пример DIBLOOK в MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CGdiObject](../../mfc/reference/cgdiobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Кпалетте:: Жетпалеттинтриес](#getpaletteentries)<br/>
[Кпалетте:: Сетпалеттинтриес](#setpaletteentries)
