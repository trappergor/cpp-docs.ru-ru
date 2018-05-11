---
title: исключить (#import) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cbc9d6f5ae0dcb1f82264ff07d3ea93a71cab60
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="exclude-import"></a>exclude (#import)
**Конкретных C++**  
  
 Исключает элементы из создаваемых файлов заголовка библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### <a name="parameters"></a>Параметры  
 `Name1`  
 Первый исключаемый элемент.  
  
 `Name2`  
 Второй исключаемый элемент (при необходимости).  
  
## <a name="remarks"></a>Примечания  
 Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Этот атрибут может принимать любое количество аргументов, каждый из которых является именем исключаемого элемента, находящегося на верхнем уровне библиотеки типов.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)