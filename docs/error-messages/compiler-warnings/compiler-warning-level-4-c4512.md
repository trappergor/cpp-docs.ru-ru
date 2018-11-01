---
title: Предупреждение компилятора (уровень 4) C4512
ms.date: 11/04/2016
f1_keywords:
- C4512
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
ms.openlocfilehash: c5e84fe1d0e558e689e48fba8df112861f81acec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564519"
---
# <a name="compiler-warning-level-4-c4512"></a>Предупреждение компилятора (уровень 4) C4512

'класс' : не удалось создать оператор назначения

Компилятор не может создать оператор назначения для заданного класса. Оператор назначения не был создан.

Это предупреждение может быть вызвано оператором назначения базового класса, недоступным для производного класса.

Чтобы избежать этого предупреждения, укажите определенный пользователем оператор назначения для класса.

Компилятор также создаст функцию оператора назначения для класса, который его не определяет. Этот оператор назначения представляет собой поэлементную копию членов данных объекта. Элементы данных `const` невозможно изменить после инициализации, поэтому если класс содержит элемент `const`, то оператор назначения по умолчанию не будет работать. Еще одна причина предупреждения C4512 — объявление нестатического члена данных ссылочного типа. Если нужно создать некопируемый тип, следует также предотвратить создание конструктора копий по умолчанию.

Устранить предупреждение C4512 в коде можно одним из трех способов:

- Явным образом определить оператор назначения для класса.

- Удалить **const** или ссылочный оператор из элемента данных в классе.

- Используйте директиву #pragma [предупреждение](../../preprocessor/warning.md) инструкцию, чтобы отключить предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4512.

```
// C4512.cpp
// compile with: /EHsc /W4
// processor: x86

class Base {
private:
   const int a;

public:
   Base(int val = 0) : a(val) {}
   int get_a() { return a; }
};   // C4512 warning

class Base2 {
private:
   const int a;

public:
   Base2(int val = 0) : a(val) {}
   Base2 & operator=( const Base2 & ) { return *this; }
   int get_a() { return a; }
};

// Type designer intends this to be non-copyable because it has a
// reference member
class Base3
{
private:
   char& cr;

public:
   Base3(char& r) : cr(r) {}
   // Uncomment the following line to explicitly disable copying:
   // Base3(const Base3&) = delete;
};   // C4512 warning

int main() {
   Base first;
   Base second;

   // OK
   Base2 first2;
   Base2 second2;

   char c = 'x';
   Base3 first3(c);
   Base3 second3 = first3; // C2280 if no default copy ctor
}
```