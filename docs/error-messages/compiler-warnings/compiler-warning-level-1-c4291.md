---
title: "Предупреждение (уровень 1) C4291 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4291
dev_langs: C++
helpviewer_keywords: C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a1c03e12805c35ce04322a7ffb4d48499a9a9f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4291"></a>Предупреждение компилятора (уровень 1) C4291
«объявление»: не обнаружен; соответствующий оператор delete память не будут освобождены при инициализации возникнет исключение  
  
 Размещение [новый](../../cpp/new-operator-cpp.md) используется для которого нет не размещения [удалить](../../cpp/delete-operator-cpp.md).  
  
 Если выделить память для объекта с помощью оператора **новый**, вызывается конструктор этого объекта. Если конструктор вызывает исключение, должна быть освобождена память, выделенная для объекта. Это не может иметь место, если оператор **удаление** функция существует, соответствующий оператор **новый**.  
  
 Если вы используете оператор **новый** без дополнительных аргументов и компиляция с [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), или/EHa параметры, чтобы включить обработку исключений, компилятор создаст код вызывающий оператор **удалить** Если конструктор вызывает исключение.  
  
 При использовании формы размещения оператора **новый** оператор (формы с аргументами в дополнение к размеру выделения) и в конструктор объекта вызывает исключение, по-прежнему компилятор создаст код, вызывающий оператор **удаление**; но он будет делать только если формы размещения оператора **удаление** существует сопоставление формы размещения оператора **новый** , выделена память. Пример:  
  
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
  
 Приведенный выше пример возникает предупреждение C4291, поскольку не формы размещения оператора **удалить** был определен, соответствующий формы размещения оператора **новый**. Чтобы решить проблему, вставьте следующий код выше **основной**. Обратите внимание, что все перегруженный оператор **удаление** параметры функции соответствуют перегруженный оператор **новый**, за исключением первого параметра.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```