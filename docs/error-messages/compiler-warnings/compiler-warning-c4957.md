---
title: "Предупреждение компилятора C4957 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4957"
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"приведение": явное приведение "исходный\_тип" к "конечный\_тип" недоступно для проверки  
  
 В результате приведения будет создан недоступный для проверки образ.  
  
 Некоторые приведения являются безопасными \(например, приведение `static_cast` вызывает выполнение пользовательских преобразований и приведение `const_cast`\). При выполнении приведения [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) гарантированно создается проверяемый код.  
  
 Для получения дополнительной информации см. [Чистый и проверяемый код](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью директивы pragma [warning](../../preprocessor/warning.md) или параметра компилятора [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 Следующий пример приводит к возникновению предупреждения C4957:  
  
```  
// C4957.cpp // compile with: /clr:safe // #pragma warning( disable : 4957 ) using namespace System; int main() { Object ^ o = "Hello, World!"; String ^ s = static_cast<String^>(o);   // C4957 String ^ s2 = safe_cast<String^>(o);   // OK }  
```