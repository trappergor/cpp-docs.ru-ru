---
title: "Схемы подготовки к отправке | Microsoft Docs"
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
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "макросы схемы отправки"
  - "съемы подготовки к отправке"
  - "макросы схем отправки"
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Схемы подготовки к отправке
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ole\-автоматизации предоставляет способы в вызовы методов и свойств доступа между приложениями.  Механизм, библиотеки Microsoft Foundation Class для подготовки эти запросы «схема подготовки к сообщению,», которая обозначает внутренние и внешние имена функций и свойств объекта, так и типы данных, свойств и аргументов функции.  
  
### Схемы подготовки к отправке  
  
|||  
|-|-|  
|[DECLARE\_DISPATCH\_MAP](../Topic/DECLARE_DISPATCH_MAP.md)|Объявляет, что схема подготовки к сообщению будет использоваться для предоставления методы и свойства класса \(не используется в объявлении класса\).|  
|[BEGIN\_DISPATCH\_MAP](../Topic/BEGIN_DISPATCH_MAP.md)|Запускает определение схемы подготовки к сообщению.|  
|[END\_DISPATCH\_MAP](../Topic/END_DISPATCH_MAP.md)|Завершите определение схемы подготовки к сообщению.|  
|[DISP\_FUNCTION](../Topic/DISP_FUNCTION.md)|Используется в схеме подготовки к сообщению, чтобы определить функцию ole\-автоматизации.|  
|[DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)|Определяет свойство ole\-автоматизации.|  
|[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)|Определяет свойства и имена ole\-автоматизации получение и установка функции.|  
|[DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)|Определяет свойство ole\-автоматизации с уведомлением.|  
|[DISP\_PROPERTY\_PARAM](../Topic/DISP_PROPERTY_PARAM.md)|Определяет свойство ole\-автоматизации, параметрами и получение и установка функции.|  
|[DISP\_DEFVALUE](../Topic/DISP_DEFVALUE.md)|Выполняет существующим свойством значение по умолчанию объекта.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)