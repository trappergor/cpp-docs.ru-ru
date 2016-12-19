---
title: "Предупреждение компилятора (уровень 1) C4291 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4291"
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"объявление" : не обнаружен соответствующий оператор delete; память не будет освобождена, если в ходе инициализации возникнет исключение  
  
 Использован оператор [new](../../cpp/new-operator-cpp.md) с размещением, для которого не найден оператор [delete](../../cpp/delete-operator-cpp.md) с размещением.  
  
 Когда память выделяется под объект, имеющий оператор **new**, вызывается конструктор этого объекта.  Если в конструкторе возникает исключение, то вся память, выделенная под объект, должна быть освобождена.  Этого произойдет только в том случае, если существует соответствующий оператору **new** оператор **delete**.  
  
 Если оператор **new** используется без дополнительных аргументов и компиляция производится с параметром [\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md), [\/EHs](../../build/reference/eh-exception-handling-model.md), или \/EHa, включающим обработку исключений, то компилятор создаст код, вызывающий оператор **delete**, если в конструкторе возникает исключение.  
  
 Если оператор **new** используется в форме с размещением \(форма с дополнительными аргументами помимо объема выделяемой памяти\) и в конструкторе объекта возникает исключение, то компилятор все равно создаст код, вызывающий оператор **delete**; тем не менее, он сделает это только в том случае, если существует форма оператора **delete** с размещением, соответствующая форме оператора **new** с размещением, с помощью которого выделялась память.  Примеры.  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 В приведенном ниже примере возникает предупреждение C4291, поскольку в нем не определена форма оператора **delete** с размещением, соответствующая форме оператора **new** с размещением.  Для устранения проблемы вставьте перед функцией **main** приведенный ниже код.  Обратите внимание, что все формальные параметры перегруженного оператора **delete**, за исключением первого, соответствуют параметрам перегруженного оператора **new**.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```