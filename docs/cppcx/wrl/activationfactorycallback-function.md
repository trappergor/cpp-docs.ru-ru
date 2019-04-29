---
title: ActivationFactoryCallback - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 4743e7724c5aba4171cb017654267afaac676f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303881"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback - функция

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>Параметры

*activationId*<br/>
Дескриптор строка, задающая имя класса среды выполнения.

*ppFactory*<br/>
После завершения операции фабрику активации, соответствующее параметру *activationId*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Скорее всего, ошибочные значения HRESULT: CLASS_E_CLASSNOTAVAILABLE и E_INVALIDARG.

## <a name="remarks"></a>Примечания

Возвращает фабрику активации для активации указанного идентификатора.

Среда выполнения Windows вызывает эту функцию обратного вызова для запроса объекта, заданный его именем класса среды выполнения.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)