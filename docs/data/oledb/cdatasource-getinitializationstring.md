---
title: "CDataSource::GetInitializationString | Microsoft Docs"
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
  - "ATL::CDataSource::GetInitializationString"
  - "CDataSource.GetInitializationString"
  - "GetInitializationString"
  - "CDataSource::GetInitializationString"
  - "ATL.CDataSource.GetInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInitializationString - метод"
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлечь строку инициализации источника данных, который в настоящее время открыт.  
  
## Синтаксис  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### Параметры  
 *pInitializationString*  
 \[out\] указатель на строку инициализации.  
  
 *bIncludePassword*  
 \[in\] **true**, если строка содержит пароль; в противном случае — значение **false**.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Результирующее строку инициализации можно использовать позже, чтобы снова открыть это соединение с источником данных.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataSource](../Topic/CDataSource%20Class.md)