---
title: "IntPtr::IntPtr - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::IntPtr - конструктор"
ms.assetid: 828b4c18-790d-4fb4-90fe-47769ff381c0
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::IntPtr - конструктор
Инициализирует новый экземпляр класса IntPtr, используя указанное значение.  
  
## Синтаксис  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
#### Параметры  
 value  
 64\-разрядный дескриптор или указатель, указатель на 64\-разрядное значение или 32\-разрядное значение, которое можно преобразовать в 64\-разрядное.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс значения Platform::IntPtr](../cppcx/platform-intptr-value-class.md)