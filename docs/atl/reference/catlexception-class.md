---
title: Класс CAtlException
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: d8ad46fa219ec29c7973677e2184e7b6d65c74b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468878"
---
# <a name="catlexception-class"></a>Класс CAtlException

Этот класс определяет ATL исключения.

## <a name="syntax"></a>Синтаксис

```
class CAtlException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|Конструктор.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlException::operator HRESULT](#operator_hresult)|Приводит текущий объект в значение HRESULT.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|Переменная типа HRESULT, созданный и используется для хранения состояния ошибки.|

## <a name="remarks"></a>Примечания

Объект `CAtlException` представляет условие исключения, связанные с ATL операции. `CAtlException` Класс включает в себя членом открытых данных, который хранит код состояния, указывающее причину исключения и оператор приведения, который позволяет обрабатывать исключение, как если бы значение HRESULT.

Как правило, вы будете вызывать `AtlThrow` вместо того чтобы создавать `CAtlException` объекта напрямую.

## <a name="requirements"></a>Требования

**Заголовок:** atlexcept.h

##  <a name="catlexception"></a>  CAtlException::CAtlException

Конструктор.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Параметры

*hr*<br/>
Код ошибки HRESULT.

##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT

Приводит текущий объект в значение HRESULT.

```
operator HRESULT() const throw ();
```

##  <a name="m_hr"></a>  CAtlException::m_hr

Элемент данных HRESULT.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Примечания

Элемент данных, который хранит условие ошибки. Значение HRESULT имеет значение с помощью конструктора [CAtlException::CAtlException](#catlexception).

## <a name="see-also"></a>См. также

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
