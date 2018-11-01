---
title: Первичные выражения
ms.date: 11/04/2016
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: e7dcb8290c0130fa9376e48f065e82163a1ca5b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677582"
---
# <a name="primary-expressions"></a>Первичные выражения

Основные выражения являются стандартными блоками более сложных выражений. Это литералы, имена и имена, уточняемые с помощью оператора разрешения области действия (`::`).  Основное выражение может иметь любую из следующих форм.

```
literal
this
name
::name ( expression )
```

Объект *литерала* — это основное константное выражение. Его тип зависит от формы его спецификации. См. в разделе [литералы](../cpp/numeric-boolean-and-pointer-literals-cpp.md) полные сведения об определении литералов.

**Это** ключевое слово представляет собой указатель на объект класса. Он доступен в нестатических функциях-членах и указывает на экземпляр класса, для которого была вызвана функция. **Это** ключевое слово не может использоваться вне тела функции-члена класса.

Тип **это** указатель находится `type`  **\*const** (где `type` — это имя класса) внутри функции, не изменяющих **этот** указатель. В следующем примере показано член объявления функций и типов **это**:

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

См. в разделе [этот указатель](this-pointer.md) Дополнительные сведения об изменении типа **это** указатель.

Оператор разрешения области действия (`::`), за которым следует имя, составляет основное выражение.  Такие имена должны быть именами в глобальной области, а не именами членов.  Тип данного выражения определяется с помощью объявления имени. Это l-значение (то есть оно может отображаться слева от выражения оператора присваивания), если объявляющее имя является l-значением. Оператор разрешения области действия позволяет ссылаться на глобальное имя, даже если это имя скрыто в текущей области. См. в разделе [область](../cpp/scope-visual-cpp.md) пример того, как использовать оператор разрешения области действия.

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

В приведенных ниже примерах считаются *имена*и поэтому основными выражениями, представленными в различных формах:

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>См. также

[Типы выражений](../cpp/types-of-expressions.md)