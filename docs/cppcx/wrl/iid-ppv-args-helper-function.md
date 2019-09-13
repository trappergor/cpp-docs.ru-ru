---
title: IID_PPV_ARGS_Helper - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: e7733ae6084b64c20dff5a2c35d7a31c614d6e44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500508"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper - функция

Проверяет, что тип заданного аргумента является производным от интерфейса `IUnknown`.

> [!IMPORTANT]
> Данная специализация шаблона поддерживает инфраструктуру WRL и не предназначена для использования непосредственно из кода. Вместо этого используйте [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) .

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип аргумента *PP*.

*PP*<br/>
Двойной косвенный указатель.

## <a name="return-value"></a>Возвращаемое значение

Аргумент *PP* приведение указателя к указателю на тип **void**.

## <a name="remarks"></a>Примечания

Если параметр шаблона *T* не является производным от `IUnknown`, создается ошибка времени компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

