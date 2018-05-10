---
title: Класс is_standard_layout | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d899d9c56ecc8b27b18498de225bbba6f0d110d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="isstandardlayout-class"></a>Класс is_standard_layout

Проверяет, является ли тип стандартным макетом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Ty`|Запрашиваемый тип.|

## <a name="remarks"></a>Примечания

Экземпляр этого предиката типа содержит значение true, если тип `Ty` является классом, имеющим стандартный макет объектов-членов; в противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
