---
title: "Предупреждение компилятора (уровень 1) C4138 | Microsoft Docs"
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
  - "C4138"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4138"
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4138
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\*\/" найден вне комментария  
  
 Закрывающему разделителю комментария не предшествует разделитель, открывающий комментарий. Компилятор предполагает пробел между звездочкой \(**\***\) и косой чертой \(\/\).  
  
## Пример  
  
```  
// C4138a.cpp // compile with: /W1 int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning int main() { }  
```  
  
 Это предупреждение может быть вызвано попыткой создать вложенный комментарий.  
  
 Чтобы устранить это предупреждение, раскомментируйте код, содержащий комментарии, поместите его в блок **\#if\/\#endif** и задайте для управляющего выражения значение нуль:  
  
```  
// C4138b.cpp // compile with: /W1 #if 0 int my_variable;   /* Declaration currently not needed */ #endif int main() { }  
```