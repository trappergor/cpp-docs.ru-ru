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
ms.openlocfilehash: 6da56e4d6c443520eb6f857624a5923e71a1e580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318993"
---
# <a name="catlexception-class"></a>Класс CAtlException

Этот класс определяет исключение ATL.

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
|[CAtlException::оператор HRESULT](#operator_hresult)|Отбрасывает текущий объект в значение HRESULT.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|Переменная типа HRESULT, созданная объектом и используемая для хранения состояния ошибки.|

## <a name="remarks"></a>Remarks

Объект `CAtlException` представляет условие исключения, связанное с операцией ATL. Класс `CAtlException` включает в себя общедоступный элемент данных, который хранит код статуса с указанием причины исключения, и литого оператора, который позволяет рассматривать исключение как если бы это было HRESULT.

В общем, вы `AtlThrow` будете звонить, а не создавать `CAtlException` объект напрямую.

## <a name="requirements"></a>Требования

**Заголовок:** atlexcept.h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>CAtlException::CAtlException

Конструктор.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Параметры

*Hr*<br/>
Код ошибки HRESULT.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException::оператор HRESULT

Отбрасывает текущий объект в значение HRESULT.

```
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>CAtlException::m_hr

Член данных HRESULT.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Remarks

Член данных, который хранит условие ошибки. Значение HRESULT устанавливается конструктором, [CAtlException::CAtlException](#catlexception).

## <a name="see-also"></a>См. также раздел

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
