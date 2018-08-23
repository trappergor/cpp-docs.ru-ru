---
title: Мьютекс Class1 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b20c270f7848a346d717357f474d89e37ea117a4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600032"
---
# <a name="mutex-class1"></a>Мьютекс Class1

Представляет объект синхронизации, который исключительно управляет общим ресурсом.

## <a name="syntax"></a>Синтаксис

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`SyncLock`|Синоним для класса, поддерживающего синхронной блокировки.|

### <a name="public-constructor"></a>Открытый конструктор

|name|Описание:|
|----------|-----------------|
|[Конструктор Mutex::Mutex](../windows/mutex-mutex-constructor.md)|Инициализирует новый экземпляр класса **мьютекс** класса.|

### <a name="public-members"></a>Открытые члены

|name|Описание:|
|----------|-----------------|
|[Метод Mutex::Lock](../windows/mutex-lock-method.md)|Только после текущего объекта, или **мьютекс** объект, связанный с указанным дескриптором, выпуски, мьютексом или указанный интервал времени ожидания истечет.|

### <a name="public-operator"></a>Открытый оператор

|name|Описание:|
|----------|-----------------|
|[Оператор Mutex::operator=](../windows/mutex-operator-assign-operator.md)|Назначает (перемещается) указанного **мьютекс** объект с текущим **мьютекс** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Mutex`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)