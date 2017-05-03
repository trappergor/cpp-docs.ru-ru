---
title: "Оператор Agile::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator="
ms.assetid: 2c413bef-f103-4911-afb3-0dac5f6a760e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Agile::operator=
Присваивает указанный объект текущему объекту Agile.  
  
## Синтаксис  
  
```cpp  
  
   Agile<T> operator=(  
   T^ object  
) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### Параметры  
 `T`  
 Тип, указанный в имени типа шаблона.  
  
 `object`  
 Объект или дескриптор объекта, который копируется или перемещается в текущий объект Agile.  
  
 `lp`  
 Указатель интерфейса IUnknown объекта.  
  
## Возвращаемое значение  
 Дескриптор для объекта типа `T`  
  
## Заметки  
 Первая версия оператора присваивания копирует дескриптор ссылочного типа в текущий объект Agile. Вторая версия копирует ссылку на тип Agile в текущий объект Agile. Третья версия перемещает тип Agile в текущий объект Agile. Четвертая версия перемещает указатель на COM\-объект в текущий объект Agile.  
  
 Операция присваивания автоматически сохраняет контекст текущего объекта Agile.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Agile](../cppcx/platform-agile-class.md)