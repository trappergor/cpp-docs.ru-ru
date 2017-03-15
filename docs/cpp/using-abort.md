---
title: "Использование функции abort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort - функция"
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Использование функции abort
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызов функции [abort](../c-runtime-library/reference/abort.md) приводит к немедленному завершению.  Выполняется обход нормального процесса удаления для инициализированных глобальных статических объектов.  Также осуществляется обход всей специальной обработки, которая была задана с помощью функции `atexit`.  
  
## См. также  
 [Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)