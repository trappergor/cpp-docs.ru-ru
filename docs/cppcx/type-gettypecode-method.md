---
title: "Type::GetTypeCode - метод | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::GetTypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::GetTypeCode - метод"
ms.assetid: 20c30432-91a3-400e-b9d6-eba265daaefc
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::GetTypeCode - метод
Возвращает числовой тип категории встроенных типов.  
  
## Синтаксис  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
## Возвращаемое значение  
 Одно из значений перечисления Platform::TypeCode.  
  
## Заметки  
 Эквивалентом метода\-члена GetTypeCode\(\) является свойство `typeid`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Platform::ValueType \- класс](../cppcx/platform-valuetype-class.md)