---
title: Структура pointer_traits
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: 6d89348867982bfb86c0bf2404a017f6a448d1a1
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687142"
---
# <a name="pointer_traits-struct"></a>Структура pointer_traits

Предоставляет сведения, необходимые объекту типа `allocator_traits` для описания распределителя с типом указателя `Ptr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>Заметки

Ptr может быть необработанным указателем типа `Ty *` или классом со следующими свойствами.

```cpp
struct Ptr
{ // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj); // optional
};
```

## <a name="members"></a>Члены

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|`typedef T2 difference_type`|Тип `T2` — `Ptr::difference_type`, если этот тип существует, в противном случае — `ptrdiff_t`. Если `Ptr` является необработанным указателем, то тип — `ptrdiff_t`.|
|`typedef T1 element_type`|Тип `T1` — `Ptr::element_type`, если этот тип существует, в противном случае — `Ty`. Если `Ptr` является необработанным указателем, то тип — `Ty`.|
|`typedef Ptr pointer`|Тип — `Ptr`.|

### <a name="structs"></a>структурам;

|||
|-|-|
|`rebind`|Пытается преобразовать базовый указатель в указанный тип.|

### <a name="methods"></a>Методы

|Название|Описание|
|----------|-----------------|
|[pointer_to](#pointer_to)|Преобразует произвольную ссылку в объект класса `Ptr`.|

### <a name="pointer_to"></a>pointer_to

Статический метод, возвращающий `Ptr::pointer_to(obj)`, если эта функция существует. В противном случае невозможно преобразовать произвольную ссылку на объект класса `Ptr`. Если `Ptr` является необработанной ссылкой, этот метод возвращает `addressof(obj)`.

```cpp
static pointer pointer_to(element_type& obj);
```
