---
title: "Предупреждение средств компоновщика LNK4102 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4102"
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение средств компоновщика LNK4102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

экспорт деструктора удаления "имя"; образ может неправильно выполняться  
  
 Программа попыталась экспортировать удаленный деструктор.  В результате удаление может быть выполнено на границе DLL, что может привести к тому, что процесс сможет освободить память, которой у него не было.  Убедитесь, что данный символ не присутствует в DEF\-файле и не используется в качестве аргумента параметра **\/IMPORT** или **\/EXPORT** в командной строке компоновщика.  
  
 Если производится перепостроение библиотеки времени выполнения C, это сообщение можно пропустить.