---
title: "Класс Platform::ChangedStateException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ChangedStateException"
  - "Platform/Platform::ChangedStateException::ChangedStateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ChangedStateException"
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::ChangedStateException
Создается, если внутреннее состояние объекта было изменено, тем самым делая недействительными результаты метода.  
  
## Синтаксис  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Примечания  
 Один из примеров ситуаций, когда создается это исключение: метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.  
  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)