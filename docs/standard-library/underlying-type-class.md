---
title: Класс underlying_type | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b3f796d5039900b591c219c840d1aef94d23e8f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957585"
---
# <a name="underlyingtype-class"></a>Класс underlying_type

Создает базовый целочисленный тип для типа перечисления.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Параметры

*T*  
 Тип для изменения.

## <a name="remarks"></a>Примечания

`type` Определение типа члена класса шаблонов называет базового целочисленного типа *T*, когда *T* является типом перечисления, в противном случае будет не член typedef `type`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
