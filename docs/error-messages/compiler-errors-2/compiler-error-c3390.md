---
title: "Ошибка компилятора C3390 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3390
dev_langs: C++
helpviewer_keywords: C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea23a13a338e5d09eac0714914d9c1020b5908cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3390"></a>Ошибка компилятора C3390
"аргумент_типа": недопустимый аргумент типа для универсального параметра "параметр" для универсального "универсальный_тип", должен быть ссылочный тип  
  
Экземпляр универсального типа создается неправильным образом.  Проверьте определение типа.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
В первом образце используется C# для создания компонента, который содержит универсальный тип, который имеет определенные ограничения, которые не поддерживаются при создании универсальных типов в C + +/ CLR. Дополнительные сведения см. в разделе [Ограничения параметров типа](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
Если компонент C3390.dll доступен, следующий пример приводит к возникновению ошибки C3390.  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```