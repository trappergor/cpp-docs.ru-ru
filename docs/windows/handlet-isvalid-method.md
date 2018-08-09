---
title: Метод HandleT::IsValid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
dev_langs:
- C++
helpviewer_keywords:
- IsValid method
ms.assetid: 2c3e72fd-e67b-4908-9929-9007e1a4fc25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eba8dbe8ee0dad3f085104c914a731986d736e2b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647879"
---
# <a name="handletisvalid-method"></a>Метод HandleT::IsValid
Указывает, является ли текущий **HandleT** представляет дескриптор.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool IsValid() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если **HandleT** представляет дескриптор; в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)