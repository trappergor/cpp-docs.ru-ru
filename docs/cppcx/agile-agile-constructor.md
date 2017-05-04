---
title: "Конструктор Agile::Agile | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Agile"
ms.assetid: 33c1df82-f5db-4750-98cc-0daa03be4e59
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор Agile::Agile
Инициализирует новый экземпляр класса Agile.  
  
## Синтаксис  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### Параметры  
 `T`  
 Тип, указанный в параметре имени типа шаблона.  
  
 `object`  
 Во второй версии данного конструктора: объект, используемый для инициализации нового экземпляра класса Agile. В третьей версии: объект, который копируется в новый экземпляр класса Agile. В четвертой версии: объект, который перемещается в новый экземпляр класса Agile.  
  
## Заметки  
 Первая версия этого конструктора является конструктором по умолчанию. Вторая версия инициализирует новый экземпляра класса Agile из объекта, указанного параметром `object`. Третья версия является конструктором копирования. Четвертая версия является конструктором перемещения. Этот конструктор не может вызывать исключения.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)