---
title: "Предупреждение компилятора (уровень 4) C4629 | Microsoft Docs"
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
  - "C4629"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4629"
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4629
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использован диграф, последовательность знаков digraph интерпретирована как токен char \(если требуется другой результат, добавьте пробел между двумя знаками\)  
  
 При использовании параметра [\/Za](../../build/reference/za-ze-disable-language-extensions.md) компилятор выдает предупреждение, когда обнаруживает диграф.  
  
 В следующем примере возникает ошибка C4629.  
  
```  
// C4629.cpp // compile with: /Za /W4 int main() <%   // C4629 <% digraph for { }  
```