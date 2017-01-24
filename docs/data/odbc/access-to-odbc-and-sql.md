---
title: "Доступ к ODBC и SQL | Microsoft Docs"
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
  - "вызовы API [C++], прямой вызов DAO или ODBC"
  - "ODBC [C++], функции API"
  - "функции ODBC библиотек API [C++]"
  - "функции ODBC библиотек API [C++], вызов из MFC"
  - "SQL [C++], вызовы ODBC функций API"
  - "Windows API [C++], вызов из MFC"
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Доступ к ODBC и SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотека Microsoft Foundation Class инкапсулирует многие вызовы Windows API и позволяет напрямую вызывать любую функцию Windows API.  Классы базы данных предоставляют такую же гибкость, что и ODBC API.  Классы базы данных позволяют обходить сложности ODBC и напрямую вызывать функции ODBC API в любой программе.  
  
 Аналогично классы базы данных ограждают от работы с [SQL](../../data/odbc/sql.md), однако, позволяют напрямую использовать необходимую функцию SQL.  Можно настроить объекты набора записей, передавая настраиваемую инструкцию SQL \(или часть параметров инструкции, установленных по умолчанию\) во время открытия набора записей.  Вызовы SQL также можно осуществлять, напрямую используя функцию\-член [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) класса [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Дополнительные сведения см. в разделах [ODBC: прямые запросы функций ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) и [SQL: прямые запросы SQL \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## См. также  
 [ODBC и MFC](../../data/odbc/odbc-and-mfc.md)