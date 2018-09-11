---
title: Метод RuntimeClassBaseT::AsIID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b50466fc2c357c1d57fca272ff343cd56f3689c5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604270"
---
# <a name="runtimeclassbasetasiid-method"></a>Метод RuntimeClassBaseT::AsIID

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Параметры

*T*  
Тип, который реализует идентификатор интерфейса, заданный параметром *riid*.

*Реализует*  
Переменной типа, указанного параметром шаблона *T*.

*riid*  
Извлекаемый идентификатор интерфейса.

*ppvObject*  
При успешном выполнении эта операция указатель для указатель на интерфейс, указанного параметром *riid*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, описывающее ошибку.

## <a name="remarks"></a>Примечания

Извлекает указатель на идентификатор указанного интерфейса.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)