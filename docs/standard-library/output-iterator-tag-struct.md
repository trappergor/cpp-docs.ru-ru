---
title: Структура output_iterator_tag
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: 942e2214f42f97e262d4daf7836e8b6ced0e0ab2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453021"
---
# <a name="output_iterator_tag-struct"></a>Структура output_iterator_tag

Класс, предоставляющий тип возвращаемого значения для `iterator_category` функции, представляющей итератор вывода.

## <a name="syntax"></a>Синтаксис

Структура output_iterator_tag {};

## <a name="remarks"></a>Примечания

Классы категории тегов используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` `iterator_traits`< `Iterator`>  **::iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.

Тип совпадает с **итератором** \< **iter**>  **:: iterator_category** , когда `Iter` описывает объект, который может служить итератором вывода.

Этот тег не параметризуется по `value_type` или `difference_type` для итератора, как и в случае с другими тегами итератора, так как итераторы вывода не имеют ни `value_type`, ни `difference_type`.

## <a name="example"></a>Пример

Пример использования `iterator_tag`s см. в разделе [iterator_traits](../standard-library/iterator-traits-struct.md) или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
