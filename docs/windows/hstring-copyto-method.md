---
title: Метод HString::CopyTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da0e8e241aeb3f0eb5096d64cd63425ca2102fb0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211175"
---
# <a name="hstringcopyto-method"></a>Метод HString::CopyTo

Копирует текущий **HString** объект в объект HSTRING.

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

[Класс HString](../windows/hstring-class.md)