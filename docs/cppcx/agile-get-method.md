---
title: "Метод Agile::Get | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Get"
ms.assetid: d6295e21-ddbe-4302-9158-3498da4d9669
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Agile::Get
Возвращает дескриптор объекта, представленного текущим объектом Agile.  
  
## Синтаксис  
  
```cpp  
  
          T^ Get() const  
;  
```  
  
## Возвращаемое значение  
 Дескриптор объекта, представленного текущим объектом Agile.  
  
 Тип возвращаемого значения фактически является скрытым внутренним типом. Удобный способ сохранения возвращаемого значения — присвоить это значение переменной, объявленной с помощью ключевого слова вывода типа [auto](../Topic/auto%20\(C++\).md). Например, `auto x = myAgileTvariable->Get();`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)