---
title: "DEFINE_COMMAND_EX | Microsoft Docs"
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
  - "DEFINE_COMMAND_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND_EX - макрос"
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md).  Поддерживает юникод и приложения ANSI.  
  
## Синтаксис  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### Параметры  
 *x*  
 \[in\] имя класса записей пользователя \(команды\).  
  
 `wszCommand`  
 \[in\] командная строка, используемая для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
## Заметки  
 Командная строка, которая будет использоваться по умолчанию, если не указан текст команды в методе [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
 Этот макрос принимает строку юникода, вне зависимости от типа приложения.  Этот макрос предпочтительно на [DEFINE\_COMMAND](../../data/oledb/define-command.md), поскольку он поддерживает юникод, так и приложения ANSI.  
  
## Пример  
 В разделе [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)