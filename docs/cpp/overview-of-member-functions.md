---
title: Общие сведения о функциях-членах.
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: d1c3e069325363276e58a617d6ba21cb0b6e4ff0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188471"
---
# <a name="overview-of-member-functions"></a>Общие сведения о функциях-членах.

Функции-члены являются либо статическими, либо нестатическими. Поведение статических функций-членов отличается от других функций-членов, так как статические функции-члены не имеют неявного **этого** аргумента. Нестатические функции-члены имеют **этот** указатель. Функции-члены, статические или нестатические, можно определить в объявлении класса или вне его.

Если функция-член определяется в объявлении класса, она обрабатывается как встраиваемая функция, и нет необходимости уточнять имя функции именем класса. Хотя функции, определенные внутри объявлений класса, уже обрабатываются как встроенные функции, для документирования кода можно использовать **встроенное** ключевое слово inline.

Ниже приводится пример объявления функции в объявлении класса.

```cpp
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

Если определение функции-члена находится вне объявления класса, оно рассматривается как встроенная функция только в том случае, если она явно объявлена как **Встроенная**. Кроме того, имя функции в определении должно уточняться именем класса с помощью оператора разрешения области действия (`::`).

Следующий пример идентичен предыдущему объявлению класса `Account` за исключением того, что функция `Deposit` определяется вне объявления класса.

```cpp
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
