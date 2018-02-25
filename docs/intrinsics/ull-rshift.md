---
title: "__ull_rshift | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0193bad5b9184e3168c618b9bc4e3afc5e27abc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ullrshift"></a>__ull_rshift
**Блок, относящийся только к системам Microsoft**  
  
 на x64 сдвигается на 64-разрядное значение, указан первым параметром вправо на количество битов, указанное в качестве второго параметра.  
  
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
 Число разрядов для поворота остаток от деления 32 на x86 и остаток от деления 64 на x64.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Маска сдвинуто `nBit` bits.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Если второй параметр больше 31 на номер берется по модулю 32 (64 на x64) для определения количества разрядов для поворота x86 (63 на x64). `ull` В названии указывает `unsigned long long (unsigned __int64)`.  
  
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