---
title: __popcnt16 __popcnt, __popcnt64 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs:
- C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a639091bd7c5c263a3f09067858cd0fe4ac631cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329200"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64
**Блок, относящийся только к системам Microsoft**  
  
 Подсчитывает количество один бит (счетчик заполнения) в 16-, 32- или 64-битового целого числа без знака.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `value`  
 16-, 32- или 64-разрядных целое число без знака, для которой нужно счетчик заполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Количество один бит в `value` параметра.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__popcnt16`|Дополнительно поразрядные|  
|`__popcnt`|Дополнительно поразрядные|  
|`__popcnt64`|Дополнительно поразрядные в 64-разрядном режиме.|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Каждый из этих встроенных функций приводит к возникновению ошибки `popcnt` инструкции.  Размер значения, `popcnt` инструкция возвращает совпадает со значением размера аргумента.  В 32-разрядном режиме существует не 64-разрядных регистров общего назначения, поэтому не 64-разрядных `popcnt`.  
  
 Чтобы определить аппаратную поддержку `popcnt` инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x00000001` и проверьте бит 23 `CPUInfo[2] (ECX)`. Этот бит — 1, если инструкция поддерживается и 0 в противном случае. При выполнении кода, использующего встроенную на оборудовании, которое не поддерживает `popcnt` инструкции, результаты будут непредсказуемыми.  
  
## <a name="example"></a>Пример  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__popcnt16(0x0) = 0  
__popcnt16(0xff) = 8  
__popcnt16(0xffff) = 16  
__popcnt(0x0) = 0  
__popcnt(0xff) = 8  
__popcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
