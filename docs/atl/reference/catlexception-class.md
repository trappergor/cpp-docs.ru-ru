---
title: Класс CAtlException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56038ffe4c6062422ea34a439e73b0d90a37cfb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097735"
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
