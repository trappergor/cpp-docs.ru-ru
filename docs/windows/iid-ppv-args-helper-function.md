---
title: Iid_ppv_args_helper-функция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a6131cea7a7684036fd7183a79214c7c6936540b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218752"
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

*T*  
Тип аргумента *pp*.

*PP*  
Двойной косвенный указатель.

## <a name="return-value"></a>Возвращаемое значение

Аргумент *pp* приведен указатель для указатель для **void**.

## <a name="remarks"></a>Примечания

Ошибка времени компиляции создается в том случае, если параметр шаблона *T* не является производным от `IUnknown`.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

## <a name="see-also"></a>См. также

[Справочник по (библиотека среды выполнения Windows)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)