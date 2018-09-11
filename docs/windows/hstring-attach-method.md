---
title: Метод HString::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
dev_langs:
- C++
ms.assetid: 69451979-0014-4959-bc5c-1e4ab6fb28e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7bdf5c17fc9364eb69d86f067bbb00cf40ebc5d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595320"
---
# <a name="hstringattach-method"></a>Метод HString::Attach

Связывает указанный **HString** объект с текущим **HString** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
void Attach(
       HSTRING hstr
       ) throw()  
```

### <a name="parameters"></a>Параметры

*HSTR*  
Существующий **HString** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)