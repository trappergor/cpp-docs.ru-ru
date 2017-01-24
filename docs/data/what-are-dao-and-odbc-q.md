---
title: "Что такое DAO и ODBC? | Microsoft Docs"
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
  - "доступ к данным DAO.NET, и ODBC"
  - "ODBC, сведения об ODBC"
ms.assetid: 22cc2f75-7ff6-47bc-ac56-56a40591104c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Что такое DAO и ODBC?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Data Access Objects \(DAO\) и Open Database Connectivity \(ODBC\) — это интерфейсы API, предоставляющие возможность создания приложений, независимых от каких\-либо конкретных систем управления базами данных \(СУБД\).  
  
 Интерфейс DAO знаком разработчикам приложений баз данных, использующим Microsoft Access Basic или Microsoft Visual Basic.  DAO использует ядро баз данных Microsoft Jet, предоставляя набор объектов для доступа к данным: объекты баз данных, TableDef и QueryDef, объекты наборов данных и другие объекты.  DAO оптимизирован для работы с MDB\-файлами, создаваемыми Microsoft Access, но программисты также могут осуществлять доступ к источникам данных ODBC с помощью DAO и ядра баз данных Microsoft Jet.  
  
 ODBC предоставляет интерфейс API, методы которого различные поставщики баз данных реализуют через драйверы ODBC, специфичные для конкретной СУБД.  Приложения баз данных используют этот интерфейс API для вызова диспетчера драйверов ODBC, который переадресует вызовы соответствующему драйверу.  Драйвер, в свою очередь, взаимодействует с СУБД с помощью SQL.  
  
> [!NOTE]
>  ODBC является основной частью архитектуры открытых стандартов \(Microsoft Windows Open Standards Architecture — WOSA\).  DAO оптимизирован для работы с ядром баз данных Microsoft Jet, но программистам также доступны средства ODBC и другие внешние источники данных с этим ядром; отдельный интерфейс ODBC API и классы MFC, основанные на этом интерфейсе, по\-прежнему доступны и играют свою роль при выборе инструментов баз данных.  
  
## См. также  
 [Часто задаваемые вопросы по теме доступа к данным](../data/data-access-frequently-asked-questions-mfc-data-access.md)