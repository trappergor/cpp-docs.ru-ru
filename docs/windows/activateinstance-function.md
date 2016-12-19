---
title: "Функция ActivateInstance | Microsoft Docs"
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
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance - функция"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция ActivateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистрирует и извлекает экземпляр указанного типа, определенного в указанном идентификаторе класса.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### Параметры  
 `T`  
 Активируемый тип.  
  
 `activatableClassId`  
 Имя идентификатора класса, который определяет параметр `T`.  
  
 `instance`  
 Когда эта операция завершена, ссылка на экземпляр `T`.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае ошибка HRESULT указывает причину ошибки.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Windows::Foundation  
  
## См. также  
 [Пространство имен Windows::Foundation](../Topic/Windows::Foundation%20Namespace.md)