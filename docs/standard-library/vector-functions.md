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
ms.openlocfilehash: 71594b225c950714d8b9aba169e68804033c93a2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700756"
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
