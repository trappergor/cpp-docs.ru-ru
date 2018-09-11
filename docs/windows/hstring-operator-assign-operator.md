---
title: Оператор HString::Operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9294650db7a1b18c2542603988952a80b3f1905d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598549"
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator=

Перемещает значение другого **HString** объект с текущим **HString** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>Параметры

*other*  
Существующий **HString** объекта.

## <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий **HString** объекта, а затем *других* уничтожении объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)