---
title: "Пространство имен Microsoft::WRL::Wrappers::HandleTraits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleTraits - пространство имен"
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Пространство имен Microsoft::WRL::Wrappers::HandleTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает характеристики распространенных типов ресурсов на основе дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="structures"></a>структурам;  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)|Специализирует `CriticalSection` объекта для поддержки недопустимую критическую секцию или функция для освобождения критического раздела.|  
|[Структура EventTraits](../windows/eventtraits-structure.md)|Определяет характеристики `Event` дескриптора класса.|  
|[Структура FileHandleTraits](../windows/filehandletraits-structure.md)|Определяет характеристики дескриптора файла.|  
|[Структура HANDLENullTraits](../windows/handlenulltraits-structure.md)|Определяет общие характеристики неинициализированного дескриптора.|  
|[Структура HANDLETraits](../windows/handletraits-structure.md)|Определяет общие характеристики дескриптора.|  
|[Структура MutexTraits](../windows/mutextraits-structure.md)|Определяет общие характеристики [мьютекс](Mutex%20Class1.md) класса.|  
|[Структура SemaphoreTraits](../Topic/SemaphoreTraits%20Structure.md)|Определяет общие характеристики объекта семафора.|  
|[Структура SRWLockExclusiveTraits](../windows/srwlockexclusivetraits-structure.md)|Описывает общие характеристики `SRWLock` класс в монопольном режиме блокировки.|  
|[Структура SRWLockSharedTraits](../windows/srwlocksharedtraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режиме общего доступа блокировки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)