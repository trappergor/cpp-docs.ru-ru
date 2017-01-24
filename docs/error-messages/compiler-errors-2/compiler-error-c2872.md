---
title: "Ошибка компилятора C2872 | Microsoft Docs"
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
  - "C2872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2872"
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ" : неоднозначный символ  
  
 Компилятор не может определить, какой символ имеется в виду.  
  
 Ошибка C2872 может возникать, если в файле заголовка используется [Директива using](../../misc/using-directive-cpp.md), а в последующем файле заголовка, включенном с помощью директивы `#include`, содержится тип, также входящий в пространство имен, указанное в директиве `using`.  Директиву `using` следует указывать только после включения всех необходимых файлов с помощью директив `#include`.  
  
 Дополнительные сведения о C2872 см. в разделе [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;316317](http://support.microsoft.com/default.aspx?scid=kb;en-us;316317).  
  
 Следующий пример приводит к возникновению ошибки C2872:  
  
```  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```