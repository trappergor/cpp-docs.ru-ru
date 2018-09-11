---
title: Класс aligned_storage | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::aligned_storage
dev_langs:
- C++
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aabd4a68e4ec9d9da96eff14dcf69c5bd667cc06
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107509"
---
# <a name="alignedstorage-class"></a>Класс aligned_storage

Создает должным образом выровненный тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>Параметры

*функция Len*<br/>
Размер объекта.

*Выравнивание*<br/>
Выравнивание объекта.

## <a name="remarks"></a>Примечания

Член шаблона typedef `type` является синонимом типа POD с выравниванием *выровнять* и размер *Len*. *Выровнять* должно быть равно `alignment_of<T>::value` для некоторого типа `T`, или выравниванию по умолчанию.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

typedef std::aligned_storage<sizeof (int),
    std::alignment_of<double>::value>::type New_type;
int main()
    {
    std::cout << "alignment_of<int> == "
        << std::alignment_of<int>::value << std::endl;
    std::cout << "aligned to double == "
        << std::alignment_of<New_type>::value << std::endl;

    return (0);
    }

```

```Output
alignment_of<int> == 4
aligned to double == 8
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс alignment_of](../standard-library/alignment-of-class.md)<br/>
