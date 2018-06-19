---
title: inject_statement | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 115f5b3d7012ae3e9073d81e0c1005dcb513e045
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849344"
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