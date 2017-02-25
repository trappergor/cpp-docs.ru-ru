---
title: "Класс MakeAllocator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MakeAllocator - класс"
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс MakeAllocator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,   
   T)> , T)> class MakeAllocator;  
  
template<  
   typename T  
>  
class MakeAllocator<T, false>;  
  
template<  
   typename T  
>  
class MakeAllocator<T, true>;  
```  
  
#### Параметры  
 `T`  
 Имя типа.  
  
 `hasWeakReferenceSupport`  
 `true` для выделения памяти для объекта, который поддерживает слабые ссылки; `false` для выделения памяти для объекта, который не поддерживает слабые ссылки.  
  
## Примечания  
 Выделяет память для активируемого класса с поддержкой или без поддержки слабой ссылки.  
  
 Переопределите класс MakeAllocator для реализации определяемой пользователем модели выделения памяти.  
  
 MakeAllocator обычно используется для предотвращения утечки памяти, если объект бросается во время построения.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор MakeAllocator::MakeAllocator](../windows/makeallocator-makeallocator-constructor.md)|Инициализирует новый экземпляр класса RoleService MakeAllocator.|  
|[Деструктор MakeAllocator::~MakeAllocator](../Topic/MakeAllocator::~MakeAllocator%20Destructor.md)|Уничтожает текущий экземпляр класса MakeAllocator.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод MakeAllocator::Allocate](../Topic/MakeAllocator::Allocate%20Method.md)|Выделяет память и связывает ее с текущим объектом MakeAllocator.|  
|[Метод MakeAllocator::Detach](../windows/makeallocator-detach-method.md)|Диассоциирует память, выделенную методом [Allocate](../Topic/MakeAllocator::Allocate%20Method.md) из текущего объекта MakeAllocator.|  
  
## Иерархия наследования  
 `MakeAllocator`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)