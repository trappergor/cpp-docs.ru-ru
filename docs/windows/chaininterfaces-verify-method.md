---
title: "Метод ChainInterfaces::Verify | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify - метод"
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод ChainInterfaces::Verify
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет, что каждый интерфейс, заданный параметрами `I0` шаблона через `I9` наследуется от IUnknown и\/или IInspectable, и что `I0` наследуется от `I1` через `I9`.  
  
## Синтаксис  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## Примечания  
 Если операция проверки завершается ошибкой, `static_assert` выдает сообщение об ошибке, описывающее сбой.  
  
## Примечания  
 Параметры `I0` и `I1` шаблона являются обязательными, а параметры с `I2` до `I9` являются необязательными.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)