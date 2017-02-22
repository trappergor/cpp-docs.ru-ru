---
title: "Сопоставления свойств | Microsoft Docs"
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
  - "соответствия, свойство"
  - "поставщики OLE DB, свойства"
  - "сопоставления свойств"
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Сопоставления свойств
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Кроме сеансов, наборов строк и дополнительных объектов команды каждый поставщик поддерживает одно или несколько свойств.  Эти свойства определяются в сопоставлениях свойств, содержащихся в файлах заголовков, которые создаются с помощью мастера поставщиков OLE DB.  Каждый файл заголовка содержит сопоставление для свойств в группе свойств OLE DB, определенных для объекта или объектов, которые определены в этом файле.  Файл заголовка, содержащий объект источника данных, также содержит сопоставление свойств для [свойств DataSource](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx).  Файл Session.h содержит сопоставление свойств для [свойств Session](https://msdn.microsoft.com/en-us/library/ms714221.aspx).  Объекты наборов строк и команд содержатся в одном файле заголовка *имяПроекта*RS.h.  Эти свойства являются членами группы [свойств Rowset](https://msdn.microsoft.com/en-us/library/ms711252.aspx).  
  
## См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)