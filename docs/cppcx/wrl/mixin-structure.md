---
title: Структура MixIn
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: b302d6e08e401a24b465508d5ddabcae8b16bd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213699"
---
# <a name="mixin-structure"></a>Структура MixIn

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

*Получает*<br/>
Тип, производный от структуры [Implements](implements-structure.md) .

*миксинтипе*<br/>
Базовый тип.

*хасимплементс*<br/>
**значение true** , если *миксинтипе* является производным от текущей реализации базового типа. в противном случае — **значение false** .

## <a name="remarks"></a>Remarks

Если класс является производным от среда выполнения Windows и COM-интерфейсов класса, список объявлений класса должен сначала отобразить все интерфейсы среда выполнения Windows, а затем — любые классические COM-интерфейсы. **Примеси** гарантирует, что интерфейсы указываются в правильном порядке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MixIn`

## <a name="requirements"></a>Требования

**Заголовок:** Implements. h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
