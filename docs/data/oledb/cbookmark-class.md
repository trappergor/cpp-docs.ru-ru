---
title: Класс CBookmark
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: d3d82ea09b7ed2c1cbaf325906b4f9b480e1eb4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359333"
---
# <a name="cbookmark-class"></a>Класс CBookmark

Удерживает значение закладки в буфере.

## <a name="syntax"></a>Синтаксис

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Параметры

*Nsize*<br/>
Размер буфера закладки в байтах. Когда *nSize* равен нулю, буфер закладок будет динамически создан во время выполнения.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CBookmark](#cbookmark)|Конструктор|
|[GetBuffer](#getbuffer)|Извлекает указатель в буфер.|
|[GetSize](#getsize)|Извлекает размер буфера в байтах.|
|[SetBookmark](#setbookmark)|Устанавливает значение закладки.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор](#operator)|Назначает один `CBookmark` класс другому.|

## <a name="remarks"></a>Remarks

`CBookmark<0>`является шаблоном специализации `CBookmark`; его буфер динамически создается во время выполнения.

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a>CBookmark::CBookmark

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Параметры

*Nsize*<br/>
(в) Размер буфера закладки в байтах.

### <a name="remarks"></a>Remarks

Первая функция устанавливает буфер NULL, а размер буфера - до 0. Вторая функция устанавливает размер буфера для *nSize,* а буфер к массиву байт *байтов nSize.*

> [!NOTE]
> Эта функция доступна `CBookmark<0>`только в .

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a>CBookmark::GetBuffer

Извлекает указатель в буфер закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер закладки.

## <a name="cbookmarkgetsize"></a><a name="getsize"></a>CBookmark::GetSize

Извлекает размер буфера закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Размер буфера в байтах.

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a>CBookmark::SetBookmark

Копирует значение закладки, на `CBookmark` которую ссылается *pBuffer,* в буфер и устанавливает размер буфера для *nSize.*

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Параметры

*Nsize*<br/>
(в) Размер буфера закладки.

*pBuffer*<br/>
(в) Указатель на массив байта, содержащий значение закладки.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Эта функция доступна `CBookmark<0>`только в .

## <a name="cbookmarkoperator-"></a><a name="operator"></a>CBookmark::оператор

Назначает `CBookmark` объект другому.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Remarks

Этот оператор нужен `CBookmark<0>`только в .

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[СПРАВКа о потребительских шаблонах OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
