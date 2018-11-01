---
title: CloakedIid - структура
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 7340032e91a9b30b72099477b55b88740b3eb68f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535308"
---
# <a name="cloakediid-structure"></a>CloakedIid - структура

Указывает `RuntimeClass`, `Implements` и `ChainInterfaces` шаблоны, что заданный интерфейс недоступен в списке IID.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Интерфейс, который является скрытым (замаскированные).

## <a name="remarks"></a>Примечания

Ниже приведен пример того, как **CloakedIid** используется: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`CloakedIid`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)