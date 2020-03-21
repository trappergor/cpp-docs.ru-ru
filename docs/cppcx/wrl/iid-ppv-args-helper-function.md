---
title: IID_PPV_ARGS_Helper - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 68dbd0b5b2e9d4fc04821a7e7e0193840b55e312
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077132"
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

Если параметр шаблона *T* не является производным от `IUnknown`, возникает ошибка времени компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** client.h
