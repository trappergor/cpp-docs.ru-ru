---
title: Предупреждение (уровень 1) C4930 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4930
dev_langs:
- C++
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63c21e7e73b49017ff1d26baf78cb2eb61f631dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289881"
---
# <a name="compiler-warning-level-1-c4930"></a>Предупреждение компилятора (уровень 1) C4930
«прототип»: функция с прототипом не вызвана (предполагалось определение переменной?)  
  
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
  
 C4930 также может возникать, если компилятор не может различать объявление прототипа функции и вызов функции.  
  
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
  
 В приведенном выше примере результат метода, который принимает ни одного аргумента передается в качестве аргумента в конструктор неименованной локальной переменной класса. Вызов можно однозначно определяемое имя локальной переменной или задание префикса для вызова метода экземпляр объекта и соответствующий оператор указателя на член.