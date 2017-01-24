---
title: "Оператор typeid | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid - оператор"
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор typeid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## Заметки  
 Оператор `typeid` позволяет определить тип объекта во время выполнения.  
  
 Результат `typeid` — это **const type\_info&**.  Значение представляет собой ссылку на объект **type\_info**, который представляет собой *идентификатор\-типа* или тип *выражение* в зависимости от используемой формы `typeid`.  См. дополнительные сведения в разделе [Класс type\_info](../cpp/type-info-class.md).  
  
 Оператор `typeid` не работает с управляемыми типами \(абстрактными деклараторами или экземплярами\). См. сведения о получении <xref:System.Type> заданного типа в разделе [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md).  
  
 Оператор `typeid` выполняет проверку во время выполнения, если применяется к l\-значению полиморфного типа классов, где невозможно определить истинный тип объекта на основании предоставленной статической информации.  К таким случаям относятся следующие.  
  
-   Ссылка на класс  
  
-   Указатель, ссылка на который удалена с помощью \*  
  
-   Указатель индекса \(например, \[ \]\). \(Обратите внимание, что, как правило, небезопасно использовать индекс с указателем на полиморфный тип.\)  
  
 Если *выражение* указывает на тип базового класса, а объект, фактически, является типом, извлеченным из базового класса, результатом является ссылка **type\_info** для производного класса.  *Выражение* должно указывать на полиморфный тип \(класс с виртуальными функциями\).  В противном случае результатом является **type\_info** для статического класса, на который ссылается *выражение*.  Более того, необходимо отменить ссылку на указатель, чтобы использовать объект, на который указывает этот указатель.  Если не удалить ссылку на указатель, результатом будет **type\_info** для указателя, а не объекта, на который он указывает.  Например:  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 Если *выражение* удаляет ссылку на указатель и значение этого указателя — нуль, **идентификатор\-типа** создает исключение [bad\_typeid](../cpp/bad-typeid-exception.md).  Если указатель не указывает на допустимый объект, вызывается исключение `__non_rtti_object`, обозначая попытку проанализировать RTTI, вызвавший ошибку \(например, нарушение прав доступа\), поскольку объект в какой\-то степени не действителен \(недопустимый указатель или код, который не был скомпилирован с использованием параметра [\/GR](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md)\).  
  
 Если *выражение* — ни указатель, ни ссылка на базовый класс объекта, результатом является ссылка **type\_info**, представляющая статический тип *выражение*.  *Статический тип* выражения относится к типу выражения в том виде, в котором оно существует во время компиляции.  Семантика исполнения игнорируется при оценке статического типа выражения.  Кроме того, ссылки по возможности игнорируются при определении статического типа выражения:  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **Идентификатор\-типа** также можно использовать в шаблонах для определения типа параметра шаблона:  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## См. также  
 [Сведения о типах времени выполнения](../Topic/Run-Time%20Type%20Information.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)