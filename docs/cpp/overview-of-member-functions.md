---
title: Общие сведения о функциях-членах | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b34be19c5fe67c087579e3d1cf0643d5afd71dc5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-member-functions"></a>Общие сведения о функциях-членах
Функции-члены являются либо статическими, либо нестатическими. Поведение статических функций-членов отличается от других функций-членов, поскольку статические функции-члены не имеют неявный **это** аргумент. Нестатические функции-члены имеют **это** указателя. Функции-члены, статические или нестатические, можно определить в объявлении класса или вне его.  
  
 Если функция-член определяется в объявлении класса, она обрабатывается как встраиваемая функция, и нет необходимости уточнять имя функции именем класса. Несмотря на то, что функции, определенные внутри объявления класса, всегда обрабатываются как подставляемые функции, можно использовать **встроенного** ключевое слово для документирования кода.  
  
 Ниже приводится пример объявления функции в объявлении класса.  
  
```  
// overview_of_member_functions1.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit within the declaration  
    //  of class Account.  
    double Deposit( double HowMuch )  
    {  
        balance += HowMuch;  
        return balance;  
    }  
private:  
    double balance;  
};  
  
int main()  
{  
}  
```  
  
 Если определение функции-члена вне объявления класса, он обрабатывается как встроенная функция, только в том случае, если он объявлен явно как **встроенного**. Кроме того, имя функции в определении должно уточняться именем класса с помощью оператора разрешения области действия (`::`).  
  
 Следующий пример идентичен предыдущему объявлению класса `Account` за исключением того, что функция `Deposit` определяется вне объявления класса.  
  
```  
// overview_of_member_functions2.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit but do not define it.  
    double Deposit( double HowMuch );  
private:  
    double balance;  
};  
  
inline double Account::Deposit( double HowMuch )  
{  
    balance += HowMuch;  
    return balance;  
}  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Хотя функции-члены можно определить внутри объявления класса или вне его, функции-члены нельзя добавить в класс после определения класса.  
  
 Классы, содержащие функции-члены, могут иметь несколько объявлений, но сами функции-члены должны иметь только одно определение в программе. При наличии нескольких определений выдается сообщение об ошибке во время компоновки. Если класс содержит определения встраиваемых функций, определения функций должны быть идентичными для соблюдения данного правила одного определения.  
  
