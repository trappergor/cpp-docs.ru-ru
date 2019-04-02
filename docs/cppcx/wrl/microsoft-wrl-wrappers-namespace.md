---
title: Пространство имен Microsoft::WRL::Wrappers
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 953318e09c4c0d00748f2b6189615dbd66677a96
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785090"
---
# <a name="microsoftwrlwrappers-namespace"></a>Пространство имен Microsoft::WRL::Wrappers

Определяет оболочки типа "Получение ресурса есть инициализация" (RAII), которые упрощают управление временем существования объектов, строк и дескрипторов.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|name|Описание|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[Класс CriticalSection](criticalsection-class.md)|Представляет объект критической секции.|
|[Класс Event (WRL)](event-class-wrl.md)|Представляет событие.|
|[Класс HandleT](handlet-class.md)|Представляет дескриптор объекта.|
|[Класс HString](hstring-class.md)|Обеспечивает поддержку манипулирования дескрипторами HSTRING.|
|[Класс HStringReference](hstringreference-class.md)|Представляет HSTRING, созданный из существующей строки.|
|[Класс Mutex](mutex-class.md)|Представляет объект синхронизации, который исключительно управляет общим ресурсом.|
|[Класс RoInitializeWrapper](roinitializewrapper-class.md)|Инициализирует среду выполнения Windows.|
|[Класс Semaphore](semaphore-class.md)|Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.|
|[Класс SRWLock](srwlock-class.md)|Представляет тонкую блокировку чтения и записи.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)