---
title: "_com_error::HRESULTToWCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HRESULTToWCode"
  - "_com_error.HRESULTToWCode"
  - "_com_error::HRESULTToWCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRESULTToWCode - метод"
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HRESULTToWCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляет 32\-разрядное значение `HRESULT` с 16\-разрядным `wCode`.  
  
## Синтаксис  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### Параметры  
 `hr`  
 32\-разрядное значение `HRESULT`, которое будет сопоставлено с 16\-разрядным `wCode`.  
  
## Возвращаемое значение  
 16\-разрядный `wCode`, с которым будет сопоставлено 32\-разрядное значение `HRESULT`.  
  
## Заметки  
 Дополнительные сведения см. в разделе [\_com\_error::WCode](../cpp/com-error-wcode.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)   
 [Класс \_com\_error](../cpp/com-error-class.md)