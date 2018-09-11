---
title: __ull_rshift | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c834b3b2284a7a5ae660870b840d3275c985dc9e
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539696"
---
# <a name="ullrshift"></a>__ull_rshift
**Блок, относящийся только к системам Microsoft**  
  
 Смещает 64-разрядное значение, определяемое первый параметр справа в x64, количество битов, указанное в качестве второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `mask`  
 64-разрядное целое значение для сдвига вправо.  
  
 [in] `nBit`  
 Количество битов для сдвига, остаток от деления 32 на x86 и остаток от деления 64 в x64.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Маска сдвинуты `nBit` bits.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__ull_rshift`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Если второй параметр больше, чем 31 x86 (63 в x64), это число берется остаток от деления 32 (64 в x64) для определения числа битов для сдвига. `ull` В имени указывает `unsigned long long (unsigned __int64)`.  
  
## <a name="example"></a>Пример  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
1  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)