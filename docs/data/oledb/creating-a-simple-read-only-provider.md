---
title: "Создание простого поставщика только для чтения | Microsoft Docs"
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
  - "шаблоны поставщика OLE DB, создание поставщиков"
  - "поставщики OLE DB, создание"
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Создание простого поставщика только для чтения
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

После создания поставщика OLE DB с помощью мастера проектов ATL и мастера поставщика ATL OLE DB можно добавить дополнительную функциональность.  Перед началом создания поставщика необходимо узнать, какие данные будут отправляться объекту\-получателю и при каких условиях.  Особенно важно определить, потребуется ли поддержка команд, транзакций и других дополнительных объектов.  Качественная разработка поставщика обеспечит быструю реализацию и тестирование.  
  
 Пример состоит из двух частей:  
  
-   В первой части показано [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md), который считывает пары строк.  
  
-   Во второй части показано, как [расширить простой поставщик только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) путем добавления интерфейса `IRowsetLocate`.  
  
## См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)