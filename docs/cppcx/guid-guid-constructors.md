---
title: "Конструкторы Guid::Guid | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Guid::Guid"
  - "Guid::Guid"
ms.assetid: dfa4dcad-1c3b-481f-9f60-05141b9788d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструкторы Guid::Guid
Инициализирует новый экземпляр структуры Guid.  
  
## Синтаксис  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  
);  
  
    Guid(   
        GUID m  
);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n  
);  
```  
  
#### Параметры  
 `a`  
 Первые 4 байта GUID.  
  
 `b`  
 Следующие 2 байта GUID.  
  
 `c`  
 Следующие 2 байта GUID.  
  
 `d`  
 Следующий байт GUID.  
  
 `e`  
 Следующий байт GUID.  
  
 `f`  
 Следующий байт GUID.  
  
 `g`  
 Следующий байт GUID.  
  
 `h`  
 Следующий байт GUID.  
  
 `i`  
 Следующий байт GUID.  
  
 `j`  
 Следующий байт GUID.  
  
 `k`  
 Следующий байт GUID.  
  
 `m`  
 GUID согласно определению.  
  
 `n`  
 Оставшиеся 8 байтов GUID.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс значения Platform::Guid](../cppcx/platform-guid-value-class.md)