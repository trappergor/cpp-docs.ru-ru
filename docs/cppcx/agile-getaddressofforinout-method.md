---
title: "Метод Agile::GetAddressOfForInOut | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOfForInOut"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOfForInOut"
ms.assetid: 8bb27b4c-c325-49ee-91db-9adf87c530c4
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Agile::GetAddressOfForInOut
Возвращает адрес дескриптора объекта, представленного текущим объектом Agile.  
  
## Синтаксис  
  
```cpp  
  
       T^* GetAddressOfForInOut()   
throw();  
  
```  
  
#### Параметры  
 `T`  
 Тип, указанный в параметре имени типа шаблона.  
  
## Возвращаемое значение  
 Адрес дескриптора объекта, представленного текущим объектом Agile.  
  
## Заметки  
 Эта операция получает текущий контекст потоков, затем возвращает адрес дескриптора основного объекта.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)