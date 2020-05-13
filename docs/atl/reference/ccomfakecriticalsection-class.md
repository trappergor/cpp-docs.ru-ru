---
title: CComFakeCriticalSection класс
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 4a5b9ba3551397a9c3d59a343e9c6b55b1c1207e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327852"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection класс

Этот класс предоставляет те же методы, что и [CComCriticalSection,](../../atl/reference/ccomcriticalsection-class.md) но не предоставляет критический раздел.

## <a name="syntax"></a>Синтаксис

```
class CComFakeCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|Ничего не делает, так как нет критического раздела.|
|[CComFakeCriticalSection::Lock](#lock)|Ничего не делает, так как нет критического раздела.|
|[CComFakeCriticalSection::Срок](#term)|Ничего не делает, так как нет критического раздела.|
|[CComFakeCriticalSection::Разблокировка](#unlock)|Ничего не делает, так как нет критического раздела.|

## <a name="remarks"></a>Remarks

`CComFakeCriticalSection`зеркала методы, найденные в [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем `CComFakeCriticalSection` не менее, не предоставляет критический раздел; поэтому его методы ничего не делают.

Как правило, `CComFakeCriticalSection` вы `typedef` используете `AutoCriticalSection` `CriticalSection`через имя, либо . При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), оба этих `typedef` названия ссылки. `CComFakeCriticalSection` При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), они ссылаются [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection`, соответственно.

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>CComFakeCriticalSection::Init

Ничего не делает, так как нет критического раздела.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CComFakeCriticalSection::Lock

Ничего не делает, так как нет критического раздела.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CComFakeCriticalSection::Срок

Ничего не делает, так как нет критического раздела.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComFakeCriticalSection::Разблокировка

Ничего не делает, так как нет критического раздела.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
