---
title: Класс is_trivially_copyable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: d3062ae311b63be76ba07185f4f8173afa4229cc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459748"
---
# <a name="istriviallycopyable-class"></a>Класс is_trivially_copyable

Проверяет, является ли тип тривиально копируемым.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является тривиальным копированием, в противном случае — значение false. Тривиально копируемые типы не имеют нетривиальных операций копирования, операций перемещения и деструкторов. Как правило, операция копирования считается тривиальной, если она может быть реализована как побитовое копирование. Встроенные типы и массивы тривиально копируемых типов являются тривиально копируемыми.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
