---
title: Метод ActivationFactory::GetTrustLevel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bfec8bfa6940fd4a702334f0d3068c6d936ea8c1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607318"
---
# <a name="activationfactorygettrustlevel-method"></a>Метод ActivationFactory::GetTrustLevel

Получает уровень доверия объект, текущий **ActivationFactory** создает экземпляр.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Параметры

*trustLvl*  
После завершения этой операции, уровень доверия среды выполнения класс, который **ActivationFactory** создает экземпляр.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае выдается ошибка утверждения и *trustLvl* присваивается `FullTrust`.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ActivationFactory](../windows/activationfactory-class.md)