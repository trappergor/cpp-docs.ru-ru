---
title: Метод Platform::RecreateException | Документы Microsoft
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0472d74be21048aeaf25ca92dbb5c1e98ca0ca90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087833"
---
# <a name="platformrecreateexception-method"></a>Метод Platform::ReCreateException
Этот метод предназначен только для внутреннего использования и не предназначен для пользовательского кода. Используйте вместо этого метод Exception::CreateException.

## <a name="syntax"></a>Синтаксис

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Параметры
`hr`

### <a name="property-valuereturn-value"></a>Значение свойства или возвращаемое значение

Возвращает новый Platform::Exception^, основываясь на указанном значении HRESULT.

