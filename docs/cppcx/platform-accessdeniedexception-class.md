---
title: "Класс Platform::AccessDeniedException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::AccessDeniedException"
  - "Platform/Platform::AccessDeniedException::AccessDeniedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::AccessDeniedException"
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс Platform::AccessDeniedException
Возникает при запрете доступа к ресурсу или функции.  
  
## Синтаксис  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
## Примечания  
 Если возникло это исключение, проверьте, что вы запросили соответствующую возможность и указали необходимые объявления в манифесте пакета приложения. Дополнительные сведения см. в статье [Настройка пакета приложения Windows 8.1 с помощью конструктора манифестов](../Topic/Configure%20a%20Windows%208.1%20app%20package%20by%20using%20the%20manifest%20designer.md) и в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)