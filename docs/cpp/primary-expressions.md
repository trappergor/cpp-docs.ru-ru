---
title: Основные выражения
description: Первичные выражения языка программирования C++.
ms.date: 10/02/2020
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 4c52992071453bc189a3078db9592b02dfb8ba9b
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765323"
---
# <a name="primary-expressions"></a>Основные выражения

Основные выражения являются стандартными блоками более сложных выражений. Они могут быть литералами, именами и именами, дополненными оператором разрешения области ( `::` ). Основное выражение может иметь любую из следующих форм.

*`primary-expression`*\
&emsp;*`literal`*\
&emsp;**`this`**\
&emsp;*`name`*\
&emsp;**`::`** *`name`* **`(`** *`expression`* **`)`**

*`literal`* Является константным первичным выражением. Его тип зависит от формы его спецификации. Полные сведения об указании литералов см. в разделе [литералы](../cpp/numeric-boolean-and-pointer-literals-cpp.md) .

**`this`** Ключевое слово является указателем на объект класса. Он доступен в нестатических функциях члена. Он указывает на экземпляр класса, для которого была вызвана функция. **`this`** Ключевое слово не может использоваться за пределами тела функции-члена класса.

Тип **`this`** указателя — `type * const` (где `type` — имя класса) в функциях, которые не изменяют **`this`** указатель. В следующем примере показаны объявления функций членов и типы **`this`** :

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

Дополнительные сведения об изменении типа **`this`** указателя см. в разделе [ `this` указатель](this-pointer.md).

Оператор разрешения области действия ( **`::`** ), за которым следует имя, является первичным выражением.  Такие имена должны быть именами в глобальной области, а не именами членов. Тип выражения определяется объявлением имени. Это l-значение (т. е. оно может присутствовать в левой части выражения назначения), если объявляемое имя является l-значением. Оператор разрешения области действия позволяет ссылаться на глобальное имя, даже если это имя скрыто в текущей области. Пример использования оператора разрешения области действия см. в разделе [Scope](../cpp/scope-visual-cpp.md) .

Выражение, заключенное в круглые скобки, является первичным выражением. Его тип и значение идентичны типу и значению выражения, заключенного в скобки. Это l-значение, если выражение, заключенное в скобки, является l-значением.

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

Все эти примеры считаются *именами*, а также в качестве первичных выражений в различных формах:

```cpp
MyClass // an identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>См. также раздел

[Типы выражений](../cpp/types-of-expressions.md)
