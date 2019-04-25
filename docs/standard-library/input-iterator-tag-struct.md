---
title: Структура input_iterator_tag
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 5478a8f9fa6013202a1ea8dd838eedb80b9c367e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159255"
---
# <a name="inputiteratortag-struct"></a>Структура input_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функцию, которая представляет собой итератор ввода.

## <a name="syntax"></a>Синтаксис

struct input_iterator_tag {};

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` `iterator_traits`< `Iterator`> **::iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип — так же, как **итератор** \< **Iter**> **:: iterator_category** при `Iter` описывает объект, который можно использовать в качестве итератор ввода.

## <a name="example"></a>Пример

См. в разделе [iterator_traits](../standard-library/iterator-traits-struct.md) или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) пример демонстрирует использование `iterator_tag`s.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
