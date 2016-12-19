---
title: "Оператор Event::operator= | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= - оператор"
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор Event::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Присваивает указанную ссылку на событие текущему экземпляру Event.  
  
## Синтаксис  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### Параметры  
 `h`  
 Rvalue\-ссылка на экземпляр события.  
  
## Возвращаемое значение  
 Указатель на экземпляр текущего события.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс Event \(библиотека шаблонов C\+\+ среды выполнения Windows\)](../windows/event-class-windows-runtime-cpp-template-library.md)