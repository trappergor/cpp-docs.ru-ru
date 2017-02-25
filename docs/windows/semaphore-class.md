---
title: "Класс Semaphore | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Semaphore - класс"
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс Semaphore
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет объект синхронизации, который управляет общим ресурсом, который поддерживает ограниченное число пользователей.  
  
## Синтаксис  
  
```  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`SyncLock`|Синоним для класса, поддерживающего синхронные блокировки.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор Semaphore::Semaphore](../windows/semaphore-semaphore-constructor.md)|Инициализирует новый экземпляр класса Semaphore.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод InvokeHelper::Invoke](../windows/invokehelper-invoke-method.md)|Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Semaphore::Lock](../windows/semaphore-lock-method.md)|Ожидает, пока текущий объект или объект Semaphore, связанный с указанным дескриптором, не будет находиться в сигнальном состоянии или указанный интервал времени ожидания истечет.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор Semaphore::operator\=](../windows/semaphore-operator-assign-operator.md)|Перемещает указанный дескриптор из объекта Semaphore в текущий объект Semaphore.|  
  
## Иерархия наследования  
 `Semaphore`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)