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
ms.openlocfilehash: 28ec7e7840d3fd3a23e7b65fe6c46ce9cbc244c3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017582"
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
 Этот метод вызывает метод [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)