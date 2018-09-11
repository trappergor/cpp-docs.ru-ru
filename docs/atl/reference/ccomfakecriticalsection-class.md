---
title: Класс CComFakeCriticalSection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48b120b7be3e605b6ed2619cbd71011b0a693bdc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757280"
---
# <a name="ccomfakecriticalsection-class"></a>Класс CComFakeCriticalSection

Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критический раздел.

## <a name="syntax"></a>Синтаксис

```
class CComFakeCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
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
