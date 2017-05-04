---
title: "Метод String::Concat | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Concat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Concat"
ms.assetid: 68052d22-3df0-4777-828d-fc3a8e8a3ab7
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::Concat
Объединяет значения двух объектов String.  
  
## Синтаксис  
  
```cpp  
  
String^ Concat( String ^ str1,   
String ^ str2  
)  
  
```  
  
#### Параметры  
 `str1`  
 Первый объект String или значение `null`.  
  
 `str2`  
 Второй объект String или значение `null`.  
  
## Возвращаемое значение  
 Новый объект String^, значение которого является объединением значений `str1` и `str2`.  
  
 Если `str1` имеет значение `null`, а `str2` — значение, отличное от null, возвращается значение `str1` . Если `str2` имеет значение `null`, а `str1` — значение, отличное от null, возвращается значение `str2`. Если оба параметра `str1` и `str2` имеют значение `null`, возвращается пустая строка \(L""\).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)