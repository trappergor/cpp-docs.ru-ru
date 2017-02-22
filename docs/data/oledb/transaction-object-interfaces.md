---
title: "Интерфейсы объекта транзакции | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы, список"
  - "интерфейсы, OLE DB"
  - "шаблоны поставщика OLE DB, интерфейсы объектов"
  - "поставщики OLE DB, поддержка транзакций"
  - "OLE DB, интерфейсы"
  - "интерфейсы объекта транзакции"
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Интерфейсы объекта транзакции
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект транзакции определяет неделимую единицу работы в источнике данных и отношения этих единиц друг к другу.  Этот объект не поддерживается непосредственно шаблонами поставщика OLE DB \(это означает, что его необходимо создавать\).  
  
 В следующей таблице приведены обязательные и необязательные интерфейсы, определенные в OLE DB для объекта транзакции.  
  
|Интерфейс|Обязательный?|Реализован шаблонами OLE DB?|  
|---------------|-------------------|----------------------------------|  
|[\<caps:sentence id\="tgt7" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Обязательно|Нет|  
|[\<caps:sentence id\="tgt10" sentenceid\="f5097e646bb93cceb560c38e13953a89" class\="tgtSentence"\>ITransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Обязательно|Нет|  
|[\<caps:sentence id\="tgt13" sentenceid\="130702210bcc45e1afd88b1f2aae1a0b" class\="tgtSentence"\>ISupportErrorInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Необязательный|Нет|  
  
## См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)