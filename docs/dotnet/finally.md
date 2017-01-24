---
title: "finally | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finally - ключевое слово [C++]"
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# finally
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помимо `try` и предложениям `catch`, поддержка обработки исключений среды CLR предложение `finally`.  Семантика идентична блоку `__finally` в структурной обработке исключений \(SEH\).  Блок `__finally` может следовать блок `try` или `catch`.  
  
## Заметки  
 Цель блока `finally` для освобождения любых ресурсов, которые еще после исключения было.  Обратите внимание, что блок `finally` выполняется всегда, даже если исключение не было создано.  Блок `catch` только выполняется, если управляемое исключение в соответствующий блок `try`.  
  
 `finally` — контекстно\-зависимое ключевое слово; дополнительные сведения см. в разделе [Контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере показан простой блок `finally`:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
  **в перехвате**  
**MyException**  
**в конце**   
## См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)