---
title: Класс RemoveIUnknown
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 3b54f6a3072d82d40db4ac698503f0939e745472
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036777"
---
# <a name="removeiunknown-class"></a>Класс RemoveIUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс.

## <a name="remarks"></a>Примечания

Создает тип, эквивалентный базовому типу `IUnknown`, но имеющий невиртуальные функции-члены `QueryInterface`, `AddRef` и `Release`.

По умолчанию методы модели COM предоставляют виртуальные `QueryInterface`, `AddRef`, и `Release` методы. Однако для `ComPtr` не требуется нагрузка, связанная с виртуальными методами. `RemoveIUnknown` исключает эту нагрузку, предоставляя закрытые невиртуальные `QueryInterface`, `AddRef`, и `Release` методы.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`ReturnType`|Синоним для типа, которое эквивалентно значению параметра-шаблона *T* , но имеющий невиртуальные `IUnknown` членов.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)