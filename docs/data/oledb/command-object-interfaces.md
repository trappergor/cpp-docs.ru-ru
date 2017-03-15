---
title: "Интерфейсы объекта команды | Microsoft Docs"
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
  - "интерфейсы объекта команды [C++]"
  - "командные объекты [OLE DB]"
  - "OLE DB [C++], интерфейсы объекта команды"
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Интерфейсы объекта команды
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект команды использует интерфейс `IAccessor` для указания привязок параметров.  Объект\-получатель вызывает объект `IAccessor::CreateAccessor`, передавая ему массив структур `DBBINDING`.  Структура `DBBINDING` содержит сведения о привязках к столбцам \(например, их тип и длина\).  Поставщик получает структуры и определяет способ передачи данных и необходимость преобразований.  
  
 Интерфейс `ICommandText` обеспечивает способ определения текстовой команды.  Интерфейс `ICommandProperties` обрабатывает все свойства команд.  
  
## См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)