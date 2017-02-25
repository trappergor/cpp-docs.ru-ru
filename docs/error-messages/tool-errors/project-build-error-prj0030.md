---
title: "Ошибка построения проекта PRJ0030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0030"
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка построения проекта PRJ0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ошибка раскрытия макроса.Рекурсия при вычислении макроса $\(макрос\) превысила 32 уровня.  
  
 Причина этой ошибки — рекурсия в макросах.  Например, если задать для свойства **Промежуточный каталог** \(см. раздел [Страница свойств "Общие" \(Проект\)](../Topic/General%20Property%20Page%20\(Project\).md)\) значение $\(IntDir\), то будет возникать рекурсия.  
  
 Для устранения этой ошибки следует избегать определения макросов с помощью макросов, в свою очередь определяемых с их помощью.