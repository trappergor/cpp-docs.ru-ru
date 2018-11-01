---
title: Пространство имен Microsoft::WRL::Wrappers::HandleTraits
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: e558838ca9cd06fb5529f689d45a920db151d272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643252"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::HandleTraits

Описывает характеристики распространенных типов ресурсов на основе дескриптора.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Участники

### <a name="structures"></a>структурам;

|Имя|Описание|
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