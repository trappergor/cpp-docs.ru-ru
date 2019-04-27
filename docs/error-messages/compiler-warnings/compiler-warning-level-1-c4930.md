---
title: Предупреждение компилятора (уровень 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: 15cd1ed61c747e2c9168b9fc0fee03dca8403a24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242790"
---
# <a name="compiler-warning-level-1-c4930"></a>Предупреждение компилятора (уровень 1) C4930

«прототип»: функция с прототипом не вызвана (был предполагалось определение переменной?)

Компилятор обнаружил неиспользуемый прототип функции. Если прототипа предполагалось объявление переменной, удалите круглые скобки, открытия и закрытия.

Следующий пример приводит к возникновению ошибки C4930:

```
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

C4930 также может возникать, когда компилятор не может различать объявление прототипа функции и вызов функции.

Следующий пример приводит к возникновению ошибки C4930:

```
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

В приведенном выше примере результат метода, который принимает ноль аргументов конструктору неименованный класс локальной переменной передается как аргумент. Вызов может быть однозначно определяемое имя локальной переменной или добавления префикса вызов метода с экземпляром объекта, а также соответствующий оператор указателя на член.