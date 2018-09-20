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
ms.openlocfilehash: 2f0a9116e9abe07628d2b205bd5249d9354d6f88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413917"
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

*HSTR*<br/>
Существующий **HString** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)