---
title: Метод DeferrableEventArgs::GetDeferral | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 47376a055da1625f718b7b2a8b6dbf4fe703e533
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601809"
---
# <a name="deferrableeventargsgetdeferral-method"></a>Метод DeferrableEventArgs::GetDeferral

Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```

### <a name="parameters"></a>Параметры

*результат*  
Указатель, который будет ссылаться на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объекта после завершения вызова.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Пример кода см. в разделе [класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)