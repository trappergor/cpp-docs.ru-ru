---
title: "Интерфейсы объекта источника данных | Microsoft Docs"
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
  - "объекты источников данных [C++]"
  - "объекты источников данных [C++], интерфейсы"
  - "интерфейсы [C++], список"
  - "интерфейсы [C++], OLE DB"
  - "OLE DB [C++], интерфейсы"
  - "шаблоны поставщика OLE DB [C++], интерфейсы объектов"
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Интерфейсы объекта источника данных
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В таблице представлены обязательные и дополнительные интерфейсы, определенные OLE DB для объекта источника данных.  
  
|Интерфейс|Обязательный?|Реализован шаблонами OLE DB?|  
|---------------|-------------------|----------------------------------|  
|`IDBCreateSession`|Обязательно|Да|  
|`IDBInitialize`|Обязательно|Да|  
|`IDBProperties`|Обязательно|Да|  
|[\<caps:sentence id\="tgt14" sentenceid\="731a3344bc1c6b5f8f54d9de3524f18a" class\="tgtSentence"\>IPersist\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Обязательно|Да|  
|[\<caps:sentence id\="tgt17" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Необязательный|Нет|  
|`IDBDataSourceAdmin`|Необязательный|Нет|  
|`IDBInfo`|Необязательный|Нет|  
|[\<caps:sentence id\="tgt26" sentenceid\="7e6a12ecd4cb3b1bd45dccf9421ed567" class\="tgtSentence"\>IPersistFile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Необязательный|Нет|  
|`ISupportErrorInfo`|Необязательный|Нет|  
  
 Объект источника данных реализует интерфейсы `IDBProperties`, `IDBInitialize` и `IDBCreateSession` посредством наследования.  Можно выбрать поддержку дополнительных функций путем наследования или не наследования из одного из этих классов реализации.  Для обеспечения поддержки интерфейса `IDBDataSourceAdmin` необходимо наследовать от класса `IDBDataSourceAdminImpl`.  
  
## См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)