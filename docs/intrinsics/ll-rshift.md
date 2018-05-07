---
title: __ll_rshift | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e086339c41f789323cb4aab386a96dae27a0eeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="llrshift"></a>__ll_rshift
**Блок, относящийся только к системам Microsoft**  
  
 Сдвигает 64-разрядное значение, указан первым параметром вправо на количество битов, указанное в качестве второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Mask`  
 64-разрядное целое значение для сдвига вправо.  
  
 [in] `nBit`  
 Число разрядов для поворота по модулю 64 на x64 и остаток от деления 32 на x86.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Маска сдвинуто `nBit` bits.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Если второй параметр больше 64 на номер берется по модулю 64 (32 на x86) для определения количества разрядов для поворота x64 (32 на x86). `ll` Префикс указывает, что эта операция выполняется на `long long`, другое имя для `__int64`, 64-разрядных целочисленный тип данных со знаком.  
  
## <a name="example"></a>Пример  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **Примечание** Если `_ull_rshift` уже используется, MSB сдвиг вправо значения были бы нулю, поэтому требуемый результат не получается в случае отрицательного значения.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)