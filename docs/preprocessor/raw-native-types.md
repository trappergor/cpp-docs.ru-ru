---
title: raw_native_types | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5baa3204b14da53f6a6a3232874e0ac7de0fd91b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849799"
---
# <a name="rawnativetypes"></a>raw_native_types
**Конкретных C++**  
  
 Отключает использование классов поддержки COM в высокоуровневых функциях оболочки и принудительно использует вместо них низкоуровневые типы данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию высокоуровневые методы обработки ошибок используют классы поддержки COM [_bstr_t](../cpp/bstr-t-class.md) и [_variant_t](../cpp/variant-t-class.md) вместо `BSTR` и **VARIANT** типов данных и необработанные указатели для COM-интерфейса. Эти классы инкапсулируют сведения выделения и отмены выделения хранилища памяти для этих типов данных и значительно упрощают операции приведения и преобразования типов.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)