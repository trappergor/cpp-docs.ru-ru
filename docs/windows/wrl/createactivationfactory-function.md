---
title: CreateActivationFactory - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 07bc0dceb8066faf9c1beab64d48245d8735aa64
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336835"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory - функция

Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Сочетание одного или нескольких [RuntimeClassType](runtimeclasstype-enumeration.md) значений перечисления.

*entry*<br/>
Указатель на [CreatorMap](creatormap-structure.md) , содержащий инициализации и регистрации сведений о параметрах *riid*.

*riid*<br/>
Ссылка на идентификатор интерфейса.

*ppFactory*<br/>
Если эта операция завершается успешно, указатель на фабрику активации.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Ошибка assert создается в том случае, если параметр шаблона *фабрики* не является производным от интерфейса `IActivationFactory`.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::Details](microsoft-wrl-wrappers-details-namespace.md)