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
ms.openlocfilehash: 5915d9e25588e4e35538619662281ceaf1b35ff7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317607"
---
# <a name="cstringdata-class"></a>Класс CStringData

Этот класс представляет данные объекта строки.

## <a name="syntax"></a>Синтаксис

```
struct CStringData
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AddRef](#addref)|Приравливывает количество ссылок объекта данных строки.|
|[данные](#data)|Извлекает данные о символах объекта строки.|
|[IsLocked](#islocked)|Определяет, заблокирован ли буфер связанного объекта строки.|
|[IsShared](#isshared)|Определяет, является ли буфер связанного объекта строки в настоящее время общим.|
|[Блокировки](#lock)|Блокирует буфер связанного объекта строки.|
|[Release](#release)|Выпускает указанный объект строки.|
|[Разблокировать](#unlock)|Открывает буфер связанного объекта строки.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[nAllocДлина](#nalloclength)|Длина выделенных `XCHAR`данных в s (не включая прекращение нулевых)|
|[nDataДлина](#ndatalength)|Длина используемых `XCHAR`в настоящее время данных в s (не включая прекращение нулевых)|
|[nРефы](#nrefs)|Текущий подсчет ссылок объекта.|
|[pStringMgr](#pstringmgr)|Указатель на строку менеджера этого объекта строки.|

## <a name="remarks"></a>Remarks

Этот класс должен использоваться только разработчиками, реализующими пользовательские строки менеджеров. Для получения дополнительной информации о пользовательских менеджеров строк, [см. Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

Этот класс инкапсулирует различные типы информации и данных, связанных с более высоким объектом строки, такие как [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), или [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) объектов. Каждый объект выше строки содержит `CStringData` указатель на связанный с ним объект, что позволяет нескольким объектам строки указывать на один и тот же объект данных строки. Это отношение представлено подсчетом`nRefs`ссылок `CStringData` () объекта.

> [!NOTE]
> В некоторых случаях тип строки `CFixedString`(например) не будет совместно с объектом данных строки делиться с более чем одним объектом выше строки. Для получения дополнительной информации об этом, [см. Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

Эти данные состоят из:

- Менеджер памяти (типа [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) строки.

- Текущая длина [(nDataLength](#ndatalength)) строки.

- Выделенная длина [(nAllocLength](#nalloclength)) строки. По причинам производительности это может отличаться от текущей длины строки

- Текущее значение отсчета ссылок `CStringData` [(nRefs](#nrefs)) объекта. Это значение используется при определении количества объектов `CStringData` строки, разделяющих один и тот же объект.

- Фактический буфер символов [(данные](#data)) строки.

   > [!NOTE]
   > Фактический буфер символов объекта строки выделяется диспетчером строки и пригоден к объекту. `CStringData`

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

## <a name="cstringdataaddref"></a><a name="addref"></a>CStringData::AddRef

Приравливывает количество ссылок объекта строки.

```
void AddRef() throw();
```

### <a name="remarks"></a>Remarks

Приравливывает количество ссылок объекта строки.

> [!NOTE]
> Не вызывайте этот метод на строке с отрицательным подсчетом ссылок, так как отрицательное количество указывает на то, что буфер строки заблокирован.

## <a name="cstringdatadata"></a><a name="data"></a>CStringData::data

Возвращает указатель в буфер символов объекта строки.

```
void* data() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер символов объекта строки.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы вернуть текущий буфер символов связанного объекта строки.

> [!NOTE]
> Этот буфер выделяется `CStringData` не объектом, а менеджером строки, когда это необходимо. При выделении буфер пригожен к объекту данных строки.

## <a name="cstringdataislocked"></a><a name="islocked"></a>CStringData::Заблокировано

Определяет, заблокирован ли буфер символов.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если буфер заблокирован; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вызов ими функции, чтобы определить, заблокирован ли буфер символов объекта строки.

## <a name="cstringdataisshared"></a><a name="isshared"></a>CStringData::IsShared

Определяет, является ли буфер символов общим.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если буфер является общим; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы определить, является ли буфер символов объекта данных строки в настоящее время общим между несколькими объектами строки.

## <a name="cstringdatalock"></a><a name="lock"></a>CStringData::Lock

Блокирует буфер символов связанного объекта строки.

```
void Lock() throw();
```

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы заблокировать буфер символов объекта данных строки. Блокировка и разблокировка используется, когда разработчик требует прямого доступа к буферу символов. Хороший пример блокировки демонстрируется методами `CSimpleStringT` [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer.](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)

> [!NOTE]
> Буфер символов может быть заблокирован только в том случае, если буфер не разделен между более высокими объектами строки.

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a>CStringData::nAllocДлина

Длина выделенного буфера символов.

```
int nAllocLength;
```

### <a name="remarks"></a>Remarks

Хранит длину выделенного буфера данных в `XCHAR`s (не включая прекращение нулевых).

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a>CStringData::nDataДлина

Текущая длина объекта строки.

```
int nDataLength;
```

### <a name="remarks"></a>Remarks

Хранит длину используемых `XCHAR`в настоящее время данных в s (не включая прекращение нулевых).

## <a name="cstringdatanrefs"></a><a name="nrefs"></a>CStringData::nRefs

Количество ссылок на объект данных строки.

```
long nRefs;
```

### <a name="remarks"></a>Remarks

Хранит количество ссылок объекта данных строки. Это число указывает количество более высоких объектов строки, которые связаны с объектом данных строки. Отрицательное значение указывает на то, что объект данных строки в настоящее время заблокирован.

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a>CStringData::pStringMgr

Менеджер памяти связанного объекта строки.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Remarks

Хранит диспетчер амдозапас амагентства памяти для связанного объекта строки. Для получения дополнительной информации об менеджерах памяти и строках [см. Управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringdatarelease"></a><a name="release"></a>CStringData::Release

Декретирует количество ссылок на объект данных строки.

```
void Release() throw();
```

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы decrement подсчет ссылок, освобождая структуру, `CStringData` если количество ссылок достигает нуля. Обычно это делается при удалении объекта строки, и поэтому больше не нужно ссылаться на объект данных строки.

Например, следующий код `CStringData::Release` будет вызывать объект `str1`строки данных, связанный с:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a>CStringData::Разблокировка

Открывает буфер символов связанного объекта строки.

```
void Unlock() throw();
```

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы разблокировать буфер символов объекта данных строки. Как только буфер разблокирован, он является пригодным для общего обмена и может быть отсчитан.

> [!NOTE]
> Каждый `Lock` вызов должен быть сопоставлен `Unlock`с соответствующим вызовом.

Блокировка и разблокировка используется, когда разработчик должен убедиться, что данные строки не будут общими. Хороший пример блокировки демонстрируется методами `CSimpleStringT` [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) и [UnlockBuffer.](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
