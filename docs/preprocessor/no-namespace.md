---
title: no_namespace | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d4558b0fd6a4014bc9601d5260882af444f87e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="nonamespace"></a>no_namespace
**Конкретных C++**  
  
 Указывает, что пространство имен не генерируется компилятором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Примечания  
 Содержимое библиотеки типов в файле заголовка `#import` обычно определяется в пространстве имен. Имя пространства имен, указанное в **библиотеки** оператором в исходном файле IDL. Если атрибут `no_namespace` определен, это пространство имен не генерируется компилятором.  
  
 Если вы хотите использовать различные пространства имен, используйте [rename_namespace](../preprocessor/rename-namespace.md) атрибутом.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)