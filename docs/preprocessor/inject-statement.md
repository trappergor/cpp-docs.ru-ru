---
title: "inject_statement | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: inject_statement
dev_langs: C++
helpviewer_keywords: inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d1ac68cae628f09c9511c4b86eac75da8dff6ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="injectstatement"></a>inject_statement
**Конкретных C++**  
  
 Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>Параметры  
 `source_text`  
 Исходный текст, вставляемый в файл заголовка библиотеки типов.  
  
## <a name="remarks"></a>Примечания  
 Текст вставляется в начало объявления пространства имен, в которое помещается содержимое библиотеки типов в файле заголовка.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)