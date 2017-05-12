---
title: "Класс Platform::ArrayReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ArrayReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Platform::ArrayReference"
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::ArrayReference
`ArrayReference` — тип оптимизации, который можно заменить на [Platform::Array^](../cppcx/platform-array-class.md) во входных параметрах, если требуется заполнить входными данными массив в стиле языка C.  
  
## Синтаксис  
  
```vb  
  
```  
  
```csharp  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор ArrayReference::ArrayReference](../cppcx/arrayreference-arrayreference-constructor.md)|Инициализирует новый экземпляр класса `ArrayReference`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор ArrayReference::operator\(\)](../cppcx/arrayreference-operator-call-operator.md)|Преобразует этот объект `ArrayReference` в `Platform::Array<T>^*`.|  
|[Оператор ArrayReference::operator\=](../cppcx/arrayreference-operator-assign-operator.md)|Назначает содержимое другой ссылки `ArrayReference` этому экземпляру.|  
  
## Исключения  
  
## Заметки  
 Использование `ArrayReference` для заполнения массива в стиле языка C позволяет избежать дополнительной операции копирования, которая потребовалось бы при копировании сначала в переменную `Platform::Array`, а затем в массив в стиле языка C. При использовании `ArrayReference` выполняется только одна операция копирования. Пример кода см. в разделе [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## Заголовок подраздела  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)