---
title: ImplementsHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: 250a59152e9b41eb48c453caaa696fdc8ca3d3b4
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336456"
---
# <a name="implementshelper-structure"></a>ImplementsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Параметры

*RuntimeClassFlagsT*<br/>
Поле флагов, который указывает один или несколько [RuntimeClassType](runtimeclasstype-enumeration.md) перечислителей.

*ILst*<br/>
Список идентификаторов интерфейсов.

*IsDelegateToClass*<br/>
Укажите **true** Если текущий экземпляр `Implements` является базовым классом для идентификатор первого интерфейса в *ILst*; в противном случае **false**.

## <a name="remarks"></a>Примечания

Помогает реализовать [реализует](implements-structure.md) структуры.

Этот шаблон, проходит через список интерфейсов и добавляет их в качестве базовых классов, а также как сведения, необходимые для включения `QueryInterface`.

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                    | Описание:
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ImplementsHelper::CanCastTo](#cancastto)               | Возвращает указатель на идентификатор указанного интерфейса.
[ImplementsHelper::CastToUnknown](#casttounknown)       | Возвращает указатель на базовый `IUnknown` интерфейса для текущего `Implements` структуры.
[ImplementsHelper::FillArrayWithIid](#fillarraywithiid) | Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива.
[ImplementsHelper::IidCount](#iidcount)                 | Содержит число идентификаторов реализованного интерфейса в текущем `Implements` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ImplementsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="cancastto"></a>ImplementsHelper::CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса.

*ppv*<br/>
Если операция выполнена успешно, указатель на интерфейс, заданный *riid* или *iid*.

*IID*<br/>
Ссылка на идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Возвращает указатель на идентификатор указанного интерфейса.

## <a name="casttounknown"></a>ImplementsHelper::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый `IUnknown` интерфейс.

### <a name="remarks"></a>Примечания

Возвращает указатель на базовый `IUnknown` интерфейса для текущего `Implements` структуры.

## <a name="fillarraywithiid"></a>ImplementsHelper::FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Отсчитываемый от нуля индекс, указывающий начальный элемент массива для этой операции. По завершении этой операции *индекс* увеличивается на 1.

*идентификаторы IID*<br/>
Массив типа IID.

### <a name="remarks"></a>Примечания

Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива.

## <a name="iidcount"></a>ImplementsHelper::IidCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Примечания

Содержит число идентификаторов реализованного интерфейса в текущем `Implements` объекта.
