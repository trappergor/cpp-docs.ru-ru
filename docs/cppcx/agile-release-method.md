---
title: "Метод Agile::Release | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Release"
ms.assetid: aa825134-943f-425d-857e-449ec104765e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Agile::Release
Отменяет базовый объект и контекст текущего объекта Agile.  
  
## Синтаксис  
  
```cpp  
  
void Release() throw();  
  
```  
  
## Заметки  
 Выполняется отмена базового объекта и контекста текущего объекта Agile, если они существуют, а затем значению объекта Agile присваивается NULL.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)