---
title: "Практическое руководство. Повышение производительности с помощью универсальных коллекций (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "универсальные [C++], производительность"
  - "производительность, C++"
  - "Visual C++, универсальные шаблоны"
  - "Visual C++, производительность"
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Повышение производительности с помощью универсальных коллекций (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью универсальных шаблонов можно создать повторно используемый код на основе параметра типа.  Определение фактического типа параметра типа откладывается до вызова из клиентского кода.  Дополнительные сведения об универсальных элементах см. в разделе [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md).  
  
 В этой статье обсуждается, как универсальные шаблоны могут помочь повысить производительность приложения, которое использует коллекции.  
  
## Пример  
 .NET Framework поставляется с несколькими классами коллекций в пространстве имен <xref:System.Collections?displayProperty=fullName>.  Большинство этих коллекций работает с объектами типа <xref:System.Object?displayProperty=fullName>.  Это позволяет коллекциям хранить объекты любого типа, поскольку все типы платформы .NET Framework, даже типы значений, наследуются от <xref:System.Object?displayProperty=fullName>.  Однако у этого подхода есть два недостатка.  
  
 Во\-первых, если коллекция содержит типы значения, такие как целые числа, значение должно быть упаковано перед добавлением в коллекцию и распаковано при извлечении из коллекции.  Эти операции ресурсоемки.  
  
 Во\-вторых, не существует способа контролировать типы, добавляемые в коллекцию.  Допускается добавить целое число и строку в одну и ту же коллекцию, несмотря на то, что, возможно, такое действие не предполагалось.  Таким образом, чтобы обеспечить типобезопасность кода, необходимо проверить, что тип, извлеченный из коллекции, соответствует ожидаемому.  
  
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
    while (s->Count > 0)  
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
  
  **Извлечена строка: Seven**  
**Извлечен int: 7**   
## Пример  
 Новое пространство имен <xref:System.Collections.Generic?displayProperty=fullName> содержит многие из коллекций, указанных в пространстве имен <xref:System.Collections?displayProperty=fullName>, но они были изменены, чтобы принимать параметры универсального типа.  Это исключает два недостатка неуниверсальных коллекций: упаковка\-распаковка и невозможность указания типов, которые должны храниться в коллекциях.  Операции над двумя коллекциях совпадают; они отличаются только способом создания.  
  
 Сравните вышеприведенный пример с данным, использующим универсальную коллекцию <xref:System.Collections.Generic.Stack%601>.  Для больших коллекций, к которым часто осуществляется доступ, производительность этого примера будет гораздо выше предыдущего.  
  
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
  
  **14**   
## См. также  
 [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md)