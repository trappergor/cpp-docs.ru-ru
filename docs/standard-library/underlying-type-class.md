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
ms.openlocfilehash: 4f45af807b37294b87920b6fabac18647f170025
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853226"
---
# <a name="underlyingtype-class"></a>Класс underlying_type

Создает базовый целочисленный тип для типа перечисления.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Параметры

`T` Тип для изменения.

## <a name="remarks"></a>Примечания

Определение типа члена `type` для класса шаблона задает имя базового целочисленного типа `T`, где `T` имеет тип перечисления, в противном случае определение типа члена `type` отсутствует.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
