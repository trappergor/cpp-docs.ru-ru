---
title: "Метод ActivationFactory::GetTrustLevel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel - метод"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ActivationFactory::GetTrustLevel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает уровень доверия объекта, который инициализируется текущим ActivationFactory.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### Параметры  
 `trustLvl`  
 Когда эта операция завершается, уровень доверия класса среды выполнения, который инициализируется ActivationFactory.  
  
## Возвращаемое значение  
 S\_ОК в случае успеха; в противном случае появляется ошибка, и `trustLvl` устанавливается на FullTrust.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)