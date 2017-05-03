---
title: "Метод String::IsEmpty | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsEmpty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsEmpty"
ms.assetid: 4b651706-eace-4055-a694-d9e26a03ce05
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::IsEmpty
Указывает, является ли объект String пустым.  
  
## Синтаксис  
  
```cpp  
  
bool IsEmpty()  
```  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект String имеет значение `null` или является пустой строкой \(L""\); в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)