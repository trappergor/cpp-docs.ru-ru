---
title: Пространство имен Microsoft::WRL::Wrappers::HandleTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c83b921aabeee34b583c8f771190ecf60edccb59
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015815"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::HandleTraits
Описывает характеристики распространенных типов ресурсов на основе дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="structures"></a>структурам;  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)|Специализируется `CriticalSection` объекта для поддержки недопустимую критическую секцию или функцию для освобождения критического раздела.|  
|[Структура EventTraits](../windows/eventtraits-structure.md)|Определяет характеристики `Event` дескриптора класса.|  
|[Структура FileHandleTraits](../windows/filehandletraits-structure.md)|Определяет характеристики дескриптора файла.|  
|[Структура HANDLENullTraits](../windows/handlenulltraits-structure.md)|Определяет общие характеристики дескриптора неинициализированным.|  
|[Структура HANDLETraits](../windows/handletraits-structure.md)|Определяет общие характеристики дескриптора.|  
|[Структура MutexTraits](../windows/mutextraits-structure.md)|Определяет общие характеристики [мьютекс](../windows/mutex-class1.md) класса.|  
|[Структура SemaphoreTraits](../windows/semaphoretraits-structure.md)|Определяет общие характеристики объекта семафора.|  
|[Структура SRWLockExclusiveTraits](../windows/srwlockexclusivetraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режиме эксклюзивной блокировки.|  
|[Структура SRWLockSharedTraits](../windows/srwlocksharedtraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)