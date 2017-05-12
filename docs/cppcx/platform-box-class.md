---
title: "Класс Platform::Box | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box"
dev_langs: 
  - "C++"
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс Platform::Box
Позволяет сохранять тип значения, такой как `Windows::Foundation::DateTime`, или скалярный тип, такой как `int`, в типе `Platform::Object`. Как правило, нет необходимости использовать `Box` явным образом, так как процесс упаковки выполняется неявно при приведении значения типа к `Object^`.  
  
## Синтаксис  
  
```cpp  
ref class Box abstract;  
```  
  
## Заметки  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Упаковка](../cppcx/boxing-c-cx.md)