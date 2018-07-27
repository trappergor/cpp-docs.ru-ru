---
title: Метод HString::GetAddressOf | Документы Microsoft
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
ms.openlocfilehash: 7d4804373045d12c2e251e2de61b7aefd52ec916
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874672"
---
# <a name="hstringgetaddressof-method"></a>Метод HString::GetAddressOf
Извлекает указатель на базовый дескриптор HSTRING.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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