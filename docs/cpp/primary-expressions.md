---
title: Основные выражения
ms.date: 11/04/2016
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 03f0d0d04ad8ef2b052b9303d15437c53369a003
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177629"
---
# <a name="primary-expressions"></a>Основные выражения

Основные выражения являются стандартными блоками более сложных выражений. Это литералы, имена и имена, уточняемые с помощью оператора разрешения области действия (`::`).  Основное выражение может иметь любую из следующих форм.

```
literal
this
name
::name ( expression )
```

*Литерал* является константным первичным выражением. Его тип зависит от формы его спецификации. Полные сведения об указании литералов см. в разделе [литералы](../cpp/numeric-boolean-and-pointer-literals-cpp.md) .

Ключевое слово **this** является указателем на объект класса. Он доступен в нестатических функциях-членах и указывает на экземпляр класса, для которого была вызвана функция. Ключевое слово **this** не может использоваться за пределами тела функции-члена класса.

**Этот** указатель имеет тип `type` **\*const** (где `type` является именем класса) в функциях, не изменяющих **этот** указатель специально. В следующем примере показаны объявления функций и типы **этого**элемента:

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

Дополнительные сведения об изменении **типа указателя см** . в [этом указателе](this-pointer.md) .

Оператор разрешения области действия (`::`), за которым следует имя, составляет основное выражение.  Такие имена должны быть именами в глобальной области, а не именами членов.  Тип данного выражения определяется с помощью объявления имени. Это l-значение (то есть оно может отображаться слева от выражения оператора присваивания), если объявляющее имя является l-значением. Оператор разрешения области действия позволяет ссылаться на глобальное имя, даже если это имя скрыто в текущей области. Пример использования оператора разрешения области действия см. в разделе [Scope](../cpp/scope-visual-cpp.md) .

Выражение, заключенное в круглые скобки, является основным выражением, тип и значение которого идентичны типу и значению выражения, не заключенного в круглые скобки. Это l-значение, если выражение, не заключенное в круглые скобки, является l-значением.

Ниже приводятся примеры основных выражений.

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

В приведенных ниже примерах рассматриваются *имена*и, следовательно, основные выражения в различных формах:

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>См. также раздел

[Типы выражений](../cpp/types-of-expressions.md)
