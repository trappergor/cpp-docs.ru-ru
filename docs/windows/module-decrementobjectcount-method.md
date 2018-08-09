---
title: Метод Module::DecrementObjectCount | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::DecrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- DecrementObjectCount method
ms.assetid: 6a06d1f9-7881-4f0e-891f-46b0e5c4f604
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 075c1ae368df59e735d90d8d98d9e8fd23ac8ad9
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017348"
---
# <a name="moduledecrementobjectcount-method"></a>Метод Module::DecrementObjectCount
Уменьшает число объектов, отслеживаемых модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
virtual long DecrementObjectCount();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число, прежде чем операция уменьшения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
## <a name="see-also"></a>См. также
[Класс Module](../windows/module-class.md)