---
title: Метод ActivationFactory::GetRuntimeClassName | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
dev_langs:
- C++
helpviewer_keywords:
- GetRuntimeClassName method
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbae13c6ce70533b8338d47893b6007a3032abab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416309"
---
# <a name="activationfactorygetruntimeclassname-method"></a>Метод ActivationFactory::GetRuntimeClassName

Получает имя класса среды выполнения объекта, который текущего **ActivationFactory** создает экземпляр.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Параметры

*runtimeName*<br/>
После завершения операции, дескриптор строка, содержащая имя класса среды выполнения объекта, текущий **ActivationFactory** создает экземпляр.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ActivationFactory](../windows/activationfactory-class.md)