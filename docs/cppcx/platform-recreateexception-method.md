---
title: Метод Platform::RecreateException | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc789ce0eb723410e5c62505183d5d3449d95c5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601203"
---
# <a name="platformrecreateexception-method"></a>Метод Platform::ReCreateException
Этот метод предназначен только для внутреннего использования и не предназначен для пользовательского кода. Используйте вместо него метод Exception::CreateException.

## <a name="syntax"></a>Синтаксис

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Параметры
`hr`

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Возвращает новый Platform::Exception^, основываясь на указанном значении HRESULT.

