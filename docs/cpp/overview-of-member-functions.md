---
title: Общие сведения о функциях-членах | Документация Майкрософт
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
ms.openlocfilehash: 409f896e7b2c345d1558700f86182d06793f543d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016433"
---
# <a name="overview-of-member-functions"></a>Общие сведения о функциях-членах

Функции-члены являются либо статическими, либо нестатическими. Поведение статических функций-членов отличается от других функций-членов, поскольку статические функции-члены не имеют неявного **это** аргумент. Нестатические функции-члены имеют **это** указатель. Функции-члены, статические или нестатические, можно определить в объявлении класса или вне его.

Если функция-член определяется в объявлении класса, она обрабатывается как встраиваемая функция, и нет необходимости уточнять имя функции именем класса. Несмотря на то, что функции, определенные в объявлениях класса, всегда обрабатываются как встраиваемые функции, можно использовать **встроенного** ключевое слово для документирования кода.

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

Если определение функции-члена вне объявления класса, он обрабатывается как встраиваемая функция, только в том случае, если он объявлен явно как **встроенного**. Кроме того, имя функции в определении должно уточняться именем класса с помощью оператора разрешения области действия (`::`).

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