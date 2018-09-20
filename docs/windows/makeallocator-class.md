---
title: Makeallocator-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 460e2cdef4d0ba4252ceb8a4b7fe6defc25c183a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375378"
---
# <a name="makeallocator-class"></a>MakeAllocator - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<
   typename T,
   bool hasWeakReferenceSupport =
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа.

*hasWeakReferenceSupport*<br/>
**значение true,** выделить память для объекта, который поддерживает слабых ссылок; **false** выделить память для объекта, который не поддерживает слабые ссылки.

## <a name="remarks"></a>Примечания

Выделяет память для активируемого класса, с или без поддержку слабых ссылок.

Переопределить **MakeAllocator** класс для реализации модели выделения памяти, определяемые пользователем.

**MakeAllocator** обычно используется для предотвращения утечек памяти в том случае, если объект вызывает исключение во время построения.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор MakeAllocator::MakeAllocator](../windows/makeallocator-makeallocator-constructor.md)|Инициализирует новый экземпляр класса **MakeAllocator** класса.|
|[Деструктор MakeAllocator::~MakeAllocator](../windows/makeallocator-tilde-makeallocator-destructor.md)|Деинициализирует текущий экземпляр **MakeAllocator** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод MakeAllocator::Allocate](../windows/makeallocator-allocate-method.md)|Выделяет память и связывает его с текущим **MakeAllocator** объекта.|
|[Метод MakeAllocator::Detach](../windows/makeallocator-detach-method.md)|Отменяет связь памяти, выделенной с помощью [выделения](../windows/makeallocator-allocate-method.md) метод из текущего **MakeAllocator** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MakeAllocator`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)