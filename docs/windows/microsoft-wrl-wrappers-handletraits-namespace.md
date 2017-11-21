---
title: "Пространство имен Microsoft::WRL::Wrappers::HandleTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs: C++
helpviewer_keywords: HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3369f7b9264c7b0fd0bfbb9f137278a9f53848d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::HandleTraits
Описывает характеристики распространенных типов ресурсов на основе дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="structures"></a>структурам;  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)|Специализирует `CriticalSection` объектов для поддержки недопустимую критическую секцию или функцию освобождения критической секции.|  
|[Структура EventTraits](../windows/eventtraits-structure.md)|Определяет характеристики `Event` дескриптора класса.|  
|[Структура FileHandleTraits](../windows/filehandletraits-structure.md)|Определяет характеристики дескриптора файла.|  
|[Структура HANDLENullTraits](../windows/handlenulltraits-structure.md)|Определяет общие характеристики дескриптора неинициализированным.|  
|[Структура HANDLETraits](../windows/handletraits-structure.md)|Определяет общие характеристики дескриптора.|  
|[Структура MutexTraits](../windows/mutextraits-structure.md)|Определяет общие характеристики [мьютекс](../windows/mutex-class1.md) класса.|  
|[Структура SemaphoreTraits](../windows/semaphoretraits-structure.md)|Определяет общие характеристики объекта семафора.|  
|[Структура SRWLockExclusiveTraits](../windows/srwlockexclusivetraits-structure.md)|Описывает общие характеристики `SRWLock` класса в режиме эксклюзивной блокировки.|  
|[Структура SRWLockSharedTraits](../windows/srwlocksharedtraits-structure.md)|Описывает общие характеристики `SRWLock` класса в режим разделяемой блокировки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)