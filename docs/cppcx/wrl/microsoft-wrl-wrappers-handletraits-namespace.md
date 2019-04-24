---
title: Пространство имен Microsoft::WRL::Wrappers::HandleTraits
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 6ed8156b6a0e71d40d1579fc9a33912f698e1773
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030398"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::HandleTraits

Описывает характеристики распространенных типов ресурсов на основе дескриптора.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Участники

### <a name="structures"></a>Структуры

|name|Описание|
|----------|-----------------|
|[Структура CriticalSectionTraits](criticalsectiontraits-structure.md)|Специализируется `CriticalSection` объекта для поддержки недопустимую критическую секцию или функцию для освобождения критического раздела.|
|[Структура EventTraits](eventtraits-structure.md)|Определяет характеристики `Event` дескриптора класса.|
|[Структура FileHandleTraits](filehandletraits-structure.md)|Определяет характеристики дескриптора файла.|
|[Структура HANDLENullTraits](handlenulltraits-structure.md)|Определяет общие характеристики дескриптора неинициализированным.|
|[Структура HANDLETraits](handletraits-structure.md)|Определяет общие характеристики дескриптора.|
|[Структура MutexTraits](mutextraits-structure.md)|Определяет общие характеристики [мьютекс](mutex-class.md) класса.|
|[Структура SemaphoreTraits](semaphoretraits-structure.md)|Определяет общие характеристики объекта семафора.|
|[Структура SRWLockExclusiveTraits](srwlockexclusivetraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режиме эксклюзивной блокировки.|
|[Структура SRWLockSharedTraits](srwlocksharedtraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)