---
title: Метод ActivationFactory::GetIids | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49ef07365675ddb9cdedee1f6a2cdfb676188dc6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42576713"
---
# <a name="activationfactorygetiids-method"></a>Метод ActivationFactory::GetIids

Извлекает массив идентификаторов реализованного интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Параметры

*iidCount*  
После завершения операции, число идентификаторов интерфейса в *идентификаторы IID* массива.

*идентификаторы IID*  
После завершения операции представляет массив идентификаторов реализованного интерфейса.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. E_OUTOFMEMORY является возможной ошибкой HRESULT.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ActivationFactory](../windows/activationfactory-class.md)