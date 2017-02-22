---
title: "Неправильный доступ к объединению | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Неправильный доступ к объединению
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.3.2.3** Доступ к члену объекта объединения с помощью члена другого типа  
  
 Если объявляется объединение двух типов и сохраняется одно значение, но для доступа к объединению используется другой тип, результаты будут ненадежными.  
  
 Например, объявлено объединение **float** и `int`.  Значение **float** сохраняется, но впоследствии программа обращается к значению как к `int`.  В этом случае значение будет зависеть от внутреннего хранилища значений **float**.  Целочисленное значение будет ненадежным.  
  
## См. также  
 [Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)