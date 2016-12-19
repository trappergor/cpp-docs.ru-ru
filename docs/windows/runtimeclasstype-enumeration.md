---
title: "Перечисление RuntimeClassType | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassType - перечисление"
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Перечисление RuntimeClassType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет поддерживаемый тип экземпляра [RuntimeClass](../windows/runtimeclass-class.md).  
  
## Синтаксис  
  
```  
enum RuntimeClassType;  
```  
  
## Члены  
  
### Значения  
  
|Имя|Описание|  
|---------|--------------|  
|`ClassicCom`|Класс среды выполнения классической модели COM.|  
|`Delegate`|Аналогично параметру **ClassicCom**.|  
|`InhibitFtmBase`|Отключает поддержку `FtmBase`, если `__WRL_CONFIGURATION_LEGACY__` не определено.|  
|`InhibitWeakReference`|Отключает поддержку слабой ссылки.|  
|`WinRt`|Класс [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|`WinRtClassicComMix`|Комбинация `WinRt` и `ClassicCom`.|  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)