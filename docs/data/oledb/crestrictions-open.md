---
title: "CRestrictions::Open | Microsoft Docs"
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
  - "CRestrictions.Open"
  - "ATL::CRestrictions::Open"
  - "ATL.CRestrictions.Open"
  - "CRestrictions::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open - метод"
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает результирующий набор в соответствии с предоставленным пользователем ограничений.  
  
## Синтаксис  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### Параметры  
 `session`  
 \[in\] определяет объект существующего сеанса, используемый для подключения к источнику данных.  
  
 *lpszParam*  
 \[in\] определяющий ограничения в наборе строк схемы.  
  
 `bBind`  
 \[in\] указывает ли привязка сопоставление столбцов автоматически.  Значение по умолчанию **true**, которое вызывает сопоставление столбцов, привязанным автоматически.  Параметр `bBind` в **false** предотвращает автоматическую привязку сопоставления столбцов, чтобы можно было выполнить вручную. \(Ручная привязка представляет особый интерес для пользователей OLAP\).  
  
## Возвращаемое значение  
 Один из стандартных значений `HRESULT`.  
  
## Заметки  
 Можно задать не более 7 ограничений в наборе строк схемы.  
  
 В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) сведения об определенных ограничениях каждый набор строк схемы.  
  
## Требования  
 **Header:** atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)