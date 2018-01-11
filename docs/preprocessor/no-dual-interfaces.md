---
title: "no_dual_interfaces | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_dual_interfaces
dev_langs: C++
helpviewer_keywords: no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42501c329b5c040f762b692e9298b184a2035d7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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