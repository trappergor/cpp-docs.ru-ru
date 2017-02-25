---
title: "Преобразование данных, не поддерживаемых поставщиком | Microsoft Docs"
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
  - "шаблоны поставщика OLE DB, неподдерживаемые типы данных"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Преобразование данных, не поддерживаемых поставщиком
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При запросе объектом\-получателем типа данных, не поддерживаемых поставщиком, для преобразования типа данных с помощью кода шаблона поставщика OLE DB для `IRowsetImpl::GetData` вызывается Msdadc.dll.  
  
 При реализации подобного интерфейса `IRowsetChange` требующего преобразования данных для выполнения преобразования можно вызвать Msdaenum.dll.  Используйте `GetData` определенный в Atldb.h, в качестве примера.  
  
## См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)