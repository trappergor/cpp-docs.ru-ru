---
title: Структура bidirectional_iterator_tag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a04265a68a03edc9f957161991d2ddd91a8e6096
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958183"
---
# <a name="bidirectionaliteratortag-struct"></a>Структура bidirectional_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функцию, которая представляет собой Двунаправленный итератор.

## <a name="syntax"></a>Синтаксис

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точную категорию своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator`, `iterator_traits`< `Iterator`>:: **iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип — так же, как **итератор** \< **Iter**>:: **iterator_category** при `Iter` описывает объект, который можно использовать в качестве двунаправленный итератор.

## <a name="example"></a>Пример

Пример использования `bidirectional_iterator_tag` см. в разделе [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
