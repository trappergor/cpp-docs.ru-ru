---
title: "Метод ComPtr::Get | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Get - метод"
ms.assetid: 078eee51-7bca-4924-a74b-cd4f6a05de31
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ComPtr::Get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает указатель на интерфейс, который связан с этим ComPtr.  
  
## Синтаксис  
  
```  
T* Get() const;  
```  
  
## Возвращаемое значение  
 Указатель на интерфейс, связанный с данным объектом ComPtr.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)