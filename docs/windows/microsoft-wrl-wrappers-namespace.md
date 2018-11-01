---
title: Пространство имен Microsoft::WRL::Wrappers
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: eac85d10351a141ce561da4272d033644128608f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535490"
---
# <a name="microsoftwrlwrappers-namespace"></a>Пространство имен Microsoft::WRL::Wrappers

Определяет оболочки типа "Получение ресурса есть инициализация" (RAII), которые упрощают управление временем существования объектов, строк и дескрипторов.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс CriticalSection](../windows/criticalsection-class.md)|Представляет объект критической секции.|
|[Класс Event (WRL)](../windows/event-class-wrl.md)|Представляет событие.|
|[Класс HandleT](../windows/handlet-class.md)|Представляет дескриптор объекта.|
|[Класс HString](../windows/hstring-class.md)|Обеспечивает поддержку манипулирования дескрипторами HSTRING.|
|[Класс HStringReference](../windows/hstringreference-class.md)|Представляет HSTRING, созданный из существующей строки.|
|[Класс Mutex](../windows/mutex-class.md)|Представляет объект синхронизации, который исключительно управляет общим ресурсом.|
|[Класс RoInitializeWrapper](../windows/roinitializewrapper-class.md)|Инициализирует среду выполнения Windows.|
|[Класс Semaphore](../windows/semaphore-class.md)|Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.|
|[Класс SRWLock](../windows/srwlock-class.md)|Представляет тонкую блокировку чтения и записи.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)