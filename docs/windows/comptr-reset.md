---
title: "ComPtr::Reset | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::Reset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Освобождает все ссылки на указатель на интерфейс, который связан с данным объектом ComPtr.  
  
## Синтаксис  
  
```  
unsigned long Reset();  
```  
  
## Возвращаемое значение  
 Число освобожденных ссылок, если таковые имеются.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)