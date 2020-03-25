---
title: Класс type_info
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 7a016fe8fee4e5765e6172184bfa9c90eecbc687
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160675"
---
# <a name="type_info-class"></a>Класс type_info

Класс **type_info** описывает сведения о типах, созданные в программе компилятором. Объекты этого класса эффективно сохраняют указатель на имя для типа. Класс **type_info** также хранит закодированное значение, пригодное для сравнения двух типов на равенство или порядок сортировки. Правила кодирования и последовательность размещения типов не указаны и могут различаться в разных программах.

Для использования класса **type_info** необходимо добавить файл заголовка `<typeinfo>`. Интерфейс для класса **type_info** :

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

Нельзя напрямую создавать экземпляры объектов класса **type_info** , так как класс имеет только закрытый конструктор копии. Единственный способ создать (временный) объект **type_info** — использовать оператор [typeid](../cpp/typeid-operator.md) . Поскольку оператор присваивания также является закрытым, нельзя копировать или назначать объекты класса **type_info**.

`type_info::hash_code` определяет хэш-функцию, подходящую для сопоставления значений типа **typeInfo** с распределением значений индекса.

Операторы `==` и `!=` можно использовать для сравнения на равенство и неравенство с другими **type_infoными** объектами соответственно.

Нет связи между порядком размещения типов и отношениями наследования. Используйте функцию члена `type_info::before`, чтобы определить порядок сортировки типов. Нет никакой гарантии, что `type_info::before` выдаст тот же результат в разных программах или даже в разных запусках одной программы. Таким образом, `type_info::before` аналогичен оператору address-of `(&)`.

Функция-член `type_info::name` возвращает `const char*` в строку, завершающуюся нулем, представляющую понятное имя типа. Указываемая память кэшируется. Ее никогда не следует освобождать напрямую.

Функция-член `type_info::raw_name` возвращает `const char*` с завершающим нулем строкой, представляющей декорированное имя типа объекта. Имя фактически хранится в оформленном виде с целью экономии пространства. Следовательно, эта функция работает быстрее, чем `type_info::name`, так как ей не нужно размечать имя. Строка, возвращаемая функцией `type_info::raw_name`, полезна в операциях сравнения, но недоступна для чтения. Если требуется читаемая строка, используйте функцию `type_info::name`.

Сведения о типе для полиморфизма создаются только в том случае, если указан параметр компилятора [/GR (включить сведения о типе времени выполнения)](../build/reference/gr-enable-run-time-type-information.md) .

## <a name="see-also"></a>См. также раздел

[Сведения о типах среды выполнения](../cpp/run-time-type-information.md)
