---
title: "Предупреждение компилятора (уровень 1) C4930 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4930"
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровень 1) C4930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"прототип": функция с прототипом не вызвана \(предполагалось определение переменной?\)  
  
 В процессе компиляции обнаружен неиспользуемый прототип функции.  Если в качестве прототипа предполагалось объявление переменной, удалите открывающие и закрывающие круглые скобки.  
  
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
  
 Ошибка C4930 также может возникать в том случае, если компилятор не может различить объявление прототипа функции и вызов функции.  
  
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
  
 В приведенном выше примере результат метода, принимающего нулевые аргументы, передается в качестве аргумента в конструктор неименованной локальной переменной класса.  Чтобы однозначно определить вызов, присвойте имя локальной переменной или используйте в качестве префикса для вызова метода экземпляр объекта и соответствующий оператор указателя на член.