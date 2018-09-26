---
title: Структура RuntimeClassBaseT | Документация Майкрософт
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9e7f5b38d3434e8753646db4733218978e7e766
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169714"
---
# <a name="runtimeclassbaset-structure"></a>Структура RuntimeClassBaseT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   unsigned int RuntimeClassTypeT
>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Параметры

*RuntimeClassTypeT*<br/>
Поле флагов, который указывает один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.

## <a name="remarks"></a>Примечания

Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                         | Описание
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT::AsIID](#asiid)                           | Извлекает указатель на идентификатор указанного интерфейса.
[RuntimeClassBaseT::GetImplementedIIDS](#getimplementediids) | Извлекает массив идентификаторов, которые реализуются с помощью указанного типа интерфейсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassBaseT`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="asiid"></a>RuntimeClassBaseT::AsIID

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип, который реализует идентификатор интерфейса, заданный параметром *riid*.

*Реализует*<br/>
Переменной типа, указанного параметром шаблона *T*.

*riid*<br/>
Извлекаемый идентификатор интерфейса.

*ppvObject*<br/>
При успешном выполнении эта операция указатель для указатель на интерфейс, указанного параметром *riid*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, описывающее ошибку.

### <a name="remarks"></a>Примечания

Извлекает указатель на идентификатор указанного интерфейса.

## <a name="getimplementediids"></a>RuntimeClassBaseT::GetImplementedIIDS

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип *реализует* параметра.

*Реализует*<br/>
Указатель на тип, указанный параметром *T*.

*iidCount*<br/>
Максимальное число идентификаторов интерфейса для извлечения.

*идентификаторы IID*<br/>
Если эта операция завершается успешно, массив идентификаторов, реализуемый типом интерфейсов *T*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, описывающее ошибку.

### <a name="remarks"></a>Примечания

Извлекает массив идентификаторов, которые реализуются с помощью указанного типа интерфейсов.
