---
title: Метод Module::GetActivationFactory | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e87ea3b0e44732d4271385073c48fd92e1aa114
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608931"
---
# <a name="modulegetactivationfactory-method"></a>Метод Module::GetActivationFactory

Получает фабрику активации для модуля.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*pActivatibleClassId*  
Представляет IID класса среды выполнения.

*ppIFactory*  
Представляет интерфейс IActivationFactory указанного класса среды выполнения.

*Имя_сервера*  
Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос, или указать **nullptr** для получения имени сервера по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)  
[Макрос ActivatableClass](../windows/activatableclass-macros.md)