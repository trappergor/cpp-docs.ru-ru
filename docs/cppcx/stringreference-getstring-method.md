---
title: "Метод StringReference::GetString | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::GetString"
dev_langs: 
  - "C++"
ms.assetid: be3fe22e-783e-4abd-a363-113ededbe729
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод StringReference::GetString
Возвращает содержимое строки как `Platform::String^`.  
  
## Синтаксис  
  
```scr  
__declspec(no_release_return) __declspec(no_refcount)  
    ::Platform::String^ GetString() const  
```  
  
## Возвращаемое значение  
 Объект `Platform::String^`, который содержит строковые данные.  
  
## Заметки  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)