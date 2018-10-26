---
title: Класс scoped_d3d_access_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0bb3442de264e263ae0f0eabd93345eace1fde1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059614"
---
# <a name="scopedd3daccesslock-class"></a>Класс scoped_d3d_access_lock

Программа-оболочка RAII для блокирования доступа D3D объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```
class scoped_d3d_access_lock;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор scoped_d3d_access_lock](#ctor)|Перегружен. Создает объект `scoped_d3d_access_lock`. Блокировка снимается, когда этот объект выходит из области.|
|[~ Деструктор scoped_d3d_access_lock](#dtor)|Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Принимает владельца блокировки из другого `scoped_d3d_access_lock`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scoped_d3d_access_lock`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** concurrency::direct3d

##  <a name="ctor"></a> scoped_d3d_access_lock

Создает объект `scoped_d3d_access_lock`. Блокировка снимается, когда этот объект выходит из области.

```
explicit scoped_d3d_access_lock(// [1] constructor
    accelerator_view& _Av);

explicit scoped_d3d_access_lock(// [2] constructor
    accelerator_view& _Av,
    adopt_d3d_access_lock_t _T);

scoped_d3d_access_lock(// [3] move constructor
    scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
`accelerator_view` Блокировки внедрить.

*_T*<br/>
Объект `adopt_d3d_access_lock_t`.

*_Другое*<br/>
`scoped_d3d_access_lock` Объект, из которого нужно переместить существующую блокировку.

## <a name="construction"></a>Создание экземпляра

[1] конструктор получает блокировку доступа D3D для заданного [accelerator_view](accelerator-view-class.md) объекта. Создание блокируется до получения блокировки.

[2] конструктор применять блокировку доступа D3D от заданного [accelerator_view](accelerator-view-class.md) объекта.

[3] перемещение конструктор принимает существующую блокировку доступа D3D из другого `scoped_d3d_access_lock` объекта. Создание не блокируется.

##  <a name="dtor"></a> ~ scoped_d3d_access_lock

Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.

```
~scoped_d3d_access_lock();
```

## <a name="operator_eq"></a> оператор =

Принимает владельца блокировки доступа D3D из другого `scoped_d3d_access_lock` объекта, освобождая предыдущую блокировку.

```
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
Accelerator_view, из которого нужно переместить блокировку доступа D3D.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `scoped_accelerator_view_lock`.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)
