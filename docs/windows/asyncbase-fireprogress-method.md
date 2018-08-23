---
title: Метод AsyncBase::FireProgress | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91cf005e3dc1d088a5c7d0e664f67610fac28843
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606253"
---
# <a name="asyncbasefireprogress-method"></a>Метод AsyncBase::FireProgress

Вызывает текущий обработчик событий процесса выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Параметры

*arg*  
Метод обработчика событий для запуска.

## <a name="remarks"></a>Примечания

`ProgressTraits` является производным от [argtraitshelper-структура](../windows/argtraitshelper-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс AsyncBase](../windows/asyncbase-class.md)