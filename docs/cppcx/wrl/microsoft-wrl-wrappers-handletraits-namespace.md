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
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
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
|[CriticalSectionTraits - структура](criticalsectiontraits-structure.md)|Специализируется `CriticalSection` объекта для поддержки недопустимую критическую секцию или функцию для освобождения критического раздела.|
|[EventTraits - структура](eventtraits-structure.md)|Определяет характеристики `Event` дескриптора класса.|
|[FileHandleTraits - структура](filehandletraits-structure.md)|Определяет характеристики дескриптора файла.|
|[HANDLENullTraits - структура](handlenulltraits-structure.md)|Определяет общие характеристики дескриптора неинициализированным.|
|[HANDLETraits - структура](handletraits-structure.md)|Определяет общие характеристики дескриптора.|
|[MutexTraits - структура](mutextraits-structure.md)|Определяет общие характеристики [мьютекс](mutex-class.md) класса.|
|[SemaphoreTraits - структура](semaphoretraits-structure.md)|Определяет общие характеристики объекта семафора.|
|[SRWLockExclusiveTraits - структура](srwlockexclusivetraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режиме эксклюзивной блокировки.|
|[SRWLockSharedTraits - структура](srwlocksharedtraits-structure.md)|Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)