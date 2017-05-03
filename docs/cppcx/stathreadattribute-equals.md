---
title: "STAThreadAttribute::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::STAThreadAttribute::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STAThreadAttribute::Equals"
ms.assetid: 8a63d242-6da9-4064-a091-fbfd792708f3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# STAThreadAttribute::Equals
Определяет, равен ли заданный объект текущему объекту.  
  
## Синтаксис  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
## Параметры  
 obj  
 Объект для сравнения.  
  
## Возвращаемое значение  
 Значение `true`, если объекты равны, в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::STAThreadAttribute](../cppcx/platform-stathreadattribute-class.md)