---
title: Метод HString::GetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e327e2818903396c154be7406ec325695b6b6982
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613369"
---
# <a name="hstringgetaddressof-method"></a>Метод HString::GetAddressOf

Извлекает указатель на базовый дескриптор HSTRING.

## <a name="syntax"></a>Синтаксис

```cpp
HSTRING* GetAddressOf() throw()  
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на базовый дескриптор HSTRING.

## <a name="remarks"></a>Примечания

После этой операции строковое значение базового дескриптора HSTRING будет уничтожено.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)