---
title: CreateClassFactory - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: e7e213d1b0679f17ce070de85ee9410ff9546716
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785340"
---
# <a name="createclassfactory-function"></a>CreateClassFactory - функция

Создает фабрику, которая создает экземпляры указанного класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Factory>
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(
   _In_ unsigned int *flags,
   _In_ const CreatorMap* entry,
   REFIID riid,
   _Outptr_ IUnknown **ppFactory
) throw();
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Сочетание одного или нескольких [RuntimeClassType](runtimeclasstype-enumeration.md) значений перечисления.

*entry*<br/>
Указатель на [CreatorMap](creatormap-structure.md) , содержащий инициализации и регистрации сведений о параметрах *riid*.

*riid*<br/>
Ссылка на идентификатор интерфейса.

*ppFactory*<br/>
Если эта операция завершается успешно, указатель на фабрику класса.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Ошибка assert создается в том случае, если параметр шаблона *фабрики* не является производным от интерфейса `IClassFactory`.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::Details](microsoft-wrl-wrappers-details-namespace.md)