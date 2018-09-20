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
ms.openlocfilehash: 8e528bed14f3f6f3b35270975833bdd17fd777db
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422653"
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator=

Перемещает значение другого **HString** объект с текущим **HString** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>Параметры

*other*<br/>
Существующий **HString** объекта.

## <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий **HString** объекта, а затем *других* уничтожении объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)