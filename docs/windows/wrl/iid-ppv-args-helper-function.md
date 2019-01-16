---
title: IID_PPV_ARGS_Helper - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: cae29c70c551701a351cdcf404342ed1634a0e3b
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336472"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper - функция

Проверяет, что тип заданного аргумента является производным от интерфейса `IUnknown`.

> [!IMPORTANT]
> Данная специализация шаблона поддерживает инфраструктуру WRL и не предназначена для использования непосредственно из кода. Используйте [IID_PPV_ARGS](https://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) вместо этого.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип аргумента *pp*.

*PP*<br/>
Двойной косвенный указатель.

## <a name="return-value"></a>Возвращаемое значение

Аргумент *pp* приведен указатель для указатель для **void**.

## <a name="remarks"></a>Примечания

Ошибка времени компиляции создается в том случае, если параметр шаблона *T* не является производным от `IUnknown`.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

