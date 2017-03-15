---
title: "CDataConnection::operator CSession* | Microsoft Docs"
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
  - "CDataConnection.operatorCSession*"
  - "CDataConnection::operatorCSession*"
  - "operatorCSession*"
  - "CSession*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession* - оператор"
  - "оператор CSession*"
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession*
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает указатель на объект, который содержит `CSession`.  
  
## Синтаксис  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## Заметки  
 Этот оператор возвращает указатель на объект, который содержит `CSession`, позволяя тем самым передать объект `CDataConnection` место указателя `CSession` ожидаемому.  
  
## Пример  
 В разделе [оператор CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) для примера потребления.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataConnection](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)