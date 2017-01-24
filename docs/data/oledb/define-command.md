---
title: "DEFINE_COMMAND | Microsoft Docs"
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
  - "DEFINE_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND - макрос"
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет команду, которая будет использоваться для создания набора строк при использовании класса [CCommand](../../data/oledb/ccommand-class.md).  Принимает только строковые типы, соответствующие определенному типу приложения \(ANSI или юникод\).  
  
> [!NOTE]
>  Рекомендуется использовать [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`.  
  
## Синтаксис  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### Параметры  
 *x*  
 \[in\] имя класса записей пользователя \(команды\).  
  
 `szCommand`  
 \[in\] командная строка, используемая для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
## Заметки  
 Командная строка, которая будет использоваться по умолчанию, если не указан текст команды в методе [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
 Этот макрос принимает строку ANSI при построении приложения в качестве строки ANSI или юникода, при построении приложения в кодировке юникод.  Рекомендуется использовать [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`, поскольку первый принимает строку юникода, вне зависимости от типа приложения ANSI или юникод.  
  
## Пример  
 В разделе [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)