---
title: Виртуальные функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6de0d358c6ac587944977340e02b1ee6ed086f8c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111746"
---
# <a name="virtual-functions"></a>Виртуальные функции

Виртуальная функция — это функция-член, которую предполагается переопределить в производных классах. При ссылке на объект производного класса с помощью указателя или ссылки на базовый класс можно вызвать виртуальную функцию для этого объекта и выполнить версию функции производного класса.

Виртуальные функции обеспечивают вызов соответствующей функции для объекта независимо от выражения, используемого для вызова функции.

Предположим, что базовый класс содержит функцию, объявленную как [виртуального](../cpp/virtual-cpp.md) и производный класс определяет ту же функцию. Функция производного класса вызывается для объектов производного класса, даже если она вызывается с помощью указателя или ссылки на базовый класс. В следующем примере показан базовый класс, который предоставляет реализацию функции `PrintBalance` и два производных класса.

```cpp
// deriv_VirtualFunctions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Account {
public:
   Account( double d ) { _balance = d; }
   virtual double GetBalance() { return _balance; }
   virtual void PrintBalance() { cerr << "Error. Balance not available for base type." << endl; }
private:
    double _balance;
};

class CheckingAccount : public Account {
public:
   CheckingAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Checking account balance: " << GetBalance() << endl; }
};

class SavingsAccount : public Account {
public:
   SavingsAccount(double d) : Account(d) {}
   void PrintBalance() { cout << "Savings account balance: " << GetBalance(); }
};

int main() {
   // Create objects of type CheckingAccount and SavingsAccount.
   CheckingAccount *pChecking = new CheckingAccount( 100.00 ) ;
   SavingsAccount  *pSavings  = new SavingsAccount( 1000.00 );

   // Call PrintBalance using a pointer to Account.
   Account *pAccount = pChecking;
   pAccount->PrintBalance();

   // Call PrintBalance using a pointer to Account.
   pAccount = pSavings;
   pAccount->PrintBalance();
}
```

В предыдущем примере вызовы `PrintBalance` идентичны за исключением тех, на которые указывает объект `pAccount`. Поскольку функция `PrintBalance` виртуальная, вызывается версия функции, определенная для каждого объекта. Функция `PrintBalance` в производных классах `CheckingAccount` и `SavingsAccount` переопределяет функцию в базовом классе `Account`.

Если объявлен класс, который не предоставляет переопределяющую реализацию функции `PrintBalance`, используется реализация по умолчанию из базового класса `Account`.

Функции в производных классах переопределяют виртуальные функции в базовых классах, только если их тип совпадает. Функция в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого значения; список аргументов также должен отличаться.

При вызове функции с помощью указателей или ссылок применяются следующие правила.

- Вызов виртуальной функции разрешается в соответствии с базовым типом объекта, для которого она вызывается.

- Вызов невиртуальной функции разрешается в соответствии с типом указателя или ссылки.

В следующем примере показано поведение виртуальной и невиртуальной функций при вызове с помощью указателей.

```cpp
// deriv_VirtualFunctions2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base {
public:
   virtual void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Base::NameOf() {
   cout << "Base::NameOf\n";
}

void Base::InvokingClass() {
   cout << "Invoked by Base\n";
}

class Derived : public Base {
public:
   void NameOf();   // Virtual function.
   void InvokingClass();   // Nonvirtual function.
};

// Implement the two functions.
void Derived::NameOf() {
   cout << "Derived::NameOf\n";
}

void Derived::InvokingClass() {
   cout << "Invoked by Derived\n";
}

int main() {
   // Declare an object of type Derived.
   Derived aDerived;

   // Declare two pointers, one of type Derived * and the other
   //  of type Base *, and initialize them to point to aDerived.
   Derived *pDerived = &aDerived;
   Base    *pBase    = &aDerived;

   // Call the functions.
   pBase->NameOf();           // Call virtual function.
   pBase->InvokingClass();    // Call nonvirtual function.
   pDerived->NameOf();        // Call virtual function.
   pDerived->InvokingClass(); // Call nonvirtual function.
}
```

### <a name="output"></a>Вывод

```Output
Derived::NameOf
Invoked by Base
Derived::NameOf
Invoked by Derived
```

Обратите внимание, что независимо от того, вызывается ли функция `NameOf` с помощью указателя на `Base` или указателя на `Derived`, вызывается функция для `Derived`. Вызывается функция для `Derived`, поскольку `NameOf` является виртуальной функцией, и `pBase` и `pDerived` указывают на объект типа `Derived`.

Так как виртуальные функции вызываются только для объектов типов классов, нельзя объявлять глобальной или статической функции как **виртуального**.

**Виртуальных** слово может использоваться при объявлении переопределяющих функций в производном классе, но он не нужен; переопределения виртуальных функций всегда являются виртуальными.

Виртуальные функции в базовом классе необходимо определить, если они объявлены с помощью *чистый спецификатор*. (Дополнительные сведения о чистых виртуальных функций, см. в разделе [абстрактные классы](../cpp/abstract-classes-cpp.md).)

Механизм вызова виртуальных функций можно подавить, явно указав имя функции с помощью оператора разрешения области действия (`::`). Рассмотрим предыдущий пример с классом `Account`. Для вызова `PrintBalance` в базовом классе используйте следующий код.

```cpp
CheckingAccount *pChecking = new CheckingAccount( 100.00 );

pChecking->Account::PrintBalance();  //  Explicit qualification.

Account *pAccount = pChecking;  // Call Account::PrintBalance

pAccount->Account::PrintBalance();   //  Explicit qualification.
```

Оба вызова `PrintBalance` в предыдущем примере подавляют механизм вызова виртуальных функций.