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
ms.openlocfilehash: 157512ee556126291427c3db6578788a477505a6
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016383"
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