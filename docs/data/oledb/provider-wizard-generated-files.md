---
title: "Созданные мастером поставщика файлы | Microsoft Docs"
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
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Созданные мастером поставщика файлы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Мастер поставщика ATL OLE DB создает следующие файлы.  В разделах используется краткое обозначение "MyProvider", однако, конкретные имена файлов зависят от выбора пользователя во время создания поставщика.  
  
|Имя файла|Описание|  
|---------------|--------------|  
|MyProviderRS.cpp|Содержит метод поддержки команд `Execute` и сопоставления столбца поставщика.|  
|MyProviderDS.h|Реализует объект источника данных.  Файл заголовка содержит сопоставляемые свойства в параметрах источника данных.|  
|MyProviderDS.h|Реализует объекты команд и наборов строк  Файл заголовка содержит сопоставляемые свойства в параметрах набора срок и команд.|  
|MyProviderSess.h|Реализует объект сеанса.  Файл заголовка содержит сопоставляемые свойства в параметрах сеанса.|  
|MyProvider.rgs|Содержит зарегистрированные объекты, созданные мастером поставщика OLE DB.|  
  
## См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)