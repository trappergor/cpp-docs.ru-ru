---
title: Метод SimpleActivationFactory::GetTrustLevel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b5a1838c153dc7a0a4def9f98e5e043e36ae9414
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603849"
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>Метод SimpleActivationFactory::GetTrustLevel

Получает уровень доверия выполняемого экземпляра класса, указанного параметром `Base` параметре шаблона класса.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Параметры

*trustLvl*  
После завершения операции, уровень доверия текущего объекта класса.

## <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)