---
title: Метод HString::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
dev_langs:
- C++
ms.assetid: 5006ee13-549d-40a8-8dfe-d3fb3b5e18b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 21bfc0516fdcdf3287c5ce2a0203038e88cd290f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015563"
---
# <a name="hstringdetach-method"></a>Метод HString::Detach
Отменяет связывание заданных **HString** объект с его базовым значением.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HSTRING Detach() throw()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Базовый **HString** значение до запуска операции отсоединения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)