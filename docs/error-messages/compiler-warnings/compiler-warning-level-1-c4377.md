---
title: "Предупреждение компилятора (уровень 1) C4377 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4377"
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Предупреждение компилятора (уровень 1) C4377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

собственные типы являются закрытыми по умолчанию; типы \-d1PrivateNativeTypes являются нежелательными  
  
 В предыдущих выпусках собственные типы в сборках были открытыми по умолчанию, а для их преобразования в закрытый тип использовался внутренний недокументированный параметр компилятора \(**\/d1PrivateNativeTypes**\).  
  
 Все типы — как собственные, так и CLR — теперь являются в сборках закрытыми по умолчанию, поэтому типы **\/d1PrivateNativeTypes** больше не нужны.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4377.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```