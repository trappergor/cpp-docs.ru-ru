---
title: Структура bidirectional_iterator_tag
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: bab2664fcb552a72baa032d719cf6b0141ffe525
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456627"
---
# <a name="bidirectionaliteratortag-struct"></a>Структура bidirectional_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей двунаправленный итератор.

## <a name="syntax"></a>Синтаксис

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точную категорию своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator`, `iterator_traits`< `Iterator`>:: **iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Этот тип совпадает с итератором  \< **iter**>:: **iterator_category** , когда `Iter` описывает объект, который может использоваться в качестве двунаправленного итератора.

## <a name="example"></a>Пример

Пример использования `bidirectional_iterator_tag` см. в разделе [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
