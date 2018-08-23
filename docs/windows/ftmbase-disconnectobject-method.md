---
title: Метод FtmBase::DisconnectObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs:
- C++
helpviewer_keywords:
- DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b467162d2f5cc5b04bc43a6d31019eb08e17e750
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595410"
---
# <a name="ftmbasedisconnectobject-method"></a>Метод FtmBase::DisconnectObject

Принудительно освобождает все внешние подключения к объекту. Сервер объекта вызывает реализацию объекта этот метод перед завершением работы системы.

## <a name="syntax"></a>Синтаксис

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Параметры

*dwReserved*  
Зарезервировано для будущего использования; должно иметь значение нуль.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="requirements"></a>Требования

**Заголовок:** ftm.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс FtmBase](../windows/ftmbase-class.md)