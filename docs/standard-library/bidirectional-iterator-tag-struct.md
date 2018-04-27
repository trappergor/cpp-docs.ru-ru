---
title: Структура bidirectional_iterator_tag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 800968993b874070ccc32baf91e8feec3e01e472
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="bidirectionaliteratortag-struct"></a>Структура bidirectional_iterator_tag

Класс, предоставляющий тип возвращаемого значения для функции **iterator_category**, которая представляет собой двунаправленный итератор.

## <a name="syntax"></a>Синтаксис

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точную категорию своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator`, `iterator_traits`< `Iterator`>:: **iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип является таким же, как **iterator**\< **Iter**>:: **iterator_category**, где **Iter** описывает объект, который может служить как двунаправленный итератор.

## <a name="example"></a>Пример

Пример использования `bidirectional_iterator_tag` см. в разделе [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
