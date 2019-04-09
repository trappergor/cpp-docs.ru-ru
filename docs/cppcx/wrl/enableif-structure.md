---
title: EnableIf - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: daaba919acaa35615af56831f9458831c3d35427
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029989"
---
# <a name="enableif-structure"></a>EnableIf - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

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
Выражение типа Boolean.

## <a name="remarks"></a>Примечания

Определяет данные-член типа, указанного в качестве второго параметра шаблона, если первый параметр шаблона, результатом которого является **true**.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`type`|Если параметр шаблона *b* принимает значение **true**, частичная специализация определяет данные-член `type` типа `T`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EnableIf`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)