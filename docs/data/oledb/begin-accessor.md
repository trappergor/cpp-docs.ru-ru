---
title: "BEGIN_ACCESSOR | Microsoft Docs"
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
  - "BEGIN_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR - макрос"
  - "BEGIN_ACCESSOR - макрос, синтаксис"
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обозначает начало записи доступа.  
  
## Синтаксис  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### Параметры  
 *num*  
 \[in\] число нулевым смещения для доступа в этом сопоставлении доступа.  
  
 *bAuto*  
 \[in\] указывает, этот метод доступа к автоматический или ручной доступ.  Если **true**, доступ автоматическо; если **false**, доступ вручную.  Автоматический доступ означает, что данные осуществляется удаленный доступ для разработчика в операциях перемещения.  
  
## Заметки  
 В случае нескольких объектов доступа на наборе строк, необходимо определить `BEGIN_ACCESSOR_MAP` и использовать макрос `BEGIN_ACCESSOR` для каждого отдельного доступа.  Макрос `BEGIN_ACCESSOR` завершен с макросом `END_ACCESSOR`.  Макрос `BEGIN_ACCESSOR_MAP` завершен с макросом `END_ACCESSOR_MAP`.  
  
## Пример  
 В разделе [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)