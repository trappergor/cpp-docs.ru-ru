---
title: CloakedIid - структура
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 10dc2af1897147045382e8463b6602fa015fc899
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033727"
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

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)