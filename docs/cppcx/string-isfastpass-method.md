---
title: "Метод String::IsFastPass | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsFastPass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsFastPass"
ms.assetid: 0a8c2db7-e44f-45fe-9570-3dc82fbbacdd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::IsFastPass
Указывает, участвует ли текущий объект String в операции *быстрой передачи*. В операции быстрой передачи подсчет ссылок приостанавливается.  
  
## Синтаксис  
  
```cpp  
  
bool IsFastPass();  
```  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект String участвует в операции быстрой передачи; в противном случае — значение `false`.  
  
## Заметки  
 При вызове функции, где в качестве параметра используется объект с подсчетом ссылок и вызываемая функция обращается к этому объекту только для чтения, компилятор может безопасно приостановить подсчет ссылок, чтобы повысить производительность вызова. Это свойство не дает никакой дополнительной пользы для вашего кода. Система обрабатывает все сведения.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)