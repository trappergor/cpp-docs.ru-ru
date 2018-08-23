---
title: Метод ComPtr::AsIID | Документация Майкрософт
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d79707eaa3e5e93ab5c05e120d1556ee86168af2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607302"
---
# <a name="comptrasiid-method"></a>Метод ComPtr::AsIID

Возвращает **ComPtr** , представляющий интерфейс, определенный с помощью идентификатора указанного интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Параметры

*riid*  
Идентификатор интерфейса.

*p*  
Если объект имеет интерфейс, идентификатор которой равняется *riid*, двойной косвенный указатель на интерфейс, определенный следующим *riid* параметра; в противном случае указатель на `IUnknown`.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)