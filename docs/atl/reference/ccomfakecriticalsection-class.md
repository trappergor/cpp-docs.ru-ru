---
title: Класс CComFakeCriticalSection
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
ms.openlocfilehash: 39a9859380eba1b72768234eb8f43d80fca0143f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302147"
---
# <a name="ccomfakecriticalsection-class"></a>Класс CComFakeCriticalSection

Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критический раздел.

## <a name="syntax"></a>Синтаксис

```
class CComFakeCriticalSection
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|Не выполняет никаких действий, так как отсутствует критический раздел.|
|[CComFakeCriticalSection::Lock](#lock)|Не выполняет никаких действий, так как отсутствует критический раздел.|
|[CComFakeCriticalSection::Term](#term)|Не выполняет никаких действий, так как отсутствует критический раздел.|
|[CComFakeCriticalSection::Unlock](#unlock)|Не выполняет никаких действий, так как отсутствует критический раздел.|

## <a name="remarks"></a>Примечания

`CComFakeCriticalSection` зеркально отражает методы, найденные в [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем не менее `CComFakeCriticalSection` не поддерживает критической секции; таким образом, ничего не делать его методы.

Как правило, используется `CComFakeCriticalSection` через `typedef` имя, либо `AutoCriticalSection` или `CriticalSection`. При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), оба этих `typedef` имена ссылок `CComFakeCriticalSection`. При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), если они ссылаются на [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection`, соответственно.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="init"></a>  CComFakeCriticalSection::Init

Не выполняет никаких действий, так как отсутствует критический раздел.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="lock"></a>  CComFakeCriticalSection::Lock

Не выполняет никаких действий, так как отсутствует критический раздел.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="term"></a>  CComFakeCriticalSection::Term

Не выполняет никаких действий, так как отсутствует критический раздел.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock

Не выполняет никаких действий, так как отсутствует критический раздел.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
