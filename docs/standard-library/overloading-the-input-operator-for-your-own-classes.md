---
title: "Перегрузка оператора &gt;&gt; для собственных классов | Microsoft Docs"
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
  - ">> - оператор, перегрузка собственных классов"
  - ">> - оператор"
  - ">> - оператор, перегрузка собственных классов"
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Перегрузка оператора &gt;&gt; для собственных классов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Входные потоки используют оператор извлечения \(`>>`\) для стандартных типов.  Можно написать аналогичные операторы извлечения для собственных типов. для выполнения зависит от использовании пространства явно.  
  
 Ниже приведен пример оператора извлечения для класса `Date`, представленный выше.  
  
```  
istream& operator>> ( istream& is, Date& dt )  
{  
   is >> dt.mo >> dt.da >> dt.yr;  
   return is;  
}  
```  
  
## См. также  
 [Потоки ввода](../standard-library/input-streams.md)