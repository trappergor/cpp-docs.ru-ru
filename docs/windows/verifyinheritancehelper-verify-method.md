---
title: "Метод VerifyInheritanceHelper::Verify | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify - метод"
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод VerifyInheritanceHelper::Verify
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
static void Verify();  
```  
  
## Примечания  
 Проверяет два интерфейса, заданные текущими параметрами шаблона, и определяет, является ли один интерфейс производным от другого.  
  
 Ошибка выдается, если один интерфейс не является производным от другого.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура VerifyInheritanceHelper](../windows/verifyinheritancehelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)