---
title: "Ошибка компилятора C3744 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3744"
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C3744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

для \_\_unhook требуется по крайней мере 3 аргумента в случае управляемых событий  
  
 В программе, скомпилированной для управляемых расширений для C\+\+, функция [\_\_unhook](../../cpp/unhook.md) должна принимать три параметра.  
  
 Функции `__hook` и `__unhook` не совместимы с параметром \/clr.  Вместо этого следует использовать операторы \+\= и \-\=.  
  
 Ошибка C3744 возникает только при использовании параметра **\/clr:oldSyntax**.  
  
 Следующий пример приводит к возникновению ошибки C3744:  
  
```  
// C3744.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __delegate void delegate1();  
  
[ event_source(managed) ]  
public __gc class CPSource {  
public:  
   __event delegate1* event1;  
};  
  
[event_receiver(managed)]  
public __gc class CReceiver {  
public:  
   void Handler1() {  
   }  
  
   void UnhookAll1(CPSource* pSrc, CReceiver* pRec) {  
      pRec;  
      __unhook(pSrc);   // C3744  
      // The following line resolves the error.  
      // __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1);  
   }  
};  
  
int main() {  
}  
```