---
title: ".CODE | Microsoft Docs"
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
  - ".CODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".CODE directive"
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .CODE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При использовании с .MODEL, указывающий начало участка кода.  
  
## Синтаксис  
  
```  
.CODE [[name]]  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`name`|Необязательный параметр, который задает имя сегмента кода.  Имя по умолчанию \_TEXT для малюсенького, маленького, компактного и плоского [модели](../../assembler/masm/dot-model.md).  Имя по умолчанию *modulename*\_TEXT для других моделей.|  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)