---
title: Структура intput_iterator_tag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::input_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95e2713f3c73a3dc35c11be8d245ede94b2c3bba
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953983"
---
# <a name="inputiteratortag-struct"></a>Структура input_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функцию, которая представляет собой итератор ввода.

## <a name="syntax"></a>Синтаксис

Структура input_iterator_tag {};

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
