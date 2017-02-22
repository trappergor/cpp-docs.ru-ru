---
title: "Метод RuntimeClass::GetTrustLevel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel - метод"
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод RuntimeClass::GetTrustLevel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает уровень доверия текущего объекта RuntimeClass.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
## Параметры  
 `trustLvl`  
 Если эта операция завершается, уровень доверия текущего объекта RuntimeClass.  
  
## Возвращаемое значение  
 Всегда значение S\_ОК.  
  
## Примечания  
 Добавляется утвержденная ошибка, если \_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO \_\_WRL\_STRICT\_\_or не определены.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)