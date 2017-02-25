---
title: "Пример вызова. Прототип функции и вызов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "соглашения при вызове, примеры [C++]"
  - "примеры [C++], соглашения при вызове"
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Пример вызова. Прототип функции и вызов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 В следующем примере показаны результаты вызова функции с использованием различных соглашений о вызове.  
  
 Этот пример основан на следующей схеме функции.  Замените `calltype` соответствующим соглашением о вызове.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Дополнительные сведения см. в разделе [Пример результатов вызова](../Topic/Results%20of%20Calling%20Example.md).  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [Соглашения о вызовах](../Topic/Calling%20Conventions.md)