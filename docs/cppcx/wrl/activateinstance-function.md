---
title: ActivateInstance - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: d1109e769352d412df8348822e05b66063159ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214231"
---
# <a name="activateinstance-function"></a>ActivateInstance - функция

Регистрирует и извлекает экземпляр указанного типа, определенного в указанном ИДЕНТИФИКАТОРе класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип для активации.

*Запись*<br/>
Имя идентификатора класса, определяющего параметр *T*.

*instance*<br/>
По завершении этой операции ссылка на экземпляр *T*.

## <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае возвращается ошибка HRESULT, указывающая причину ошибки.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Windows:: Foundation

## <a name="see-also"></a>См. также раздел

[Пространство имен Windows::Foundation](windows-foundation-namespace.md)
