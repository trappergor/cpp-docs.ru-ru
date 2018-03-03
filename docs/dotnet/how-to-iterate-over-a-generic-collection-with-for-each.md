---
title: "Как: перебор универсальной коллекции с использованием for each | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic collection, iterating over
ms.assetid: 00288d53-3d41-44d0-be5b-b3033456ceaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed9d92c4d6123d1c9c8f92814272ae5a77184102
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-iterate-over-a-generic-collection-with-for-each"></a>Практическое руководство. Перебор элементов универсальной коллекции с использованием цикла for each
[Универсальных шаблонов](../windows/generics-cpp-component-extensions.md) компонент Visual C++ позволяет создавать универсальные коллекции.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как использовать `for each` с коллекцией простое значение универсального типа.  
  
```  
// for_each_generics.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <class T>  
public value struct MyArray : public IEnumerable<T> {     
  
   MyArray( array<T>^ d ) {  
      data = d;  
   }  
  
   ref struct enumerator : IEnumerator<T> {  
      enumerator( MyArray^ myArr ) {  
         colInst = myArr;  
         currentIndex = -1;  
      }  
  
      virtual bool MoveNext() = IEnumerator<T>::MoveNext {  
         if ( currentIndex < colInst->data->Length - 1 ) {  
            currentIndex++;  
            return true;  
         }  
  
         return false;  
      }  
  
      virtual property T Current {  
         T get() {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      property Object^ CurrentNonGeneric {  
         virtual Object^ get() = System::Collections::IEnumerator::Current::get {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      virtual void Reset() {}  
      ~enumerator() {}  
  
      MyArray^ colInst;  
      int currentIndex;  
   };  
  
   array<T>^ data;  
  
   virtual IEnumerator<T>^ GetEnumerator() {  
      return gcnew enumerator(*this);  
   }  
   virtual System::Collections::IEnumerator^ GetEnumeratorNonGeneric() = System::Collections::IEnumerable::GetEnumerator {  
      return gcnew enumerator(*this);  
   }  
};  
  
int main() {  
   MyArray<int> col = MyArray<int>( gcnew array<int>{10, 20, 30 } );  
  
   for each ( Object^ c in col )  
      Console::WriteLine((int)c);  
}  
```  
  
```Output  
10  
20  
30  
```  
  
## <a name="see-also"></a>См. также  
 [for each, in](../dotnet/for-each-in.md)