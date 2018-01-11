---
title: "Упаковка-преобразование (C + +/ CX) | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d953e35c0fe238dc8dee76ad6c2d5aab7a0ab1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="boxing-ccx"></a>Упаковка-преобразование (C++/CX)
*Упаковка* — это заключение переменной типа значения, например [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), или базового скалярного типа, например `int`, в ссылочный класс при передаче переменной методу, который в качестве входного типа принимает [Platform::Object^](../cppcx/platform-object-class.md) .  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Передача типа значения параметру Object^  
 Хотя явным образом упаковывать переменную для ее передачи в параметр метода типа [Platform::Object^](../cppcx/platform-object-class.md)не требуется, необходимо выполнять явное приведение к исходному типу при получении значений, которые до этого были упакованы.  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Использование Platform::IBox\<T > для поддержки типов, допускающих значения NULL  
 C# и Visual Basic поддерживают понятие типов значений, допускающих значения null. В C + +/ CX, можно использовать `Platform::IBox<T>` тип для предоставления открытых методов, которые поддерживают параметры типа значения, допускающие значение NULL. В следующем примере показано C + +/ CX открытый метод, который возвращает значение null, если вызывающий код C# передает null в качестве одного из аргументов.  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 В клиенте XAML C# его можно использовать следующим образом:  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>См. также  
 [Система типов (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Приведение (C + +/ CX)](../cppcx/casting-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)