---
title: Класс CGdiObject
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: 0cd7a0e0ed500ee9394b00e8906640e9f950163b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373740"
---
# <a name="cgdiobject-class"></a>Класс CGdiObject

Предоставляет базовый класс для различных типов объектов интерфейса графических устройств Windows (GDI), таких как растровые изображения, области, кисти, перья, палитры и шрифты.

## <a name="syntax"></a>Синтаксис

```
class CGdiObject : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|Формирует объект `CGdiObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::Прикрепите](#attach)|Прикрепляет объект GDI `CGdiObject` Windows к объекту.|
|[CGdiObject::CreateStockObject](#createstockobject)|Извлекает ручку на одну из предопределенных пакетов, кистей или шрифтов Windows.|
|[CGdiObject::DeleteObject](#deleteobject)|Удаляет объект Windows GDI, прикрепленный к `CGdiObject` объекту, из памяти, освобождая все системные хранилища, связанные с объектом.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Удаляет любые `CGdiObject` временные `FromHandle`объекты, созданные .|
|[CGdiObject::Detach](#detach)|Отсоединяет объект GDI Windows от `CGdiObject` объекта и возвращает ручку объекту GDI Windows.|
|[CGdiObject::FromHandle](#fromhandle)|Возвращает указатель объекту, `CGdiObject` данной рукоятке объекту GDI Windows.|
|[CGdiObject::GetObject](#getobject)|Заполняет буфер данными, описывающие объект Windows GDI, прикрепленный к объекту. `CGdiObject`|
|[CGdiObject::GetObjectType](#getobjecttype)|Извлекает тип объекта GDI.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Возвращает, `m_hObject` если **это** не NULL, и в этом случае NULL возвращается.|
|[CGdiObject::UnrealiseObject](#unrealizeobject)|Сбрасывает происхождение кисти или сбрасывает логическую палитру.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::оператор !](#operator_neq)|Определяет, являются ли два объекта GDI логически не равными.|
|[CGdiObject::оператор](#operator_eq_eq)|Определяет, являются ли два объекта GDI логически равными.|
|[CGdiObject:оператор HGDIOBJ](#operator_hgdiobj)|Извлекает HANDLE на прилагаемый объект Windows GDI.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|К этому объекту прилагается HANDLE, содержащий HBITMAP, Hpalette, HRGN, HBRUSH, HPEN или HFONT.|

## <a name="remarks"></a>Remarks

Вы никогда `CGdiObject` не создаете непосредственно. Скорее, вы создаете объект из одного из `CPen` `CBrush`его производных классов, таких как или .

Для получения `CGdiObject`дополнительной информации о, см. [Graphic Objects](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cgdiobjectattach"></a><a name="attach"></a>CGdiObject::Прикрепите

Прикрепляет объект GDI `CGdiObject` Windows к объекту.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
HANDLE к объекту GDI Windows (например, HPEN или HBRUSH).

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вложение успешно; в противном случае 0.

## <a name="cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>CGdiObject::CGdiObject

Формирует объект `CGdiObject`.

```
CGdiObject();
```

### <a name="remarks"></a>Remarks

Вы никогда `CGdiObject` не создаете непосредственно. Скорее, вы создаете объект из одного из `CPen` `Cbrush`его производных классов, таких как или .

## <a name="cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>CGdiObject::CreateStockObject

Извлекает ручку к одной из предопределенных пакетов, кистей или шрифтов Windows, а `CGdiObject` также прикрепляет объект GDI к объекту.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Постоянная указание типа желаемого объекта акций. Ознакомьтесь с параметром *fnObject* для [GetStockObject](/windows/win32/api/wingdi/nf-wingdi-getstockobject) в SDK Windows для описания соответствующих значений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Вызовите эту функцию с одним из производных классов, который `CPen` соответствует типу объекта Windows GDI, например, для стоковой ручки.

## <a name="cgdiobjectdeleteobject"></a><a name="deleteobject"></a>CGdiObject::DeleteObject

Удаляет прилагаемый объект Windows GDI из памяти, освободив все системное хранилище, связанное с объектом Windows GDI.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Возвращаемое значение

Незерно, если объект GDI был успешно удален; в противном случае 0.

### <a name="remarks"></a>Remarks

Хранилище, связанное `CGdiObject` с объектом, не зависит от этого вызова. Приложение не должно `DeleteObject` вызывать `CGdiObject` объект, который в настоящее время выбран в контексте устройства.

При удалении кисти шаблона битная карта, связанная с кистью, не удаляется. Бит-карта должна быть удалена самостоятельно.

## <a name="cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>CGdiObject::DeleteTempMap

Вызывается автоматически `CWinApp` обработчиком `DeleteTempMap` простоя, `CGdiObject` удаляет `FromHandle`любые временные объекты, созданные .

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Remarks

`DeleteTempMap`отсоединяет объект Windows GDI, прикрепленный `CGdiObject` к временному объекту, `CGdiObject` перед удаляя объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

## <a name="cgdiobjectdetach"></a><a name="detach"></a>CGdiObject::Detach

Отсоединяет объект GDI Windows от `CGdiObject` объекта и возвращает ручку объекту GDI Windows.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Возвращаемое значение

A `HANDLE` к объекту Windows GDI отделен; в противном случае NULL, если ни один объект GDI не прилагается.

## <a name="cgdiobjectfromhandle"></a><a name="fromhandle"></a>CGdiObject::FromHandle

Возвращает указатель объекту, `CGdiObject` данной рукоятке объекту GDI Windows.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
HANDLE к объекту GDI Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CGdiObject` который может быть временным или постоянным.

### <a name="remarks"></a>Remarks

Если `CGdiObject` объект еще не подключен к объекту Windows `CGdiObject` GDI, создается и прикрепляется временный объект.

Этот `CGdiObject` временный объект действителен только до следующего времени, когда приложение будет проходить время простоя в цикле событий, после чего все временные графические объекты удаляются. Другой способ сказать это заключается в том, что временный объект действителен только при обработке одного окна сообщения.

## <a name="cgdiobjectgetobject"></a><a name="getobject"></a>CGdiObject::GetObject

Заполняет буфер данными, определяющими указанный объект.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Параметры

*Ncount*<br/>
Определяет количество байтов для копирования в буфер *lpObject.*

*lpObject*<br/>
Указывает на буфер, поставляемый пользователем, который должен получать информацию.

### <a name="return-value"></a>Возвращаемое значение

Количество полученных байтов; в противном случае 0, если происходит ошибка.

### <a name="remarks"></a>Remarks

Функция извлекает структуру данных, тип которой зависит от типа графического объекта, как показано в следующем списке:

|Объект|Тип буфера|
|------------|-----------------|
|`CPen`|[ЛОГПЕН](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[ЛОГБРУШ](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[ЛОГФОНТ](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[Растрового изображения](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|Не поддерживается|

Если объект является `CBitmap` объектом, `GetObject` возвращается только ширина, высота и цветовая информация о формате битной карты. Фактические биты можно получить с помощью [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Если объект является `CPalette` объектом, `GetObject` получает СЯО, которое определяет количество записей в палитре. Функция не получает структуру [LOGPALETTE,](/windows/win32/api/wingdi/ns-wingdi-logpalette) определяющую палитру. Приложение может получить информацию о палитры записей, позвонив [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).

## <a name="cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>CGdiObject::GetObjectType

Извлекает тип объекта GDI.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип объекта, в случае успеха; в противном случае 0. Он может иметь одно из следующих значений:

- OBJ_BITMAP Битмап

- кисть OBJ_BRUSH

- шрифт OBJ_FONT

- OBJ_PAL палитра

- OBJ_PEN пен

- OBJ_EXTPEN расширенная ручка

- OBJ_REGION регион

- контекст OBJ_DC устройства

- контекст устройства OBJ_MEMDC памяти

- OBJ_METAFILE Метафили

- OBJ_METADC контексте устройства Metafile

- OBJ_ENHMETAFILE Улучшенный метафайл

- OBJ_ENHMETADC контексте улучшенного метафайла

## <a name="cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>CGdiObject::GetSafeHandle

Возвращает, `m_hObject` если **это** не NULL, и в этом случае NULL возвращается.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

HANDLE к присоединенному объекту Windows GDI; в противном случае NULL, если объект не прилагается.

### <a name="remarks"></a>Remarks

Это является частью общей парадигмы интерфейса ручки и полезно, когда NULL является действительным или специальное значение для ручки.

### <a name="example"></a>Пример

  Смотрите пример [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

## <a name="cgdiobjectm_hobject"></a><a name="m_hobject"></a>CGdiObject::m_hObject

К этому объекту прилагается HANDLE, содержащий HBITMAP, HRGN, HBRUSH, HPEN, Hpalette или HFONT.

```
HGDIOBJ m_hObject;
```

## <a name="cgdiobjectoperator-"></a><a name="operator_neq"></a>CGdiObject::оператор !

Определяет, являются ли два объекта GDI логически не равными.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Указатель на существующий `CGdiObject`.

### <a name="remarks"></a>Remarks

Определяет, если объект GDI на левой стороне не равна объекту GDI на правой стороне.

## <a name="cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>CGdiObject::оператор

Определяет, являются ли два объекта GDI логически равными.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Ссылка на `CGdiObject`существующую .

### <a name="remarks"></a>Remarks

Определяет, является ли объект GDI на левой стороне равным объекту GDI с правой стороны.

## <a name="cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>CGdiObject:оператор HGDIOBJ

Извлекает HANDLE на присоединенный объект Windows GDI; в противном случае NULL, если объект не прилагается.

```
operator HGDIOBJ() const;
```

## <a name="cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>CGdiObject::UnrealiseObject

Сбрасывает происхождение кисти или сбрасывает логическую палитру.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Хотя `UnrealizeObject` функция члена `CGdiObject` класса является членом, она `CBrush` должна `CPalette` вызываться только на или объекты.

Для `CBrush` объектов `UnrealizeObject` система направляет для сбросить происхождение данной кисти при следующем выборе в контекст устройства. Если объект является `CPalette` объектом, `UnrealizeObject` направляет систему для реализации палитры, как если бы она ранее не была реализована. В следующий раз приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) функции для указанной палитры, система полностью переотображает логическую палитру в системной палитре.

Функция `UnrealizeObject` не должна использоваться с фондовыми объектами. Функция `UnrealizeObject` должна вызываться всякий раз, когда устанавливается новое происхождение кисти (с помощью функции [CDC::SetBrushOrg).](../../mfc/reference/cdc-class.md#setbrushorg) Функция `UnrealizeObject` не должна вызываться для выбранной в настоящее время кисти или выбранной в настоящее время палитры любого контекста отображения.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBitmap](../../mfc/reference/cbitmap-class.md)<br/>
[Класс CBrush](../../mfc/reference/cbrush-class.md)<br/>
[Класс CFont](../../mfc/reference/cfont-class.md)<br/>
[Класс CPalette](../../mfc/reference/cpalette-class.md)<br/>
[Класс CPen](../../mfc/reference/cpen-class.md)<br/>
[Класс CRgn](../../mfc/reference/crgn-class.md)
