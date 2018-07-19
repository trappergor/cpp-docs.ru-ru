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
ms.openlocfilehash: 6223151acbce299178101735db05f7b4bd516f2f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965517"
---
# <a name="isstandardlayout-class"></a>Класс is_standard_layout

Проверяет, является ли тип стандартным макетом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Ty*|Запрашиваемый тип.|

## <a name="remarks"></a>Примечания

Экземпляр этого предиката типа содержит значение true, если тип *Ty* является классом, имеющим стандартный макет объектов-членов в памяти, в противном случае он содержит значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
