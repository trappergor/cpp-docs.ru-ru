---
title: "Предупреждение компилятора C4801 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4801"
ms.assetid: 05b29dff-15ef-42ca-9712-dc993afc4fd6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращение по ссылке не поддается проверке: причина  
  
 Ссылка c отслеживанием не может храниться в локальной переменной и затем возвращаться проверяемым образом.  
  
 Проверяемость при возвращении ссылки обеспечивается только в том случае, если средство проверки может проследить ее от создания до точки возвращения, а также в том случае, если это ссылка на элемент массива или член класса.  
  
 Для получения дополнительной информации см. [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md).  
  
 Чтобы ссылка была проверяемой, она должна оставаться в стеке от момента создания до возврата.  
  
 Предупреждение C4801 всегда выводится в качестве ошибки.  Возможно отключение этого предупреждения с помощью прагма\-директивы `#pragma warning` или параметра **\/wd**; дополнительные сведения см. в разделе [warning](../../preprocessor/warning.md) или [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(уровень предупреждений\)](../../build/reference/compiler-option-warning-level.md).  
  
## Пример  
 Предупреждение C4801 будет возникать, если средство проверки не видит принятый адрес и вынужденно предполагает, что он может быть непроверяемой ссылкой.  Следующий пример приводит к возникновению предупреждения C4801.  
  
```  
// C4801.cpp  
// compile with: /clr:safe /c  
int% f(int% p) {  
   return p;   // C4801  
}  
```  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4801.  
  
```  
// C4801_b.cpp  
// compile with: /clr:safe /c  
  
int% f(int i, array<int>^ ar) {  
   int x;  
   int% bri = x;   // cannot return a byref to a local.  
   if (i < ar->Length) {  
      bri = ar[i];   // this byref is ok.  
   }  
  
   return bri;   // C4801 not returned within the basic block  
}  
```  
  
## Пример  
 Предупреждение C4801 также может возникать, если произведена попытка разыменования и возврата ссылочного значения в блоке try.  Это приведет к созданию непроверямого кода, так как стек в конце блока try очищается, что приводит к уничтожению любого возвращаемого значения, находящегося в стеке.  Вместо этого следует разыменовать ссылочный тип и присвоить его переменной, чтобы гарантировать, что не возникнет исключение.  Затем в конце функции снова разыменуйте ссылочный тип и верните его.  
  
 Следующий пример приводит к возникновению предупреждения C4801.  
  
```  
// C4801_c.cpp  
// compile with: /clr:safe  
using namespace System;  
  
ref class StackEmptyException : public System::Exception {};  
ref class StackFullException : public System::Exception {};  
  
template <typename T>  
ref struct Stack {  
  
   Stack() {  
      topElem = -1;   // initialize stack  
      stackPtr = gcnew array<T>(10);  
   }  
  
   void push(const T%);  
   T% top();  
  
private:  
   int topElem;    
   array<T>^ stackPtr;    
};  
  
template <typename T>   
T% Stack<T>::top() {  
   try {  
      return stackPtr[topElem];   // C4801  
      // Try the following line instead.  
      // T% deadstore = stackPtr[topElem] ;  
   }  
  
   catch (System::IndexOutOfRangeException ^ e) {  
      throw gcnew StackEmptyException();  
   }  
  
   catch (System::Exception ^ e) {  
      throw;  
   }  
  
   return stackPtr[topElem] ;  
}  
  
int main() {  
   typedef Stack<Int32> IntStack;  
   IntStack ^ is = gcnew IntStack();  
  
   int i = 1;  
   while (1) {  
      try {  
         is->push(i++);  
      }  
      catch (System::Exception ^ e) {  
         break;  
      }  
      Console::Write("{0} ", is->top());  
   }  
}  
```