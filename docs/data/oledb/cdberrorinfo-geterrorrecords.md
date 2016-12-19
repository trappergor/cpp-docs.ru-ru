---
title: "CDBErrorInfo::GetErrorRecords | Microsoft Docs"
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
  - "CDBErrorInfo.GetErrorRecords"
  - "ATL.CDBErrorInfo.GetErrorRecords"
  - "ATL::CDBErrorInfo::GetErrorRecords"
  - "GetErrorRecords"
  - "CDBErrorInfo::GetErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorRecords - метод"
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает записи ошибок для указанного объекта.  
  
## Синтаксис  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### Параметры  
 *панк*  
 \[in\] интерфейс на объект, для которого получается записи ошибок.  
  
 `iid`  
 \[in\] идентификатор IID интерфейса, связанного с ошибкой.  
  
 *pcRecords*  
 \[out\] указатель на число \(единицы\) записей ошибок.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Используйте первую форму функции, если необходимо проверить, которых интерфейс для доступа к информации об ошибке из.  В противном случае следует использовать вторую форму.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)