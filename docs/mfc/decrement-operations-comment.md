---
title: "// Комментарий операций | Microsoft Docs"
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
  - "комментарии, MFC - библиотека"
  - "исходные файлы MFC, Комментарии операций"
  - "Комментарий операций в исходных файлах MFC"
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Комментарий операций
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Раздел `// Operations` объявления классов MFC содержит функции\-члены, которые можно вызвать для объекта, чтобы сделать его выполняют действия или выполняют действия \(выполнение операций\).  Обычно эти функции не **const**, поскольку они обычно есть побочные эффекты.  Они могут быть виртуальный или невиртуальная в зависимости от класса.  Как правило, эти члены являются открытыми.  
  
 В списке примера из класса `CStdioFile`, в [Пример комментариев](../mfc/an-example-of-the-comments.md), приведены 2 функции\-члена в нее комментария: `ReadString` и `WriteString`.  
  
 Как и в случае с атрибутами, операции можно более таким образом разделить.  
  
## См. также  
 [Использование файлов с исходным кодом MFC](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [Пример комментариев](../mfc/an-example-of-the-comments.md)   
 [\/\/ Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [\/\/ Комментарий конструкторов](../mfc/decrement-constructors-comment.md)   
 [\/\/ Комментарий атрибутов](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Комментарий переопределяемости](../mfc/decrement-overridables-comment.md)