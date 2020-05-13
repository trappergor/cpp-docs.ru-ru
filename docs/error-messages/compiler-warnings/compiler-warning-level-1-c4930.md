---
title: Предупреждение компилятора (уровень 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: 6c012e484bddeb204601265f9d56efb7bbee7e96
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199320"
---
# <a name="compiler-warning-level-1-c4930"></a>Предупреждение компилятора (уровень 1) C4930

"прототип": функция с прототипом не вызвана (предполагалось определение переменной?)

Компилятор обнаружил неиспользуемый прототип функции. Если прототип предназначался как объявление переменной, удалите скобки, открывающие и закрывающие.

Следующий пример приводит к возникновению ошибки C4930:

```cpp
// C4930.cpp
// compile with: /W1
class Lock {
public:
   int i;
};

void f() {
   Lock theLock();   // C4930
   // try the following line instead
   // Lock theLock;
}

int main() {
}
```

C4930 также может возникать, если компилятор не может различить объявление прототипа функции и вызов функции.

Следующий пример приводит к возникновению ошибки C4930:

```cpp
// C4930b.cpp
// compile with: /EHsc /W1

class BooleanException
{
   bool _result;

public:
   BooleanException(bool result)
      : _result(result)
   {
   }

   bool GetResult() const
   {
      return _result;
   }
};

template<class T = BooleanException>
class IfFailedThrow
{
public:
   IfFailedThrow(bool result)
   {
      if (!result)
      {
         throw T(result);
      }
   }
};

class MyClass
{
public:
   bool MyFunc()
   {
      try
      {
         IfFailedThrow<>(MyMethod()); // C4930

         // try one of the following lines instead
         // IfFailedThrow<> ift(MyMethod());
         // IfFailedThrow<>(this->MyMethod());
         // IfFailedThrow<>((*this).MyMethod());

         return true;
      }
      catch (BooleanException e)
      {
         return e.GetResult();
      }
   }

private:
   bool MyMethod()
   {
      return true;
   }
};

int main()
{
   MyClass myClass;
   myClass.MyFunc();
}
```

В приведенном выше примере результат метода, принимающего нулевые аргументы, передается в качестве аргумента в конструктор неименованной переменной локального класса. Вызов может быть неоднозначной, либо именованием локальной переменной, либо префиксом вызова метода с помощью экземпляра объекта вместе с соответствующим оператором указателя на член.
