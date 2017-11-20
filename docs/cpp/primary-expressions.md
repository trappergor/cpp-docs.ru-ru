---
title: "Первичные выражения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 980be1e393fab633f3417dcc250c1820def3ff90
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="primary-expressions"></a>Первичные выражения
Основные выражения являются стандартными блоками более сложных выражений. Это литералы, имена и имена, уточняемые с помощью оператора разрешения области действия (`::`).  Основное выражение может иметь любую из следующих форм.  
  
```  
  
      literal  
      this  
:: namename( expression )  
```  
  
 Объект *литерала* — это постоянное основное выражение. Его тип зависит от формы его спецификации. В разделе [литералы](../cpp/numeric-boolean-and-pointer-literals-cpp.md) полные сведения об определении литералов.  
  
 **Это** ключевое слово является указателем на объект класса. Он доступен в нестатических функциях-членах и указывает на экземпляр класса, для которого была вызвана функция. **Это** ключевое слово не может использоваться вне тела функции-члена класса.  
  
 Тип **это** указатель `type`  **\*const** (где `type` — это имя класса) внутри функций, не изменяющих **этот** указателя. В следующем примере показано член объявления функций и типов **это**:  
  
```  
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
  
 В разделе [этот указатель](this-pointer.md) Дополнительные сведения об изменении типа **это** указателя.  
  
 Оператор разрешения области действия (`::`), за которым следует имя, составляет основное выражение.  Такие имена должны быть именами в глобальной области, а не именами членов.  Тип данного выражения определяется с помощью объявления имени. Это l-значение (то есть оно может отображаться слева от выражения оператора присваивания), если объявляющее имя является l-значением. Оператор разрешения области действия позволяет ссылаться на глобальное имя, даже если это имя скрыто в текущей области. В разделе [область](../cpp/scope-visual-cpp.md) пример использования оператора разрешения области действия.  
  
 Выражение, заключенное в круглые скобки, является основным выражением, тип и значение которого идентичны типу и значению выражения, не заключенного в круглые скобки. Это l-значение, если выражение, не заключенное в круглые скобки, является l-значением.  
  
 В контексте синтаксис основное выражение, приведенном выше *имя* означает, что-либо в синтаксис, описанный для [имена](http://msdn.microsoft.com/en-us/1c49cc24-08d5-4884-b170-ba8ed42d80db), даже если с помощью оператора разрешения области действия перед именем типа имен который может встречаться только в классе не допускаются.  К ним относятся имена функций пользовательского преобразования и имена деструкторов.  
  
 Ниже приводятся примеры основных выражений.  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 В приведенных ниже примерах считаются *имена*и поэтому первичные выражения, в различных формах:  
  
```  
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