---
title: no_dual_interfaces | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8923adb4cf2e92d72bf656064c6de8fc66e2a91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**Конкретных C++**  
  
 Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Примечания  
 Как правило, программа-оболочка вызывает метод через таблицу виртуальных функций интерфейса. С `no_dual_interfaces`, вместо этого вызывает оболочки **IDispatch::Invoke** вызова метода.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)