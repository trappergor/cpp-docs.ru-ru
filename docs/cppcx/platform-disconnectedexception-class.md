---
title: "Класс Platform::DisconnectedException | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::DisconnectedException"
  - "Platform/Platform::DisconnectedException::DisconnectedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::DisconnectedException"
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::DisconnectedException
Вызывается, если прокси\-объект COM пытается выполнить ссылку на сервер COM, которые больше не существует  
  
## Синтаксис  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## Заметки  
 Если класс A ссылается на другой класс \(класс B\) в отдельном процессе, то классу A требуется прокси\-объект для связи с находящимся вне процесса сервером COM, который содержит класс B. Иногда серверу может не хватать памяти, а класс A об этом не знает. В этом случае вызывается исключение RPC\_E\_DISCONNECTED и преобразуется в исключение Platform::DisconnectedException. Один из сценариев, в котором это происходит, связан с ситуацией, когда источник события вызывает предоставленного ему делегата, но делегат был удален в некоторой точке после своей подписки на событие. Когда это происходит, источник события удаляет делегата из своего списка вызова.  
  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)