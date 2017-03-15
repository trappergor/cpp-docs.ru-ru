---
title: "Структура RuntimeClassFlags | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassFlags - структура"
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Структура RuntimeClassFlags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит тип экземпляра [RuntimeClass](../windows/runtimeclass-class.md).  
  
## Синтаксис  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### Параметры  
 `flags`  
 Значение [Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Члены  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа RuntimeClassFlags::value](../windows/runtimeclassflags-value-constant.md)|Содержит значение [Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md).|  
  
## Иерархия наследования  
 `RuntimeClassFlags`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)