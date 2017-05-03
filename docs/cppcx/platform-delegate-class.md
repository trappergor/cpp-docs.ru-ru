---
title: "Platform::Delegate - класс | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Delegate - класс"
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Delegate - класс
Представляет объект функции.  
  
## Синтаксис  
  
```cpp  
public delegate void delegate_name();  
```  
  
## Участники  
 Класс Delegate имеет методы Equals\(\), GetHashCode\(\) и ToString\(\), производные от [Класс Platform::Object](../cppcx/platform-object-class.md).  
  
## Заметки  
 Для создания делегатов используйте ключевое слово [delegate](~/windows/delegate-cpp-component-extensions.md); не используйте Platform::Delegate явным образом. Для получения дополнительной информации см. [Делегаты](../cppcx/delegates-c-cx.md). Пример создания и использования делегата см. в разделе [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)