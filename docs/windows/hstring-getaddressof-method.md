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
ms.openlocfilehash: 4ea49833107bf58443bf4a8238229d1d63a86742
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010351"
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