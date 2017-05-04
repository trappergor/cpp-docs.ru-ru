---
title: "Упаковка-преобразование (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Упаковка-преобразование (C++/CX)
*Упаковка* — это заключение переменной типа значения, например [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), или базового скалярного типа, например `int`, в ссылочный класс при передаче переменной методу, который в качестве входного типа принимает [Platform::Object^](../cppcx/platform-object-class.md).  
  
## Передача типа значения параметру Object^  
 Хотя явным образом упаковывать переменную для ее передачи в параметр метода типа [Platform::Object^](../cppcx/platform-object-class.md) не требуется, необходимо выполнять явное приведение к исходному типу при получении значений, которые до этого были упакованы.  
  
 [!code-cpp[cx_boxing#01](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.cpp#01)]  
  
### Использование Platform::IBox\<T\> для поддержки типов значений, допускающих значения null  
 C\# и Visual Basic поддерживают понятие типов значений, допускающих значения null. В [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] с помощью типа `Platform::IBox<T>` можно предоставить доступ к отрытым методам, которые поддерживают параметры типа значения, допускающие значения null. В следующем примере показан открытый метод [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], который возвращает значение null, если вызывающий код C\# передает null в качестве одного из своих аргументов.  
  
 [!code-cpp[cx_boxing#02](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.h#02)]  
  
 В клиенте XAML C\# его можно использовать следующим образом:  
  
```  
  
// C# client code BoxingDemo.Class1 obj = new BoxingDemo.Class1(); int? a = null; int? b = 5; var result = obj.Multiply(a,b); //result = null  
  
```  
  
## См. также  
 [Система типов \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Приведение \(C\+\+\/CX\)](../cppcx/casting-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)