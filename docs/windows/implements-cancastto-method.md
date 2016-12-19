---
title: "Метод Implements::CanCastTo | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Implements::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo - метод"
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Implements::CanCastTo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает указатель на указанный интерфейс.  
  
## Синтаксис  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса.  
  
 `ppv`  
 В случае успеха — указатель на интерфейс, определенный `riid`.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку, например, E\_NOINTERFACE.  
  
## Примечания  
 Это внутренняя вспомогательная функция, которая выполняет операцию QueryInterface.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура Implements](../Topic/Implements%20Structure.md)