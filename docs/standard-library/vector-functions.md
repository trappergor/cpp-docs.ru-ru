---
title: Функции &lt;vector&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: dbcb2524736bcb99693f3a4b27790c3447d58fe3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856180"
---
# <a name="ltvectorgt-functions"></a>Функции &lt;vector&gt;


## <a name="swap"></a>  swap

Меняет местами элементы двух векторов.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

`right` Вектор, предоставляющий элементы для обмена или вектор, элементы которого должны поменяться местами с элементами вектора `left`.

`left` Вектор, элементы которого должны поменяться местами с элементами вектора `right`.

### <a name="remarks"></a>Примечания

Функция шаблона является алгоритмом, который специализируется на вектор класс контейнера для выполнения функции-члена `left`. [Vector::Swap](../standard-library/vector-class.md) *(правый*). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [vector::swap](../standard-library/vector-class.md), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также

[\<vector>](../standard-library/vector.md)<br/>
