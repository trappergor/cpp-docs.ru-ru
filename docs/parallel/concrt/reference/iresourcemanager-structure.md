---
title: "Структура IResourceManager | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IResourceManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IResourceManager - структура"
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Структура IResourceManager
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс к диспетчеру ресурсов среды параллелизма.  Это интерфейс, по которому планировщики взаимодействовать с диспетчер ресурсов.  
  
## Синтаксис  
  
```  
struct IResourceManager;  
```  
  
## Члены  
  
### Открытые перечисления  
  
|Имя|Описание|  
|---------|--------------|  
|[Перечисление IResourceManager::OSVersion](../Topic/IResourceManager::OSVersion%20Enumeration.md)|Перечислимый тип, представляющий версию операционной системы.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод IResourceManager::CreateNodeTopology](../Topic/IResourceManager::CreateNodeTopology%20Method.md)|Присутствует только в отладочных построениях среды выполнения, этот метод — теста ловушка, разработанный для упрощения тестирования диспетчера ресурсов на различных топологиях оборудования, без необходимости фактического соответствия конфигурации оборудования.  С розничными построениями среды выполнения этот метод будет выполнять возврат, не выполняя никаких действий.|  
|[Метод IResourceManager::GetAvailableNodeCount](../Topic/IResourceManager::GetAvailableNodeCount%20Method.md)|Возвращает количество узлов, доступных для диспетчера ресурсов.|  
|[Метод IResourceManager::GetFirstNode](../Topic/IResourceManager::GetFirstNode%20Method.md)|Возвращает первый узел в порядке перечисления, определенного диспетчером ресурсов.|  
|[Метод IResourceManager::Reference](../Topic/IResourceManager::Reference%20Method.md)|Увеличивает значение счетчика ссылок на экземпляр диспетчера ресурсов.|  
|[Метод IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md)|Регистрирует планировщик на диспетчере ресурсов.  После регистрации планировщик должен обмениваться данными с диспетчером ресурсов, с помощью возвращаемого интерфейса `ISchedulerProxy`.|  
|[Метод IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md)|Уменьшает значение счетчика ссылок на экземпляр диспетчера ресурсов.  Диспетчер ресурсов уничтожается, когда значение его счетчика переходит к `0`.|  
  
## Заметки  
 Используйте функцию [CreateResourceManager](../Topic/CreateResourceManager%20Function.md) для получения интерфейса на экземпляр одноэлементного диспетчера ресурсов.  Метод увеличивает значение счетчика ссылок на диспетчере ресурсов и необходимо вызвать метод [IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md), чтобы освободить ссылку, когда работа с диспетчером ресурсов закончена.  Обычно каждый создаваемый планировщик при создании будет вызывать этот метод и освобождать ссылку для диспетчера ресурсов после завершения работы.  
  
## Иерархия наследования  
 `IResourceManager`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура ISchedulerProxy](../../../parallel/concrt/reference/ischedulerproxy-structure.md)   
 [Структура IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)