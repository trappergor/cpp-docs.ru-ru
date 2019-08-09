---
title: Структура input_iterator_tag
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 47e0d08f79cfa41c414ac4fcd570ce8fdfbd0b35
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455320"
---
# <a name="inputiteratortag-struct"></a>Структура input_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей итератор ввода.

## <a name="syntax"></a>Синтаксис

Структура input_iterator_tag {};

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` `iterator_traits`< `Iterator`>  **::iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип совпадает с **итератором** \< **iter**>  **:: iterator_category** , когда `Iter` описывает объект, который может выступать в качестве итератора ввода.

## <a name="example"></a>Пример

Пример [](../standard-library/iterator-traits-struct.md) использования `iterator_tag`s см. в разделе iterator_traits или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
