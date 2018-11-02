---
title: Структура forward_iterator_tag
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 04d526e7778dc219a8d9a49db40751b4418cc82d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434259"
---
# <a name="forwarditeratortag-struct"></a>Структура forward_iterator_tag

Класс, предоставляющий тип возвращаемого значения для функции **iterator_category**, которая представляет собой прямой итератор.

## <a name="syntax"></a>Синтаксис

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Примечания

Классы тегов категории используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` `iterator_traits`< `Iterator`> **::iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип является таким же, как **итератор**\< **Iter**> **::iterator_category**, когда **Iter** описывает объект, который может быть прямым итератором.

## <a name="example"></a>Пример

См. в разделе [iterator_traits](../standard-library/iterator-traits-struct.md) или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) пример использования **iterator_tag**.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура input_iterator_tag](../standard-library/input-iterator-tag-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
