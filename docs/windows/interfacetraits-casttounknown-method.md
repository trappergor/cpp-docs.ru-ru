---
title: "Метод InterfaceTraits::CastToUnknown | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown - метод"
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод InterfaceTraits::CastToUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### Параметры  
 `T`  
 Тип параметра `ptr`.  
  
 `ptr`  
 Указатель на тип `T`.  
  
## Возвращаемое значение  
 Указатель на IUnknown, для которого `Base` является производным.  
  
## Примечания  
 Приводит определенный указатель к указателю на IUnknown.  
  
 Дополнительные сведения о `Base` см. в разделе Общедоступные определения типов в [Структура InterfaceTraits](../windows/interfacetraits-structure.md).  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура InterfaceTraits](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)