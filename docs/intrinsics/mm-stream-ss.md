---
title: _mm_stream_ss | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_ss
dev_langs:
- C++
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5058ac6c415f155b6a7cab712002d4769983d1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339492"
---
# <a name="mmstreamss"></a>_mm_stream_ss  
  
**Блок, относящийся только к системам Microsoft**  
  
 Записывает 32-разрядный адрес в памяти не избавляют кэши.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
 [выходной] `Dest`  
 Указатель на расположение, куда будут записываться в источнике данных.  
  
 [in] `Source`  
 128-разрядное число, которое содержит `float` значение для записи в его нижней 32 бита...  
  
## <a name="return-value"></a>Возвращаемое значение  
  
 Нет.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
  
Эта встроенная функция приводит к возникновению ошибки `movntss` инструкции. Чтобы определить поддержку оборудования для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит равен 1, если инструкция поддерживается и 0 в противном случае.  
  
При выполнении кода, использующего `_mm_stream_ss` на оборудовании, которое не поддерживает встроенные `movntss` инструкции, результаты будут непредсказуемыми.  
  
## <a name="example"></a>Пример  
  
```cpp  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
```  
  
```Output  
f[0] = -1, f[1] = -2  
f[2] = -3, f[3] = 3  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  

Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [_mm_stream_sd](../intrinsics/mm-stream-sd.md)   
 [_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)   
 [_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)