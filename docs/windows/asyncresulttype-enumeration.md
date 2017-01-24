---
title: "Перечисление AsyncResultType | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncResultType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncResultType - перечисление"
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Перечисление AsyncResultType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает тип результата, возвращаемого методом GetResults\(\).  
  
## Синтаксис  
  
```  
enum AsyncResultType;  
```  
  
## Члены  
  
### Значения  
  
|Имя|Описание|  
|---------|--------------|  
|`MultipleResults`|Набор нескольких результатов, которые последовательно представлены между состоянием Start и до вызова Close\(\).|  
|`SingleResult`|Единственный результат, который представляется после возникновения события Complete.|  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)