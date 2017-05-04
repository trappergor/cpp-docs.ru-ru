---
title: "Класс Platform::OutOfBoundsException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::OutOfBoundsException"
  - "Platform/Platform::OutOfBoundsException::OutOfBoundsException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::OutOfBoundsException"
ms.assetid: 96f8bf75-1207-4049-964b-7771822cadf3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Класс Platform::OutOfBoundsException
Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.  
  
## Синтаксис  
  
```cpp  
public ref class OutOfBoundsException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Примечания  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)