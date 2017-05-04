---
title: "Platform::CallbackContext - перечисление | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::CallbackContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::CallbackContext - перечисление"
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::CallbackContext - перечисление
Указывает контекст потока, в котором выполняется функция обратного вызова \(обработчик события\).  
  
## Синтаксис  
  
```cpp  
enum class CallbackContext {};  
```  
  
## Члены  
  
|Код типа|Описание|  
|--------------|--------------|  
|Любой|Функция обратного вызова может выполняться в любом контексте потока.|  
|То же|Функция обратного вызова может выполняться в контексте потока, запустившего асинхронную операцию.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd