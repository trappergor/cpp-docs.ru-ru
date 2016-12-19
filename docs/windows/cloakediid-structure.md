---
title: "Структура CloakedIid | Microsoft Docs"
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
  - "implements/Microsoft::WRL::CloakedIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CloakedIid - структура"
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура CloakedIid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает шаблонам RuntimeClass, Implements и ChainInterfaces, что заданный интерфейс не доступен в списке идентификаторов интерфейса.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### Параметры  
 `T`  
 Скрытый \(замаскированный\) интерфейс.  
  
## Примечания  
 Вот пример того, как используется CloakedIid: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## Иерархия наследования  
 `T`  
  
 `CloakedIid`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)