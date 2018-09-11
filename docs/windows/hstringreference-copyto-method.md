---
title: Метод HStringReference::CopyTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0299f469f9cd2757c72e05a8717171ec32aa2c6c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198528"
---
# <a name="hstringreferencecopyto-method"></a>Метод HStringReference::CopyTo

Копирует текущий **HStringReference** объект в объект HSTRING.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*str*  
HSTRING, который получает копию.

## <a name="remarks"></a>Примечания

Этот метод вызывает метод [WindowsDuplicateString](https://msdn.microsoft.com/library/br224634.aspx) функции.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)