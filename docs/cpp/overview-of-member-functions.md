---
title: Общие сведения о функциях-членах
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: 6dec4ee53cd840c47d76ac0579daca710b0eeb68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358409"
---
# <a name="overview-of-member-functions"></a>Общие сведения о функциях-членах

Функции-члены являются либо статическими, либо нестатическими. Поведение функций статических членов отличается от других функций членов, поскольку функции статических членов не имеют подразумеваемого **этого** аргумента. Функции нестатических членов имеют **этот** указатель. Функции-члены, статические или нестатические, можно определить в объявлении класса или вне его.

Если функция-член определяется в объявлении класса, она обрабатывается как встраиваемая функция, и нет необходимости уточнять имя функции именем класса. Хотя функции, определенные внутри деклараций классов, уже рассматриваются как внеочередные функции, можно использовать **внее ключевое** слово для документирования кода.

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

Если определение функции участника находится за пределами объявления класса, оно рассматривается как внештатная функция только в том случае, если она явно объявлена **вне строки.** Кроме того, имя функции в определении должно уточняться именем класса с помощью оператора разрешения области действия (`::`).

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
> Хотя функции-члены можно определить внутри объявления класса или вне его, функции-члены нельзя добавить в класс после определения класса.

Классы, содержащие функции-члены, могут иметь несколько объявлений, но сами функции-члены должны иметь только одно определение в программе. При наличии нескольких определений выдается сообщение об ошибке во время компоновки. Если класс содержит определения встраиваемых функций, определения функций должны быть идентичными для соблюдения данного правила одного определения.
