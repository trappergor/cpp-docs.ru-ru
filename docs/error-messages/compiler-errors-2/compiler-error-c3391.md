---
title: "C3391 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 7b5922ccf353162dc32c99e3818227639d0f5985
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3391"></a>Ошибка компилятора C3391
«аргумент»: недопустимый аргумент типа для универсального параметра «параметр» для универсального «универсальный тип», должен быть типом значения, не допускающие значения NULL  
  
Экземпляр универсального типа был создан неправильно. Проверьте определение типа. Дополнительные сведения см. в разделе <xref:System.Nullable>и [универсальных шаблонов](../../windows/generics-cpp-component-extensions.md).</xref:System.Nullable>  
  
## <a name="example"></a>Пример  
В следующем примере используется C# для создания компонента, который содержит универсальный тип, который имеет некоторые ограничения, которые не поддерживаются при создании универсальных типов в C + +/ CLI. Дополнительные сведения см. в разделе [ограничения параметров типа](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
Когда компонент C3391.dll доступен, следующий пример приводит к возникновению ошибки C3391.  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```
