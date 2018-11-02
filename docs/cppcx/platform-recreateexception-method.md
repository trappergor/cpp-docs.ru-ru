---
title: Метод Platform::RecreateException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 8173377a3d7a75bc85088037c229bac19f341649
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568874"
---
# <a name="platformrecreateexception-method"></a>Метод Platform::ReCreateException

Этот метод предназначен только для внутреннего использования и не предназначен для пользовательского кода. Используйте вместо него метод Exception::CreateException.

## <a name="syntax"></a>Синтаксис

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Параметры

*hr*

### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Возвращает новый Platform::Exception^, основываясь на указанном значении HRESULT.
