---
title: "Ошибка компилятора C2865 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2865"
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" : недопустимое сравнение для дескриптора\_или\_указателя  
  
 Ссылки можно сравнивать с [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или типами [\_\_gc](../Topic/__gc.md) только на равенство, чтобы проверить, являются ли они ссылками на один и тот же объект \("\=\="\) или на разные объекты \("\!\="\).  
  
 Сравнение порядка к ним неприменимо, поскольку среда выполнения.NET может в любое время переместить управляемые объекты, тем самым изменяя результат проверки.