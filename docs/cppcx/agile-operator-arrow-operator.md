---
title: "Оператор Agile::operator-&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator->"
ms.assetid: 570f4b0b-1735-49b3-8a30-4a302ac57074
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Agile::operator-&gt;
Извлекает дескриптор объекта, представленного текущим объектом Agile.  
  
## Синтаксис  
  
```cpp  
  
       T^ operator->()   
const throw();  
```  
  
## Возвращаемое значение  
 Дескриптор объекта, представленного текущим объектом Agile.  
  
 Этот оператор фактически возвращает скрытый внутренний тип. Удобный способ сохранения возвращаемого значения — присвоить это значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](../Topic/auto%20\(C++\).md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)