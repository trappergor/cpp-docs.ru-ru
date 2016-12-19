---
title: "CManualAccessor::CreateParameterAccessor | Microsoft Docs"
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
  - "ATL::CManualAccessor::CreateParameterAccessor"
  - "ATL.CManualAccessor.CreateParameterAccessor"
  - "CManualAccessor.CreateParameterAccessor"
  - "CreateParameterAccessor"
  - "CManualAccessor::CreateParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateParameterAccessor - метод"
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CManualAccessor::CreateParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет память для структур привязки параметров и инициализирует элементов данных параметров.  
  
## Синтаксис  
  
```  
  
      HRESULT CreateParameterAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### Параметры  
 `nBindEntries`  
 \[in\] число столбцов.  
  
 `pBuffer`  
 \[in\] указатель на буфер, в котором входные столбцы сохраняются.  
  
 `nBufferSize`  
 \[in\] размер буфера в байтах.  
  
## Возвращаемое значение  
 Один из стандартных значений `HRESULT`.  
  
## Заметки  
 Необходимо вызвать эту функцию до вызова [AddParameterEntry](../Topic/CManualAccessor::AddParameterEntry.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)   
 [CManualAccessor::CreateAccessor](../Topic/CManualAccessor::CreateAccessor.md)   
 [CManualAccessor::AddParameterEntry](../Topic/CManualAccessor::AddParameterEntry.md)