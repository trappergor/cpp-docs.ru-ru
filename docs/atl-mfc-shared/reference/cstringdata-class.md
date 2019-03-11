---
title: Класс CStringData
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: 5977d26cade89f2e70453d5184323958e99e54c4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748519"
---
# <a name="cstringdata-class"></a>Класс CStringData

Этот класс представляет данные строкового объекта.

## <a name="syntax"></a>Синтаксис

```
struct CStringData
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AddRef](#addref)|Увеличивает счетчик ссылок объекта строки данных.|
|[data](#data)|Возвращает символьные данные строкового объекта.|
|[Блокирована](#islocked)|Определяет, если буфер объекта соответствующий строковый блокируется.|
|[IsShared](#isshared)|Определяет, если буфер объекта связанные строки является общей.|
|[Блокировки](#lock)|Блокирует буфер объекта связанные строки.|
|[Релиз](#release)|Освобождает указанный строковый объект.|
|[разблокировать](#unlock)|Разблокирует буфер объекта связанные строки.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[nAllocLength](#nalloclength)|Длина выделенных данных в `XCHAR`s (не включая завершающий нуль-символ)|
|[nDataLength](#ndatalength)|Длина данных, используемые в текущий момент в `XCHAR`s (не включая завершающий нуль-символ)|
|[nRefs](#nrefs)|Текущий счетчик ссылок объекта.|
|[pStringMgr](#pstringmgr)|Указатель на диспетчер строки этого объекта string.|

## <a name="remarks"></a>Примечания

Этот класс должен использоваться только разработчиками, реализация диспетчеры пользовательскую строку. Дополнительные сведения о диспетчеры пользовательскую строку, см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

Этот класс инкапсулирует различные виды данных и данные, связанные с более поздней версии, строковые объекты, такие как [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), или [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) объекты. Каждый выше строковый объект содержит указатель на связанный с ним `CStringData` объектам несколько строковых объектов, чтобы он указывал тот же строковый объект данных. Эта связь представляется счетчик ссылок (`nRefs`) из `CStringData` объекта.

> [!NOTE]
>  В некоторых случаях строковый тип (например, `CFixedString`) не будет передавать объект строки данных с более чем одного выше объекта string. Дополнительные сведения об этом см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

Эти данные состоит из:

- Диспетчер памяти (типа [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) строки.

- Текущая длина ( [nDataLength](#ndatalength)) строки.

- Длина выделенного ( [nAllocLength](#nalloclength)) строки. Для повышения производительности он может отличаться от текущей длины строки

- Текущее количество ссылок ( [nRefs](#nrefs)) из `CStringData` объекта. Это значение используется в определении, сколько строковых объектов совместно `CStringData` объекта.

- Фактический символ буфера ( [данных](#data)) строки.

   > [!NOTE]
   > Фактический символ буфера объекта string, выделяется средой диспетчера строк и добавляется к `CStringData` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

##  <a name="addref"></a>  CStringData::AddRef

Увеличивает счетчик ссылок объекта string.

```
void AddRef() throw();
```

### <a name="remarks"></a>Примечания

Увеличивает счетчик ссылок объекта string.

> [!NOTE]
>  Не вызывайте этот метод для строки с отрицательным счетчик, так как отрицательное число указывает, что строковый буфер блокируется.

##  <a name="data"></a>  CStringData::data

Возвращает указатель на буфер символов строкового объекта.

```
void* data() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер символов строкового объекта.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы вернуть текущий буфер символов соответствующий строковый объект.

> [!NOTE]
>  Этот буфер не распределен `CStringData` объекта, но диспетчером строки, при необходимости. При выделении, буфер добавляется в объект строки данных.

##  <a name="islocked"></a>  CStringData::IsLocked

Определяет, если буфер символов блокируется.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если буфер заблокирован; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы определить, если буфер символов строкового объекта в данный момент заблокирована.

##  <a name="isshared"></a>  CStringData::IsShared

Определяет, если буфер символов используется совместно.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если буфер является общим; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы определить, если буфер символов строкового объекта данных в настоящее время является общим для нескольких строковых объектов.

##  <a name="lock"></a>  CStringData::Lock

Блокирует объекта соответствующий строковый буфер символов.

```
void Lock() throw();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для блокирования буфера символ объекта строки данных. Блокировка и разблокировка используется, если требуется прямой доступ к буферу символов разработчиком. Хорошим примером блокировки демонстрируется путем [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.

> [!NOTE]
>  Символьный буфер можно блокировать только в том случае, если буфер не является общим для более поздней версии строковых объектов.

##  <a name="nalloclength"></a>  CStringData::nAllocLength

Длина буфера выделенного символа.

```
int nAllocLength;
```

### <a name="remarks"></a>Примечания

Хранит длину буфера выделенные данные в `XCHAR`s (не включая завершающий нуль-символ).

##  <a name="ndatalength"></a>  CStringData::nDataLength

Текущая длина объекта string.

```
int nDataLength;
```

### <a name="remarks"></a>Примечания

Хранит длину данных, используемые в текущий момент в `XCHAR`s (не включая завершающий нуль-символ).

##  <a name="nrefs"></a>  CStringData::nRefs

Счетчик ссылок объекта строки данных.

```
long nRefs;
```

### <a name="remarks"></a>Примечания

Хранит количество ссылок на объект строки данных. Этот счетчик указывает число выше строковых объектов, которые связаны с объектом данных строки. Отрицательное значение указывает, что строковый объект данных заблокирован.

##  <a name="pstringmgr"></a>  CStringData::pStringMgr

Диспетчер памяти объекта связанные строки.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Примечания

Хранит диспетчер памяти для объекта, соответствующий строковый. Дополнительные сведения о диспетчеры памяти и строки, см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="release"></a>  CStringData::Release

Уменьшает счетчик ссылок объекта строки данных.

```
void Release() throw();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для уменьшения числа ссылок, освобождение `CStringData` структуры, если число ссылок достигает нуля. Обычно это делается, если строковый объект удаляется и поэтому больше не ссылается на объект строки данных.

Например, следующий код вызовет `CStringData::Release` для объекта строки данных, связанного с `str1`:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

##  <a name="unlock"></a>  CStringData::Unlock

Снимает блокировку на буфер символов соответствующий строковый объект.

```
void Unlock() throw();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для разблокировки буфер символов строкового объекта данных. После буфер будет разблокирован, он используется совместно, и может быть подсчетом ссылок.

> [!NOTE]
>  Каждый вызов `Lock` должна совпадать с соответствующим вызовом метода `Unlock`.

Блокировка и разблокировка используется, когда разработчик должен убедиться, что строковые данные, не будут передаваться. Хорошим примером блокировки демонстрируется путем [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) методы `CSimpleStringT`.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
