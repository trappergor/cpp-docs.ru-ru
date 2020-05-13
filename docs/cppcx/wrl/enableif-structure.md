---
title: EnableIf - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 44c6293b56e9e03c23d0d8cebf2a112e6fcf3664
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214036"
---
# <a name="enableif-structure"></a>EnableIf - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип.

*b*<br/>
Логическое выражение.

## <a name="remarks"></a>Remarks

Определяет элемент данных типа, заданного вторым параметром шаблона, если первый параметр шаблона имеет **значение true**.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Открытые определения типов

|Имя|Description|
|----------|-----------------|
|`type`|Если параметру шаблона *b* присвоено **значение true**, то частичная специализация определяет `type` элементов данных как тип `T`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EnableIf`

## <a name="requirements"></a>Требования

**Заголовок:** internal. h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)
