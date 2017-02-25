---
title: "Ошибка компилятора C2030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2030"
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed  
  
 Класс среды выполнения Windows, объявленный как `sealed`, не может содержать защищенный закрытый деструктор.  Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы.  Подробнее: [Классы и структуры ссылки](../Topic/Ref%20classes%20and%20structs%20\(C++-CX\).md)  
  
 Чтобы устранить эту ошибку, измените тип доступа деструктора.