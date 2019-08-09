---
title: Структура hash (Стандартная библиотека C++) | Документы Майкрософт
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: e6d0cea7bfc8cd745e7276f7fc29d493f178fc9b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451953"
---
# <a name="hash-structure-c-standard-library"></a>Структура hash (Стандартная библиотека C++)

Определяет функцию-член, возвращающую значение, которое уникально определяется с помощью `Val`. Функция-член определяет функцию [hash](../standard-library/hash-class.md), которую можно использовать для сопоставления значений типа `thread::id` с распределением значений индекса.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;

};
```

## <a name="requirements"></a>Требования

**Заголовок:** \<> потоков

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)\
[Структура unary_function](../standard-library/unary-function-struct.md)
