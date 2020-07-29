---
title: Виртуальные функции
ms.date: 09/10/2019
helpviewer_keywords:
- functions [C++], virtual functions
- derived classes [C++], virtual functions
- virtual functions
ms.assetid: b3e1ed88-2a90-4af8-960a-16f47deb3452
ms.openlocfilehash: 4296d66af8f8bb9aed4946d6dc57871f447108d2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231043"
---
# <a name="virtual-functions"></a>Виртуальные функции

Виртуальная функция — это функция-член, которую предполагается переопределить в производных классах. При ссылке на объект производного класса с помощью указателя или ссылки на базовый класс можно вызвать виртуальную функцию для этого объекта и выполнить версию функции производного класса.

Виртуальные функции обеспечивают вызов соответствующей функции для объекта независимо от выражения, используемого для вызова функции.

Предположим, что базовый класс содержит функцию, объявленную как [Виртуальная](../cpp/virtual-cpp.md) , а производный класс определяет ту же функцию. Функция производного класса вызывается для объектов производного класса, даже если она вызывается с помощью указателя или ссылки на базовый класс. В следующем примере показан базовый класс, который предоставляет реализацию функции `PrintBalance` и два производных класса.

```cpp
// deriv_VirtualFunctions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Account {
public:
   Account( double d ) { _balance = d; }
   virtual ~Account() {}
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
   CheckingAccount checking( 100.00 );
   SavingsAccount  savings( 1000.00 );

   // Call PrintBalance using a pointer to Account.
   Account *pAccount = &checking;
   pAccount->PrintBalance();

   // Call PrintBalance using a pointer to Account.
   pAccount = &savings;
   pAccount->PrintBalance();
}
```

В предыдущем примере вызовы `PrintBalance` идентичны за исключением тех, на которые указывает объект `pAccount`. Поскольку функция `PrintBalance` виртуальная, вызывается версия функции, определенная для каждого объекта. Функция `PrintBalance` в производных классах `CheckingAccount` и `SavingsAccount` переопределяет функцию в базовом классе `Account`.

Если объявлен класс, который не предоставляет переопределяющую реализацию функции `PrintBalance`, используется реализация по умолчанию из базового класса `Account`.

Функции в производных классах переопределяют виртуальные функции в базовых классах, только если их тип совпадает. Функция в производном классе не может отличаться от виртуальной функции в базовом классе только возвращаемым типом; список аргументов также должен отличаться.

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

```Output
Derived::NameOf
Invoked by Base
Derived::NameOf
Invoked by Derived
```

Обратите внимание, что независимо от того, вызывается ли функция `NameOf` с помощью указателя на `Base` или указателя на `Derived`, вызывается функция для `Derived`. Вызывается функция для `Derived`, поскольку `NameOf` является виртуальной функцией, и `pBase` и `pDerived` указывают на объект типа `Derived`.

Поскольку виртуальные функции вызываются только для объектов типов классов, глобальные или статические функции нельзя объявлять как **`virtual`** .

**`virtual`** Ключевое слово можно использовать при объявлении переопределяемых функций в производном классе, но это не обязательно; переопределения виртуальных функций всегда являются виртуальными.

Виртуальные функции в базовом классе должны быть определены, если они не объявлены с помощью *чистого описателя*. (Дополнительные сведения о чистых виртуальных функциях см. в разделе [абстрактные классы](../cpp/abstract-classes-cpp.md).)

Механизм вызова виртуальных функций можно подавить, явно указав имя функции с помощью оператора разрешения области действия (`::`). Рассмотрим предыдущий пример с классом `Account`. Для вызова `PrintBalance` в базовом классе используйте следующий код.

```cpp
CheckingAccount *pChecking = new CheckingAccount( 100.00 );

pChecking->Account::PrintBalance();  //  Explicit qualification.

Account *pAccount = pChecking;  // Call Account::PrintBalance

pAccount->Account::PrintBalance();   //  Explicit qualification.
```

Оба вызова `PrintBalance` в предыдущем примере подавляют механизм вызова виртуальных функций.
