---
title: "Элемент данных FactoryCache::cookie | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::FactoryCache::cookie"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cookie - элемент данных"
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Элемент данных FactoryCache::cookie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)], а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## Заметки  
 Содержит значение, которое определяет зарегистрированный [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] или объект COM\-класса, а затем используется для отмены регистрации объекта.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура FactoryCache](../Topic/FactoryCache%20Structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)