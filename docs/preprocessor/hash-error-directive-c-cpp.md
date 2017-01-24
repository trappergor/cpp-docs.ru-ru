---
title: "Директива #error (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#error"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#error - директива"
  - "error - директива (директива #error)"
  - "препроцессор, директивы"
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Директива #error (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Директива `#error` создает заданное пользователем сообщение об ошибке во время компиляции, а затем завершает компиляцию.  
  
## Синтаксис  
  
```  
#error token-string  
```  
  
## Заметки  
 Сообщение об ошибке, создаваемое этой директивой, содержит параметр *token\-string*.  Параметр `token-string` не подлежит расширению макроса.  Эта директива наиболее полезна в ходе предварительной обработки и позволяет уведомлять разработчика о противоречиях в программе или о нарушении ограничений.  В следующем примере демонстрируется обработка ошибки во время предварительной обработки.  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## См. также  
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)