---
title: "ML Error Messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.errors.ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), ML error messages"
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ML Error Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сообщения об ошибках, создаваемые компонентами MASM подразделяются на категории: 3  
  
-   **неустранимые ошибки.** Они указывают на проблему, которая не позволяет строгую программу из своего обычного выполнения процесса.  
  
-   **Некритичные ошибки.** Программа может запустить его процесса.  Если он заставляет, то его результат не может быть одним требуется.  
  
-   **Предупреждений.** Эти сообщения перечислены условия, которые могут помешать получение результатов.  
  
 Все сообщения об ошибках имеют следующую форму:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 Здесь:  
  
 `Utility`  
 Программа, отправившей сообщение об ошибке.  
  
 *FileName*  
 Файл, содержащий ошибка\-производя условие.  
  
 *Строка*  
 Приблизительная линия, где условие ошибки.  
  
 *Error\_type*  
 Неустранимая ошибка, ошибка или предупреждение.  
  
 *Код*  
 Уникальный или код ошибки 5 \- 6 разрядов.  
  
 `Message_text`  
 Короткое и общее описание условия ошибки.  
  
## См. также  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)