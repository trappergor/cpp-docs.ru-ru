---
title: embedded_idl | Документация Майкрософт
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
ms.openlocfilehash: 9ad4a58cf02522eb7ca1c00055c73ff921e92b11
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386123"
---
# <a name="embeddedidl"></a>embedded_idl
**Конкретных C++**  
  
Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
embedded_idl[("param")]  
```  
  
### <a name="parameters"></a>Параметры  
*param*  
Допустимо одно из двух значений:  
  
- emitidl: сведения о типах, импортированные из библиотеки типов, будут представлены в IDL-файле, созданном для помеченного атрибутом проекта.  Это значение по умолчанию, которое будет действовать, если параметр для `embedded_idl` не указан.  
  
- no_emitidl: сведения о типах, импортированные из библиотеки типов, не будут представлены в IDL-файле, созданном для помеченного атрибутом проекта.  
  
## <a name="example"></a>Пример  
  
```cpp  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## <a name="remarks"></a>Примечания  
 
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)