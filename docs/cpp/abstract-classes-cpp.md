---
title: "Абстрактные классы (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], abstract
- base classes, abstract classes
- abstract classes
- derived classes, abstract classes
ms.assetid: f0c5975b-39de-4d68-9640-6ce57f4632e6
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d8ee7473b77f943c4f9958dabb0baa4998c284f4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="abstract-classes-c"></a>Абстрактные классы (C++)
Абстрактные классы используются в качестве обобщенных концепций, на основе которых можно создавать более конкретные производные классы. Невозможно создать объект типа абстрактного класса; однако можно использовать указатели и ссылки на типы абстрактного класса.  
  
 Класс, содержащий хотя бы одну чисто виртуальную функцию, считается абстрактным. Классы, производные от абстрактного класса, должны реализовывать чисто виртуальную функцию; в противном случае они также будут абстрактными.  
  
 Виртуальная функция объявлена как «чистая» с помощью *чистый спецификатор* синтаксис (описано в [реализация протокола класса](http://msdn.microsoft.com/en-us/a319f1b3-05e8-400e-950a-1ca6eb105ab5)). Рассмотрим пример, представленный в [виртуальные функции](../cpp/virtual-functions.md). Класс `Account` создан для того, чтобы предоставлять общие функции, но объекты типа `Account` имеют слишком общий характер для практического применения. Таким образом, класс `Account` является хорошим кандидатом в абстрактный класс:  
  
```  
// deriv_AbstractClasses.cpp  
// compile with: /LD  
class Account {  
public:  
   Account( double d );   // Constructor.  
   virtual double GetBalance();   // Obtain balance.  
   virtual void PrintBalance() = 0;   // Pure virtual function.  
private:  
    double _balance;  
};  
  
```  
  
 Единственное различие между этим и предыдущим объявлениями состоит в том, что функция `PrintBalance` объявлена со спецификатором чисто виртуальной функции pure (`= 0`).  
  
## <a name="restrictions-on-abstract-classes"></a>Ограничения на использование абстрактных классов  
 Абстрактные классы невозможно использовать для следующих элементов:  
  
-   переменных и данных членов;  
  
-   типов аргументов;  
  
-   типов возвращаемых функциями значений;  
  
-   типов явных преобразований.  
  
 Другое ограничение состоит в том, что при вызове конструктором абстрактного класса чистой виртуальной функции (прямо или косвенно) результат будет неопределенным. Однако конструкторы и деструкторы абстрактных классов могут вызывать другие функции-члены.  
  
 Для абстрактных классов можно определять чистые виртуальные функции, но вызывать их можно только непосредственно с использованием следующего синтаксиса:  
  
 *Имя абстрактного класса* `::` *имя функции***)**  
  
 Это помогает при разработке иерархий классов, базовые классы которых содержат чистые виртуальные деструкторы, поскольку деструкторы базовых классов всегда вызываются в процессе удаления объекта. Рассмотрим следующий пример.  
  
```  
// Declare an abstract base class with a pure virtual destructor.  
// deriv_RestrictionsonUsingAbstractClasses.cpp  
class base {  
public:  
    base() {}  
    virtual ~base()=0;  
};  
  
// Provide a definition for destructor.  
base::~base() {}  
  
class derived:public base {  
public:  
    derived() {}  
    ~derived(){}  
};  
  
int main() {  
    derived *pDerived = new derived;  
    delete pDerived;  
}  
```  
  
 При удалении объекта, указанного с помощью `pDerived`, сначала вызывается деструктор класса `derived`, а затем — деструктор класса `base`. Пустая реализация чистой виртуальной функции гарантирует наличие хотя бы некоторой реализации для функции.  
  
> [!NOTE]
>  В предыдущем примере чистая виртуальная функция `base::~base` вызывается неявно из `derived::~derived`. Чистые виртуальные функции можно также вызывать явно, используя полное имя функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Наследование](../cpp/inheritance-cpp.md)
