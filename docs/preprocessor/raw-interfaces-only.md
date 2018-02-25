---
title: "raw_interfaces_only | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eff60ded57ae66b43dee4b3b95699ad498fa0358
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**Конкретных C++**  
  
 Подавляет создание функции-оболочки обработки ошибок и [свойство](../cpp/property-cpp.md) объявления, использующие эти функции-оболочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>Примечания  
 Атрибут `raw_interfaces_only` также вызывает удаление префикса по умолчанию, используемого для именования функций, отличных от свойств. Как правило, используется префикс **raw_**. Если этот атрибут задан, имена функций берутся непосредственно из библиотеки типов.  
  
 Этот атрибут позволяет предоставлять только низкоуровневое содержимое библиотеки типов.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)