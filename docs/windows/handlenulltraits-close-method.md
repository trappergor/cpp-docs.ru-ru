---
title: "Метод HANDLENullTraits::Close | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close - метод"
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод HANDLENullTraits::Close
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Закрывает указанный дескриптор.  
  
## Синтаксис  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### Параметры  
 `h`  
 Дескриптор, который необходимо закрыть.  
  
## Возвращаемое значение  
 **true**, если дескриптор `h` закрыт успешно; в противном случае — значение **false**.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Структура HANDLENullTraits](../windows/handlenulltraits-structure.md)