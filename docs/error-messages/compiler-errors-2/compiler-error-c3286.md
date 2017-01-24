---
title: "Ошибка компилятора C3286 | Microsoft Docs"
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
  - "C3286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3286"
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"спецификатор": переменная цикла не может иметь спецификаторы класса хранения  
  
 Для получения дополнительной информации см. [\(NOTINBUILD\)Спецификаторы классов хранения](http://msdn.microsoft.com/ru-ru/10b3d22d-cb40-450b-994b-08cf9a211b6c).  
  
 Дополнительные сведения см. в разделе [for each, in](../../dotnet/for-each-in.md).  
  
## Пример  
 В следующем примере возникает ошибка C3286:  
  
```  
// C3286.cpp // compile with: /clr int main() { array<int> ^p = { 1, 2, 3 }; for each (static int i in p) {}   // C3286 for each (int j in p) {}   // OK }  
```