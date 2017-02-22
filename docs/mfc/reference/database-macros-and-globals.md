---
title: "Макросы и глобальные объекты баз данных | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "глобальные значения базы данных [C++]"
  - "макросы базы данных [C++]"
  - "глобальные функции базы данных [C++]"
  - "глобальные функции [C++], функции базы данных"
  - "макросы [C++], база данных MFC"
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Макросы и глобальные объекты баз данных
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Макросы и globals, перечисленные ниже, на основе ODBC\- приложений баз данных.  Они не используются с приложениями DAO\- зависимости.  
  
 Перед MFC 4.2, макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` указанным асинхронным операциям возможность создавать время для других процессов.  Начиная с версии MFC 4.2, реализация этих макросов изменилась, так как классы MFC ODBC используется только синхронные операции.  Макрос `AFX_ODBC_CALL` был заново с MFC 4.2.  
  
### Макросы базы данных  
  
|||  
|-|-|  
|[AFX\_ODBC\_CALL](../Topic/AFX_ODBC_CALL.md)|Вызывает функцию ODBC API, возвращает `SQL_STILL_EXECUTING`.  `AFX_ODBC_CALL` повторно вызывает функцию до тех пор, пока она больше не возвращает `SQL_STILL_EXECUTING`.|  
|[AFX\_SQL\_ASYNC](../Topic/AFX_SQL_ASYNC.md)|Вызывает `AFX_ODBC_CALL`.|  
|[AFX\_SQL\_SYNCHRONIZATION](../Topic/AFX_SQL_SYNC.md)|Вызывает функцию API ODBC, не возвращающей `SQL_STILL_EXECUTING`.|  
  
### База данных Globals  
  
|||  
|-|-|  
|[AfxGetHENV](../Topic/AfxGetHENV.md)|Возвращает дескриптор среде ODBC в использовании MFC.  Можно использовать этот дескриптор непосредственно в вызовах ODBC.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)