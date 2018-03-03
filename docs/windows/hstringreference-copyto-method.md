---
title: "Метод HStringReference::CopyTo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5fb6ac1f645207c048e88078c7fcdc8297f8d1b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferencecopyto-method"></a>Метод HStringReference::CopyTo
Копирует текущий HStringReference объект к объекту HSTRING.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 HSTRING, который получает копию.  
  
## <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)