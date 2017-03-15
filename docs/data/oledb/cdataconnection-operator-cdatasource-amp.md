---
title: "CDataConnection::operator CDataSource&amp; | Microsoft Docs"
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
  - "CDataSource&"
  - "CDataConnection.operatorCDataSource&"
  - "operatorCDataSource&"
  - "CDataConnection::operatorCDataSource&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource& - оператор"
  - "оператор & (CDataSource)"
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CDataSource&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает ссылку на объект, который содержит `CDataSource`.  
  
## Синтаксис  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## Заметки  
 Этот оператор возвращает ссылку на объект, который содержит `CDataSource`, позволяя тем самым передать объект `CDataConnection`, ссылка `CDataSource` ожидается.  
  
## Пример  
 Если имеется функция, \(например, `func` ниже\), принимает ссылку `CDataSource` можно использовать **CDataSource&** передать объект `CDataConnection` вместо.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataConnection](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource\*](../Topic/CDataConnection::operator%20CDataSource*.md)