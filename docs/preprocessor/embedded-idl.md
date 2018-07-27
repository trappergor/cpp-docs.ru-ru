---
title: embedded_idl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0b594952e8e5be0a9be9c843877c8c4bb95eca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842720"
---
# <a name="embeddedidl"></a>embedded_idl
**Конкретных C++**  
  
 Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
embedded_idl[("param")]  
```  
  
#### <a name="parameters"></a>Параметры  
 `param`  
 Допустимо одно из двух значений:  
  
-   emitidl: сведения о типах, импортированные из библиотеки типов, будут представлены в IDL-файле, созданном для помеченного атрибутом проекта.  Это значение по умолчанию, которое будет действовать, если параметр для `embedded_idl` не указан.  
  
-   no_emitidl: сведения о типах, импортированные из библиотеки типов, не будут представлены в IDL-файле, созданном для помеченного атрибутом проекта.  
  
## <a name="example"></a>Пример  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Примечания  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)