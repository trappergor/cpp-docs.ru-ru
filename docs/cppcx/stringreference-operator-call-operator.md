---
title: "Оператор StringReference::operator() | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator()"
dev_langs: 
  - "C++"
ms.assetid: d5c65e82-300c-44aa-b826-0afe1e3645b1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор StringReference::operator()
Преобразует объект `StringReference` в объект `Platform::String^`.  
  
## Синтаксис  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
## Возвращаемое значение  
 Дескриптор для объекта типа `Platform::String`.  
  
## Заметки  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)