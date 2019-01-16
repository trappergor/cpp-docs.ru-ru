---
title: MixIn - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: d0306f4c497dd26e782b1ef2c012cb7d348db07f
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336767"
---
# <a name="mixin-structure"></a>MixIn - структура

Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>Параметры

*Производные*<br/>
Тип, производный от [реализует](implements-structure.md) структуры.

*MixInType*<br/>
Базовый тип.

*hasImplements*<br/>
**значение true,** Если *MixInType* является производным от текущей реализации базового типа; **false** в противном случае.

## <a name="remarks"></a>Примечания

Если класс является производным от среды выполнения Windows и интерфейсов класса модели COM, список объявления класса сначала должен перечислить все интерфейсы среды выполнения Windows, и затем любой классического COM интерфейсы. **MixIn** гарантирует, что интерфейсы будут указаны в правильном порядке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MixIn`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)