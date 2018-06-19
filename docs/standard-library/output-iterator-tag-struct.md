---
title: Структура output_iterator_tag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::output_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8d340f79e5442f22b09f801fd3040c09ce00a45
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853473"
---
# <a name="outputiteratortag-struct"></a>Структура output_iterator_tag

Класс, предоставляющий тип возвращаемого значения для функции **iterator_category**, которая представляет собой итератор вывода.

## <a name="syntax"></a>Синтаксис

Структура output_iterator_tag {};

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` категория `iterator_traits`< `Iterator`> **::iterator_category** должна быть определена как наиболее точный тег категории, который описывает поведение итератора.

Тип является таким же, как **итератор**\< **Iter**> **::iterator_category**, когда **Iter** описывает объект, который может быть итератором вывода.

Этот тег не параметризуется по `value_type` или `difference_type` для итератора, как и в случае с другими тегами итератора, так как итераторы вывода не имеют ни `value_type`, ни `difference_type`.

## <a name="example"></a>Пример

См. разделы [iterator_traits](../standard-library/iterator-traits-struct.md) или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) с примерами использования тегов **iterator_tag**.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
