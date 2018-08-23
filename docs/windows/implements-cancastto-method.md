---
title: Метод Implements::CanCastTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 328691877a3b129c852460f8f68cdd3db4974e6f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595303"
---
# <a name="implementscancastto-method"></a>Метод Implements::CanCastTo

Возвращает указатель на указанный интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*  
Ссылку на идентификатор интерфейса.

*ppv*  
Если в случае успешного выполнения указатель на интерфейс, заданный *riid*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, указывающее ошибку, например E_NOINTERFACE.

## <a name="remarks"></a>Примечания

Это внутренняя вспомогательная функция, которая выполняет операцию QueryInterface.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Структура Implements](../windows/implements-structure.md)