---
title: Класс CGdiObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 097d2a636ae277f2391815f531464ed5ee10571f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398200"
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
|[CGdiObject::CGdiObject](#cgdiobject)|Создает объект `CGdiObject`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::Attach](#attach)|Присоединяет объект Windows GDI для `CGdiObject` объекта.|
|[CGdiObject::CreateStockObject](#createstockobject)|Извлекает дескриптор Windows предопределенные акций перья, кисти или шрифты.|
|[CGdiObject::DeleteObject](#deleteobject)|Удаляет объект Windows GDI присоединен к `CGdiObject` объект из памяти, освобождая все хранилища системы, связанный с объектом.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|Удаляет все временные `CGdiObject` объекты, создаваемые `FromHandle`.|
|[CGdiObject::Detach](#detach)|Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор объекта Windows GDI.|
|[CGdiObject::FromHandle](#fromhandle)|Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.|
|[CGdiObject::GetObject](#getobject)|Заполняет буфер с данными, который описывает объект Windows GDI подключен к `CGdiObject` объекта.|
|[CGdiObject::GetObjectType](#getobjecttype)|Извлекает тип объекта GDI.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|Возвращает `m_hObject` Если **это** имеет значение NULL, в котором возвращается вариантов значение NULL.|
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Сбрасывает происхождение кисти или сбрасывает логической палитры.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::operator! =](#operator_neq)|Определяет, если два объекта GDI логически не равны.|
|[CGdiObject::operator ==](#operator_eq_eq)|Определяет, логически равны ли два объекта GDI.|
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Извлекает ДЕСКРИПТОР в присоединенном объекте Windows GDI.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|МАРКЕР, содержащий HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN или HFONT присоединен к этому объекту.|

## <a name="remarks"></a>Примечания

Никогда не создаст `CGdiObject` напрямую. Вместо этого объект создается из одного из его производных классов, таких как `CPen` или `CBrush`.

Дополнительные сведения о `CGdiObject`, см. в разделе [графические объекты](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="attach"></a>  CGdiObject::Attach

Присоединяет объект Windows GDI для `CGdiObject` объекта.

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
ДЕСКРИПТОР Windows объект GDI (например, HPEN или HBRUSH).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если вложение выполнено успешно; в противном случае 0.

##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject

Создает объект `CGdiObject`.

```
CGdiObject();
```

### <a name="remarks"></a>Примечания

Никогда не создаст `CGdiObject` напрямую. Вместо этого объект создается из одного из его производных классов, таких как `CPen` или `Cbrush`.

##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject

Извлекает дескриптор один из предопределенных акций Windows GDI перья, кисти или шрифты и присоединяет объект GDI для `CGdiObject` объекта.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Константа, задающая тип требуемого объекта акций. См. параметр *fnObject* для [GetStockObject](/windows/desktop/api/wingdi/nf-wingdi-getstockobject) в пакете SDK для Windows, описание соответствующие значения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызов этой функции с помощью одного из производных классов, которые соответствует тип объектов Windows GDI, таким как `CPen` для биржевой пера.

##  <a name="deleteobject"></a>  CGdiObject::DeleteObject

Удаляет присоединенный объект Windows GDI из памяти, освобождая все хранилища системы, связанный с объектом Windows GDI.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект GDI был успешно удален; в противном случае 0.

### <a name="remarks"></a>Примечания

Хранилище, связанное с `CGdiObject` этот вызов не влияет на объект. Приложение не должно вызывать `DeleteObject` на `CGdiObject` объект, который выбран в данный момент в контексте устройства.

При удалении шаблона кисти, растровое изображение, связанное с кистью не удаляется. Растровое изображение необходимо удалять по отдельности.

##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap

Автоматически вызывается `CWinApp` обработчиком времени простоя, `DeleteTempMap` удаляет все временные `CGdiObject` объекты, создаваемые `FromHandle`.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Примечания

`DeleteTempMap` Отсоединяет объект Windows GDI, присоединенный к временным `CGdiObject` объекта перед удалением `CGdiObject` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

##  <a name="detach"></a>  CGdiObject::Detach

Отсоединяет объект Windows GDI из `CGdiObject` объекта и возвращает дескриптор объекта Windows GDI.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `HANDLE` для Windows GDI объекта отсоединена; в противном случае — значение NULL, если объект GDI не подключен.

##  <a name="fromhandle"></a>  CGdiObject::FromHandle

Возвращает указатель на `CGdiObject` объект, заданный дескриптор в объект Windows GDI.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
ДЕСКРИПТОР объекта Windows GDI.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CGdiObject` , может быть временным или постоянным.

### <a name="remarks"></a>Примечания

Если `CGdiObject` объект еще не присоединен к объекту Windows GDI, временный `CGdiObject` созданный и присоединенный объект.

Этот временный `CGdiObject` объект действителен только до следующей встречи, в приложении есть время простоя в свой цикл событий, после чего будут удалены все временные графические объекты. Другими словами — это что временный объект допустима только во время обработки сообщения одного окна.

##  <a name="getobject"></a>  CGdiObject::GetObject

Заполняет буфер данных, который определяет указанный объект.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>Параметры

*nCount*<br/>
Указывает число байтов для копирования в *lpObject* буфера.

*lpObject*<br/>
Указывает на буфер, предоставленные пользователем, для получения информации.

### <a name="return-value"></a>Возвращаемое значение

Число байтов, полученных; в противном случае 0 когда возникает ошибка.

### <a name="remarks"></a>Примечания

Функция возвращает структуру данных, тип которого зависит от типа графического объекта, как показано в следующем списке:

|Object|Тип буфера|
|------------|-----------------|
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|
|`CFont`|[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)|
|`CBitmap`|[ТОЧЕЧНЫЙ РИСУНОК](../../mfc/reference/bitmap-structure.md)|
|`CPalette`|WORD|
|`CRgn`|Не поддерживается|

Если объект является `CBitmap` объекта, `GetObject` возвращает только ширину, высоту и цвет сведения о формате растрового изображения. Число битов могут быть получены с помощью [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).

Если объект является `CPalette` объекта, `GetObject` извлекает слово, которое указывает количество записей в палитре. Функция не извлекает [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) структура, определяющая палитры. Приложение может получить сведения о записи палитр, вызвав [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).

##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType

Извлекает тип объекта GDI.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип объекта, если выполнение прошло успешно; в противном случае 0. Он может иметь одно из следующих значений:

- OBJ_BITMAP растрового изображения

- OBJ_BRUSH кисти

- OBJ_FONT шрифта

- Палитра OBJ_PAL

- OBJ_PEN пера

- Расширенные OBJ_EXTPEN пера

- OBJ_REGION регион

- Контекст устройства OBJ_DC

- Контекста устройства памяти OBJ_MEMDC

- OBJ_METAFILE метафайл

- Контексте устройства метафайла OBJ_METADC

- OBJ_ENHMETAFILE расширенного метафайла

- Контекст устройства OBJ_ENHMETADC расширенный метафайл

##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle

Возвращает `m_hObject` Если **это** имеет значение NULL, в котором возвращается вариантов значение NULL.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

ДЕСКРИПТОР Windows GDI в присоединенном объекте; в противном случае — значение NULL, если объект не присоединен.

### <a name="remarks"></a>Примечания

Это является частью подход к пользовательскому интерфейсу общие дескриптор и полезно, если NULL является допустимым или специальных значение для дескриптора.

### <a name="example"></a>Пример

  См. в примере [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).

##  <a name="m_hobject"></a>  CGdiObject::m_hObject

МАРКЕР, содержащий HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE или HFONT присоединен к этому объекту.

```
HGDIOBJ m_hObject;
```

##  <a name="operator_neq"></a>  CGdiObject::operator! =

Определяет, если два объекта GDI логически не равны.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Указатель на существующий `CGdiObject`.

### <a name="remarks"></a>Примечания

Определяет, если объект GDI слева не равно объект GDI справа от оператора.

##  <a name="operator_eq_eq"></a>  CGdiObject::operator ==

Определяет, логически равны ли два объекта GDI.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Ссылка на существующий `CGdiObject`.

### <a name="remarks"></a>Примечания

Определяет, эквивалентен ли объект GDI с левой стороны объект GDI справа от оператора.

##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ

Извлекает ДЕСКРИПТОР присоединенный объект Windows GDI; в противном случае — значение NULL, если объект не присоединен.

```
operator HGDIOBJ() const;
```

##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject

Сбрасывает происхождение кисти или сбрасывает логической палитры.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Хотя `UnrealizeObject` является функцией-членом из `CGdiObject` класс, он должен вызываться только в `CBrush` или `CPalette` объектов.

Для `CBrush` объектов, `UnrealizeObject` направлена на Сброс начала заданного кисти в следующий раз, он выбран в контексте устройства. Если объект является `CPalette` объекта, `UnrealizeObject` указывает, что система для реализации палитры, как будто он был не ранее было удовлетворено. В следующий раз, приложение вызывает [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) функция для указанного палитры, система полностью указывает логическую палитру для системной палитры.

`UnrealizeObject` Функции не следует использовать с объектами акций. `UnrealizeObject` Функция должна вызываться всякий раз, когда новый источник кисти имеет значение (с помощью параметра [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) функции). `UnrealizeObject` Функция не должна вызываться для выбранной кисти или выбранного палитру для любого контекста отображения.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CBitmap](../../mfc/reference/cbitmap-class.md)<br/>
[Класс CBrush](../../mfc/reference/cbrush-class.md)<br/>
[Класс CFont](../../mfc/reference/cfont-class.md)<br/>
[Класс CPalette](../../mfc/reference/cpalette-class.md)<br/>
[Класс CPen](../../mfc/reference/cpen-class.md)<br/>
[Класс CRgn](../../mfc/reference/crgn-class.md)
