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
- CBookmark
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
ms.openlocfilehash: fb2e3ec99471405f9c6521e0b70672c1da1b755c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030145"
---
# <a name="cbookmark-class"></a>Класс CBookmark

Содержит значение закладки в свой буфер.

## <a name="syntax"></a>Синтаксис

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>Параметры

*nSize*<br/>
Размер буфера закладки в байтах. Когда *nSize* равен нулю, буфера закладки создается динамически во время выполнения.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CBookmark](#cbookmark)|Конструктор|
|[GetBuffer](#getbuffer)|Извлекает указатель на буфер.|
|[GetSize](#getsize)|Получает размер буфера в байтах.|
|[SetBookmark](#setbookmark)|Задает значение закладки.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator =](#operator)|Назначает один `CBookmark` класса в другой.|

## <a name="remarks"></a>Примечания

`CBookmark<0>` является специализацией шаблона `CBookmark`; его буфера создается динамически во время выполнения.

## <a name="cbookmark"></a> CBookmark::CBookmark

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>Параметры

*nSize*<br/>
[in] Размер буфера закладки в байтах.

### <a name="remarks"></a>Примечания

Первая функция задает буфер значение NULL, и размер буфера равным 0. Вторая функция задает размер буфера *nSize*и буфер для байтового массива *nSize* байт.

> [!NOTE]
>  Эта функция доступна только в `CBookmark<0>`.

## <a name="getbuffer"></a> CBookmark::GetBuffer

Извлекает указатель на буфер закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер закладки.

## <a name="getsize"></a> CBookmark::GetSize

Получает размер буфера закладки.

### <a name="syntax"></a>Синтаксис

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Размер буфера в байтах.

## <a name="setbookmark"></a> CBookmark::SetBookmark

Копирует значение ссылается *pBuffer* для `CBookmark` буфер и задает размер буфера *nSize*.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>Параметры

*nSize*<br/>
[in] Размер буфера закладки.

*pBuffer*<br/>
[in] Указатель на массив байтов, содержащий значение.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Эта функция доступна только в `CBookmark<0>`.

## <a name="operator"></a> CBookmark::operator =

Назначает `CBookmark` объект с другим объектом.

### <a name="syntax"></a>Синтаксис

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Примечания

Этот оператор необходим только в `CBookmark<0>`.

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)