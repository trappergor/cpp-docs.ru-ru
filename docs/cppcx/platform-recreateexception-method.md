---
title: "Метод Platform::ReCreateException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ReCreateException"
dev_langs: 
  - "C++"
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод Platform::ReCreateException
Этот метод предназначен только для внутреннего использования и не предназначен для пользовательского кода. Вместо него используйте [метод Exception::CreateException](../cppcx/exception-createexception-method.md).  
  
## Синтаксис  
  
```vb  
static Exception^ ReCreateException(int hr)  
```  
  
#### Параметры  
  
## Значение свойства, возвращаемое значение  
 Возвращает новый Platform::Exception^, основываясь на указанном значении HRESULT.  
  
## Эквивалент в .NET Framework  
  
## Требования