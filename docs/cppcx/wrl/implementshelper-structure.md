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
ms.openlocfilehash: e33842f574df5617fb40c5b3f6bb8324d5ba7c1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371398"
---
# <a name="implementshelper-structure"></a>ImplementsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Параметры

*RuntimeClassFlagsT*<br/>
Поле флагов, которое определяет один или несколько регистраторов [RuntimeClassType.](runtimeclasstype-enumeration.md)

*ILst*<br/>
Список идов интерфейса.

*IsDelegatetoClass*<br/>
Укажите **истинно,** `Implements` если текущий экземпляр является базовым классом первого идентификатора интерфейса в *ILst;* в противном случае, **ложные**.

## <a name="remarks"></a>Remarks

Помогает реализовать структуру [реализации.](implements-structure.md)

Этот шаблон пересекает список интерфейсов и добавляет их в качестве `QueryInterface`базовых классов, а также как информацию, необходимую для включения.

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                    | Описание
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[РеализуетХандер::CanCastTo](#cancastto)               | Получает указатель на указанный идентификатор интерфейса.
[РеализуетХандер::CastToUnknown](#casttounknown)       | Получает указатель на базовый `IUnknown` интерфейс `Implements` для текущей структуры.
[РеализуетХандер::FillArrayWithIid](#fillarraywithiid) | Вставляет идентификатор интерфейса, указанный текущим параметром шаблона нулевой, в указанный элемент массива.
[РеализуетХандер::IidCount](#iidcount)                 | Сохраняет количество иных идонов `Implements` интерфейса в текущем объекте.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ImplementsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>РеализуетХандер::CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

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

*Ppv*<br/>
Если эта операция успешна, указатель на интерфейс, указанный *riid* или *iid.*

*Iid*<br/>
Ссылка на идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Remarks

Получает указатель на указанный идентификатор интерфейса.

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>РеализуетХандер::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый `IUnknown` интерфейс.

### <a name="remarks"></a>Remarks

Получает указатель на базовый `IUnknown` интерфейс `Implements` для текущей структуры.

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>РеализуетХандер::FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Индекс с нулевым уровнем, указывающий элемент стартового массива для этой операции. Когда эта операция завершается, *индекс* приравнизирован на 1.

*iids*<br/>
Массив типовых IID.

### <a name="remarks"></a>Remarks

Вставляет идентификатор интерфейса, указанный текущим параметром шаблона нулевой, в указанный элемент массива.

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>РеализуетХандер::IidCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Remarks

Сохраняет количество иных идонов `Implements` интерфейса в текущем объекте.
