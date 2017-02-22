---
title: "Предупреждение компилятора (уровень 1) C4674 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4674"
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 1) C4674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод": требуется объявление как "static" и наличие строго одного параметра  
  
 Неправильная сигнатура оператора преобразования. Метод не считается пользовательским преобразованием.  
  
 Сведения об определяющих операторах при использовании нового синтаксиса \(**\/clr**\) см. в разделах [Пользовательские операторы](../../dotnet/user-defined-operators-cpp-cli.md) и [Заданные пользователем преобразования](../../dotnet/user-defined-conversions-cpp-cli.md).  
  
## Пример  
 При компиляции следующего примера будет выдано предупреждение C4674.  
  
```  
// C4674.cpp // compile with: /clr /WX /W1 /LD ref class G { int op_Implicit(int i) {   // C4674 return 0; } };  
```  
  
## Пример  
 При компиляции следующего примера будет выдано предупреждение C4674.  
  
```  
// C4674_b.cpp // compile with: /clr:oldSyntax /W1 /LD __gc class G { int op_Implicit(int i) {   // C4674 // try the following line instead // static int op_Implicit(int i) { return 0; } };  
```