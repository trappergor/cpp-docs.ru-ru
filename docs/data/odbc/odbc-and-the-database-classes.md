---
title: "ODBC и классы баз данных | Microsoft Docs"
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
  - "классы баз данных [C++], ODBC"
  - "MFC [C++], ODBC и"
  - "функции ODBC библиотек API [C++]"
  - "классы ODBC [C++], MFC-классы баз данных"
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC и классы баз данных
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы баз данных ODBC библиотеки MFC инкапсулируют вызовы функций API ODBC, которые обычно приходится реализовывать самостоятельно в функциях\-членах классов [CDatabase](../../mfc/reference/cdatabase-class.md) и [CRecordset](../Topic/CRecordset%20Class.md).  В качестве примера можно привести сложные последовательности вызовов ODBC, привязку возвращаемых записей к хранилищу, обработку ошибок и другие операции, которые выполняют классы баз данных.  В результате используется намного более простой интерфейс класса для обработки записей с использованием объекта набора записей.  
  
> [!NOTE]
>  Источники данных ODBC доступны с помощью классов ODBC MFC, как описано в данном разделе, или с помощью классов DAO MFC.  
  
 Хотя классы баз данных инкапсулируют функциональность ODBC, они не предоставляют полного соответствия функциям API ODBC.  Классы баз данных предоставляют более высокий уровень абстракций, смоделированных на основе объектов доступа к данным, используемых в Microsoft Access и Microsoft Visual Basic.  Дополнительные сведения см. в разделе [Описание модели программирования баз данных библиотеки MFC](../../data/what-is-the-mfc-database-programming-model-q.md).  
  
## См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)