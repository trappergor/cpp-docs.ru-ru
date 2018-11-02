---
title: Класс type_index
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 8807a041ab1c6ef47a9c3c12dac2688f121f6cfa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650496"
---
# <a name="typeindex-class"></a>Класс type_index

Класс `type_index` оборачивает указатель в [класс type_info](../cpp/type-info-class.md) для упрощения индексации такими объектами.

class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };

Конструктор инициализирует `ptr` в `&tinfo`.

`name` возвращает `ptr->name()`.

`hash_code` возвращает `ptr->hash_code().`

`operator==` возвращает `*ptr == right.ptr`.

`operator!=` возвращает `!(*this == right)`.

`operator<` возвращает `*ptr->before(*right.ptr)`.

`operator<=` возвращает `!(right < *this).`

`operator>` возвращает `right < *this`.

`operator>=` возвращает `!(*this < right)`.

## <a name="see-also"></a>См. также

[Сведения о типах среды выполнения](../cpp/run-time-type-information.md)<br/>
[\<typeindex>](../standard-library/typeindex.md)<br/>
