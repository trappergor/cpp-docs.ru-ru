---
title: "Предупреждение компилятора (уровень 3) C4290 | Microsoft Docs"
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
  - "C4290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4290"
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

спецификация исключений C\+\+ игнорируется, кроме случая, когда указывается, что функция не является \_\_declspec\(nothrow\)  
  
 Для функции объявлено использование спецификации исключений, которые в Visual C\+\+ являются допустимыми, но не реализованными.  Возможно, код со спецификациями исключений, которые игнорируются во время компиляции, потребуется перекомпилировать и создать на него ссылку для его использования в последующих версиях, поддерживающих спецификации исключений.  
  
 Дополнительные сведения см. в разделе [Спецификации исключений \(throw\)](../../cpp/exception-specifications-throw-cpp.md).  
  
 Чтобы избежать появления такого предупреждения, используйте директиву pragma [предупреждение](../../preprocessor/warning.md):  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 Следующий пример приводит к возникновению предупреждения C4290:  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```