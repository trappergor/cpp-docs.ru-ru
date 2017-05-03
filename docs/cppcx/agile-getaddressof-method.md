---
title: "Метод Agile::GetAddressOf | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOf"
ms.assetid: f015edf9-4155-4992-a6fc-7ff1edcc5d1e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Agile::GetAddressOf
Повторно инициализирует текущий объект Agile и возвращает адрес дескриптора для объекта типа `T`.  
  
## Синтаксис  
  
```cpp  
  
       T^* GetAddressOf()   
throw();  
```  
  
#### Параметры  
 `T`  
 Тип, указанный в параметре имени типа шаблона.  
  
## Возвращаемое значение  
 Адрес дескриптора для объекта типа `T`.  
  
## Заметки  
 Эта операция освобождает текущее представление объекта типа `T` при его наличии, повторно инициализирует данные\-члены объекта Agile, получает текущий контекст потока, а затем возвращает адрес переменной дескриптора для объекта, который может представлять объект, отличный от Agile. Чтобы экземпляр класса Agile представлял объект, используйте оператор присваивания \([Agile::operator \=](../cppcx/agile-operator-assign-operator.md)\) для назначения объекта экземпляру класса Agile.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)