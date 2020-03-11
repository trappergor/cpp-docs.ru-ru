---
title: ComPtrRefBase - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865825"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase - класс

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Параметры

*T*<br/>
[ComPtr\<t >](comptr-class.md) тип или производный от него тип, а не просто интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Remarks

Представляет базовый класс для класса [ComPtrRef](comptrref-class.md) .

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя            | Description
--------------- | -------------------------------------------------
`InterfaceType` | Синоним для типа параметра-шаблона *T*.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                       | Description
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[Оператор comptrrefbase:: operator IInspectable * *](#operator-iinspectable-star-star) | Преобразует текущий элемент данных [ptr_](#ptr) в указатель на `IInspectable` интерфейсе.
[Оператор comptrrefbase:: operator IUnknown * *](#operator-iunknown-star-star)         | Преобразует текущий элемент данных [ptr_](#ptr) в указатель на `IUnknown` интерфейсе.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Description
--------------------------- | ----------------------------------------------------------------
[Оператор comptrrefbase::p tr_](#ptr) | Указатель на тип, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="operator-iinspectable-star-star"></a>Оператор оператор comptrrefbase:: operator IInspectable\*\*

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Remarks

Преобразует текущий элемент данных [ptr_](#ptr) в указатель на `IInspectable` интерфейсе.

Если текущий `ComPtrRefBase` не является производным от `IInspectable`, генерируется ошибка.

Это приведение доступно, только если определено `__WRL_CLASSIC_COM__`.

## <a name="operator-iunknown-star-star"></a>Оператор оператор comptrrefbase:: operator IUnknown * *

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Remarks

Преобразует текущий элемент данных [ptr_](#ptr) в указатель на `IUnknown` интерфейсе.

Если текущий `ComPtrRefBase` не является производным от `IUnknown`, генерируется ошибка.

## <a name="ptr"></a>Оператор comptrrefbase::p tr_

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Remarks

Указатель на тип, заданный текущим параметром шаблона. `ptr_` является защищенным элементом данных.
