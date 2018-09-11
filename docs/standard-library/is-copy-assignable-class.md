---
title: Класс is_copy_assignable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 863c842fe3d5635848b569ad0cad6dad0556e302
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102542"
---
# <a name="iscopyassignable-class"></a>Класс is_copy_assignable

Проверяет, может ли тип быть скопирован при присвоении значения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим оператора назначения копий, в противном случае он содержит значение false. Эквивалентно is_assignable\<Ty&, const Ty&>.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
