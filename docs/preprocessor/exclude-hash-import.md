---
title: "исключить (#import) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exclude
dev_langs: C++
helpviewer_keywords: exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f28a4ce5e06687c279d80bc482895c9394726841
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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