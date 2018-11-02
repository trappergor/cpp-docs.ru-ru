---
title: Класс bad_function_call
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 6d0a3f5f5b6ac48d23b937b04b4521799ba31502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523829"
---
# <a name="badfunctioncall-class"></a>Класс bad_function_call

Сообщает о недопустимом вызове функции.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>Примечания

Данный класс описывает создание исключения для указания, что вызывается `operator()` в [классе function](../standard-library/function-class.md).
