---
title: "Класс CNoMultipleResults | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CNoMultipleResults"
  - "ATL.CNoMultipleResults"
  - "ATL::CNoMultipleResults"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoMultipleResults - класс"
ms.assetid: 343e77c4-b319-476e-b592-901ab9b2f34e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CNoMultipleResults
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется как аргумент шаблона \(*TMultiple*\) в [CCommand](../../data/oledb/ccommand-class.md) для создания оптимизированная команду, которая обрабатывает один результирующий набор.  
  
## Синтаксис  
  
```  
class CNoMultipleResults  
```  
  
## Заметки  
 Если требуется команду обрабатывать несколько результирующих наборов, используйте [CMultipleResults](../../data/oledb/cmultipleresults-class.md).  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)