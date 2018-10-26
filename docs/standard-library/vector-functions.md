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
ms.openlocfilehash: c93f535bb02cbaa1f688fba84f15d832381156c6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079323"
---
# <a name="ltvectorgt-functions"></a>Функции &lt;vector&gt;

## <a name="swap"></a>  swap

Меняет местами элементы двух векторов.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Вектор, предоставляющий элементы для обмена местами, или вектор, элементы которого должны быть заменены вектора *левой*.

*left*<br/>
Вектор, элементы которого должны быть заменены вектора *правой*.

### <a name="remarks"></a>Примечания

Функция-шаблон является алгоритмом, специализированным на векторе класса контейнера для выполнения функции-члена `left`. [Vector::Swap](../standard-library/vector-class.md) *(правом*). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [vector::swap](../standard-library/vector-class.md), в котором используется версия шаблона `swap`.

## <a name="see-also"></a>См. также

[\<vector>](../standard-library/vector.md)<br/>
