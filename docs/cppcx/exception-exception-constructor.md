---
title: "Exception::Exception - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Exception - конструктор"
ms.assetid: 173b434e-e3a8-41f5-904e-0e8fc0f21950
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Exception - конструктор
Инициализирует новый экземпляр класса Exception.  
  
## Синтаксис  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
#### Параметры  
 `hresult`  
 HRESULT ошибки, представляемый этим исключением.  
  
 `message`  
 Задаваемое пользователем сообщение \(например, текст рекомендаций\), связанное с исключением. В общем случае следует выбирать вторую перегрузку, чтобы предоставить максимально подробное описание того, как и почему произошла конкретная ошибка.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)