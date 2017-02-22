---
title: "Функция AsWeak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak - функция"
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Функция AsWeak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает слабую ссылку на определенный экземпляр.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### Параметры  
 `T`  
 Указатель на тип параметра `p`.  
  
 `p`  
 Экземпляр типа.  
  
 `pWeak`  
 Когда эта операция будет завершена, указатель на слабую ссылку на параметр `p`.  
  
## Возвращаемое значение  
 S\_OK, если операция выполнена успешно; в противном случае ошибка HRESULT, которая указывает на причину сбоя.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)