---
title: "// Комментарий конструкторов | Microsoft Docs"
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
  - "комментарии, комментарий конструкторов"
  - "комментарии, MFC - библиотека"
  - "конструкторы [C++], объявление"
  - "комментарий конструкторов"
  - "объявления, конструкторы"
  - "объявление конструкторов, комментарии к коду"
  - "конструкторы экземпляров, комментарии к коду"
  - "исходные файлы MFC, Комментарий конструкторов"
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Комментарий конструкторов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Раздел `// Constructors` объявления классов MFC объявляет конструкторы \(в смысле C C\+\+\), а все функции инициализации требуется фактически используемый объект.  Например, `CWnd::Create` в разделе конструкторов, поскольку перед использованием объекта `CWnd`, он должен быть создан «полностью» сначала вызвать конструктор C\+\+ и затем вызвать функцию **Создать**.  Как правило, эти члены являются открытыми.  
  
 Например, класс `CStdioFile` содержит 3 конструктора, один из которых отображается в списке в [Пример комментариев](../mfc/an-example-of-the-comments.md).  
  
## См. также  
 [Использование файлов с исходным кодом MFC](../Topic/Using%20the%20MFC%20Source%20Files.md)   
 [\/\/ Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [\/\/ Комментарий атрибутов](../Topic/--%20Attributes%20Comment.md)   
 [\/\/ Комментарий операций](../mfc/decrement-operations-comment.md)   
 [\/\/ Комментарий переопределяемости](../mfc/decrement-overridables-comment.md)