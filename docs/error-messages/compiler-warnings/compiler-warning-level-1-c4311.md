---
title: "Предупреждение компилятора (уровень 1) C4311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4311"
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Предупреждение компилятора (уровень 1) C4311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная" : усечение указателя из типа "тип" в "тип"  
  
 Данное предупреждение сообщает о проблемах с усечением 64\-разрядного указателя.  Например, если код компилируется для 64\-разрядной архитектуры, значение указателя \(64 бита\) будет усечено, если он назначен `int` \(32 бита\).  Подробнее: [Правила использования указателей](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 Дополнительные сведения о распространенных причинах предупреждения C4311 см. в разделе [Типичные ошибки компилятора](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 В следующем примере показано возникновение ошибки C4311 при компиляции для 64\-разрядной архитектуры и возможные способы ее устранения.  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```