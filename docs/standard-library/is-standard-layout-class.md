---
title: Класс is_standard_layout
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 4f999eaa4a5c1ea7e9672a5efdc6000a4d3d9759
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457417"
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
|*Ty*|Запрашиваемый тип.|

## <a name="remarks"></a>Примечания

Экземпляр этого предиката типа содержит значение true, если тип *Ty* является классом, имеющим стандартный макет объектов-членов в памяти, в противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
