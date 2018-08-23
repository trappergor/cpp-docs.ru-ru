---
title: 'Пространство имен Microsoft::wrl:: wrappers | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
dev_langs:
- C++
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51964bb2d4cb13394f9efb0e36d572cf9309637d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605671"
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

|Имя|Описание:|
|----------|-----------------|
|[Класс CriticalSection](../windows/criticalsection-class.md)|Представляет объект критической секции.|
|[Класс Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)|Представляет событие.|
|[Класс HandleT](../windows/handlet-class.md)|Представляет дескриптор объекта.|
|[Класс HString](../windows/hstring-class.md)|Обеспечивает поддержку манипулирования дескрипторами HSTRING.|
|[Класс HStringReference](../windows/hstringreference-class.md)|Представляет HSTRING, созданный из существующей строки.|
|[Класс Mutex](../windows/mutex-class1.md)|Представляет объект синхронизации, который исключительно управляет общим ресурсом.|
|[Класс RoInitializeWrapper](../windows/roinitializewrapper-class.md)|Инициализирует среду выполнения Windows.|
|[Класс Semaphore](../windows/semaphore-class.md)|Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.|
|[Класс SRWLock](../windows/srwlock-class.md)|Представляет тонкую блокировку чтения и записи.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)