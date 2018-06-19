---
title: Класс type_info | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- type_info
dev_langs:
- C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3e3138c9028f72327c9d4bf2c2f2e82c942dbde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422440"
---
# <a name="typeinfo-class"></a>Класс type_info
**Type_info** класс содержит сведения о типе, созданного компилятором в программе. Объекты этого класса эффективно сохраняют указатель на имя для типа. **Type_info** также хранит кодированное значение, подходящее для сравнения двух типов на равенство или порядок сортировки. Правила кодирования и последовательность размещения типов не указаны и могут различаться в разных программах.  
  
 `<typeinfo>` Заголовочный файл должен быть включен для использования **type_info** класса. Интерфейс для **type_info** класс:  
  
```cpp
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 Не удается создать экземпляр объекта **type_info** класса напрямую, поскольку этот класс имеет только закрытый конструктор копии. Единственный способ построения (временного) **type_info** необходимо использовать [typeid](../cpp/typeid-operator.md) оператор. Так как оператор присваивания также является закрытым, невозможно копировать или присвоить объекты класса **type_info**.  
  
 **type_info::hash_code** определяет хэш-функцией для сопоставления значений типа **typeinfo** распределение значений индекса.  
  
 Операторы `==` и `!=` может использоваться для сравнения на равенство и неравенство с другими **type_info** объектов, соответственно.  
  
 Нет связи между порядком размещения типов и отношениями наследования. Используйте **type_info::before** функции-члена для определения типов упорядоченной последовательности. Нет никакой гарантии, **type_info::before** даст одинаковый результат в разных программах или даже в разных запусках той же программы. Таким образом **type_info::before** похож на адрес объекта **(&)** оператор.  
  
 **Type_info::name** функция-член возвращает **const char\***  символом null строку, представляющая понятное имя типа. Указываемая память кэшируется. Ее никогда не следует освобождать напрямую.  
  
 **Type_info::raw_name** функция-член возвращает **const char\***  в строку, завершающуюся значением null, оформленное название типа объекта. Имя фактически хранится в оформленном виде с целью экономии пространства. Следовательно, эта функция выполняется быстрее, чем **type_info::name** , так как его не нужно декорированное имя. Строка, возвращаемая функцией **type_info::raw_name** функция полезна в операциях сравнения, но недоступен для чтения. Если вам требуется читаемую пользователем строку, используйте **type_info::name** вместо этого функцию.  
  
 Сведения о типе создаются для полиморфных классов, только если [/GR (включить информацию о типах времени выполнения)](../build/reference/gr-enable-run-time-type-information.md) указан параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Сведения о типах среды выполнения](../cpp/run-time-type-information.md)
