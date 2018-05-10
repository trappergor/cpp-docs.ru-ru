---
title: 'Как: повышения производительности при использовании универсальных шаблонов (Visual C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, C++
- Visual C++, performance
- Visual C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da74cce5f41c3399fb102180cfdfe8c1215c8bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-improve-performance-with-generics-visual-c"></a>Практическое руководство. Повышение производительности с помощью универсальных коллекций (Visual C++)
С помощью универсальных шаблонов можно создать многократно используемый код на основе параметра типа. Определение фактического типа параметра типа откладывается до вызова из клиентского кода. Дополнительные сведения об универсальных шаблонах см. в разделе [универсальные шаблоны](../windows/generics-cpp-component-extensions.md).  
  
 В этой статье обсуждается, как универсальные шаблоны позволяют повысить производительность приложения, использующего коллекции.  
  
## <a name="example"></a>Пример  
 .NET Framework поставляется с множеством классов коллекций в пространстве имен <xref:System.Collections?displayProperty=fullName>. Большинство этих коллекций работает с объектами типа <xref:System.Object?displayProperty=fullName>. Это позволяет коллекциям хранить объекты любого типа, поскольку все типы в среде .NET Framework, даже типы значений, наследуются от <xref:System.Object?displayProperty=fullName>. Однако у этого подхода есть два недостатка.  
  
 Во-первых, если коллекция содержит типы значений, например целые числа, то перед добавлением в коллекцию значение должно быть упаковано, а при извлечении из нее — распаковано. Это ресурсоемкие операции.  
  
 Во-вторых, нет возможности управлять типами, добавляемыми в коллекцию. В одну и ту же коллекцию могут быть добавлены целое число и строка, хотя это, возможно, не предполагалось. Таким образом, чтобы обеспечить типобезопасность кода, необходимо убедиться в том, что тип, извлеченный из коллекции, соответствует ожидаемому.  
  
 В следующем примере кода демонстрируются два главных недостатка коллекций .NET Framework по сравнению с универсальными шаблонами.  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count> 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
```Output  
Popped a String: Seven  
Popped an int: 7  
```  
  
## <a name="example"></a>Пример  
 Новое пространство имен <xref:System.Collections.Generic?displayProperty=fullName> содержит многие из коллекций, имевшихся в пространстве имен <xref:System.Collections?displayProperty=fullName>, но они изменены, чтобы принимать параметры универсального типа. При этом исключаются два недостатка неуниверсальных коллекций: упаковка-распаковка типов значений и невозможность указания типов, которые должны храниться в коллекциях. Операции над двумя коллекциях одинаковы; они отличаются только способом создания экземпляров.  
  
 Сравните вышеприведенный пример с данным, в котором используется универсальная коллекция <xref:System.Collections.Generic.Stack%601>. Для больших коллекций, к которым часто осуществляется доступ, производительность этого примера будет гораздо выше предыдущего.  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
```Output  
14  
```  
  
## <a name="see-also"></a>См. также  
 [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md)