---
title: Метод Platform::RecreateException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 9e167efc54352d125e849956a2da8d8e8cad4ed6
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693273"
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
