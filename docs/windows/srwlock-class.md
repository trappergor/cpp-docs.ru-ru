---
title: "Класс SRWLock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLock - класс"
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс SRWLock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет тонкую блокировку чтения и записи.  
  
## Синтаксис  
  
```  
class SRWLock;  
```  
  
## Примечания  
 Тонкая блокировка чтения и записи используется для синхронизации доступа в потоках к объекту или ресурсу.  Дополнительные сведения см. в разделе [Синхронизация функций](http://msdn.microsoft.com/ru-ru/9b6359c2-0113-49b6-83d0-316ad95aba1b) в библиотеке MSDN.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|||  
|-|-|  
|**SyncLockExclusive**|Синоним для объекта SRWLock, получаемого в монопольном режиме.|  
|**SyncLockShared**|Синоним для объекта SRWLock, получаемого в совместном режиме.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор SRWLock::SRWLock](../windows/srwlock-srwlock-constructor.md)|Инициализирует новый экземпляр класса SRWLock.|  
|[Деструктор SRWLock::~SRWLock](../windows/srwlock-tilde-srwlock-destructor.md)|Деиницилизирует экземпляр класса SRWLock.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод SRWLock::LockExclusive](../windows/srwlock-lockexclusive-method.md)|Получает объект SRWLock в монопольном режиме.|  
|[Метод SRWLock::LockShared](../windows/srwlock-lockshared-method.md)|Получает объект SRWLock в совместном режиме.|  
|[Метод SRWLock::TryLockExclusive](../windows/srwlock-trylockexclusive-method.md)|Пытается получить объект SRWLock в монопольном режиме для текущего или указанного объекта SRWLock.|  
|[Метод SRWLock::TryLockShared](../windows/srwlock-trylockshared-method.md)|Пытается получить объект SRWLock в режиме общего доступа для текущего или указанного объекта SRWLock.|  
  
### Защищенный член данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных SRWLock::SRWLock\_](../windows/srwlock-srwlock-data-member.md)|Содержит базовую переменную блокировки для текущего объекта SRWLock.|  
  
## Иерархия наследования  
 `SRWLock`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)