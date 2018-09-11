---
title: Класс семафора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0b3d5dff91bcb1fb1688c7b1a9314fe7ebf00c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598419"
---
# <a name="semaphore-class"></a>Semaphore - класс

Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.

## <a name="syntax"></a>Синтаксис

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`SyncLock`|Синоним для класса, поддерживающего синхронной блокировки.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор Semaphore::Semaphore](../windows/semaphore-semaphore-constructor.md)|Инициализирует новый экземпляр класса **семафора** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод InvokeHelper::Invoke](../windows/invokehelper-invoke-method.md)|Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[Метод Semaphore::Lock](../windows/semaphore-lock-method.md)|Ожидает, пока текущий объект или объект, связанный с указанным дескриптором, находится в сигнальном состоянии или истечет указанный интервал времени ожидания.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[Оператор Semaphore::operator=](../windows/semaphore-operator-assign-operator.md)|Перемещает указанный дескриптор из **семафора** объект с текущим **семафора** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Semaphore`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)