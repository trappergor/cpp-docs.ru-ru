---
title: Класс type_info
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: b0cddd2c5cc09e77e8733ca88177c3b2223fc8ce
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242091"
---
# <a name="typeinfo-class"></a>Класс type_info

**Type_info** класс содержит сведения о типе, создаваемой в рамках программы компилятором. Объекты этого класса эффективно сохраняют указатель на имя для типа. **Type_info** также хранит кодированное значение, подходящее для сравнения двух типов на равенство или порядок сортировки. Правила кодирования и последовательность размещения типов не указаны и могут различаться в разных программах.

`<typeinfo>` Заголовочный файл должен быть включен для использования **type_info** класса. Интерфейс для **type_info** класс является:

```cpp
class type_info {
public:
    type_info(const type_info& rhs) = delete; // cannot be copied
    virtual ~type_info();
    size_t hash_code() const;
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    type_info& operator=(const type_info& rhs) = delete; // cannot be copied
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    size_t hash_code() const noexcept;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

Не удается создать экземпляр объекта **type_info** класса напрямую, поскольку этот класс имеет только закрытый конструктор копии. Единственный способ построения (временного) **type_info** объекта заключается в использовании [typeid](../cpp/typeid-operator.md) оператор. Так как оператор присваивания также является закрытым, нельзя копировать или присвоить объекты класса **type_info**.

`type_info::hash_code` Определяет хэш-функцией для сопоставления значений типа **typeinfo** с распределением значений индекса.

Операторы `==` и `!=` может использоваться для сравнения на равенство и неравенство с другими **type_info** соответственно.

Нет связи между порядком размещения типов и отношениями наследования. Используйте `type_info::before` функцию-член для определения последовательности размещения типов. Нет никакой гарантии, `type_info::before` даст тот же результат, в разных программах или даже в разных запусках той же программы. Таким образом `type_info::before` аналогичен взятия адреса `(&)` оператор.

`type_info::name` Функция-член возвращает `const char*` для нулем строка, представляющая понятное имя типа. Указываемая память кэшируется. Ее никогда не следует освобождать напрямую.

`type_info::raw_name` Функция-член возвращает `const char*` на заканчивающуюся нулем строку, оформленное название типа объекта. Имя фактически хранится в оформленном виде с целью экономии пространства. Следовательно, эта функция выполняется быстрее, чем `type_info::name` поскольку она не требует отмены оформления имени. Строка, возвращаемая `type_info::raw_name` функция полезна в операциях сравнения, но недоступен для чтения. Если вам требуется удобное для восприятия строку, используйте `type_info::name` вместо этого функцию.

Сведения о типе для полиморфных классов, только если создается [/GR (включить сведения о типе времени выполнения)](../build/reference/gr-enable-run-time-type-information.md) указан параметр компилятора.

## <a name="see-also"></a>См. также

[Сведения о типах среды выполнения](../cpp/run-time-type-information.md)