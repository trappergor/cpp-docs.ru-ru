---
title: __lzcnt16 __lzcnt, __lzcnt64 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e04182cf673674e1f1ba8c073b624760bc4809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332797"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64
**Блок, относящийся только к системам Microsoft**  
  
 Счетчики число начальные нули в 16-, 32- или 64-разрядное целое число.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `value`  
 16-, 32- или 64-разрядное целое число без знака для проверки на наличие начальных нулей.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число начальных нулей в `value` параметра. Если `value` равен нулю, возвращается размер входного операнда (16, 32 или 64). Если наиболее значимый бит `value` равна 1, возвращаемое значение равно нулю.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__lzcnt16`|AMD: Дополнительно поразрядные (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt`|AMD: Дополнительно поразрядные (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt64`|AMD: Расширенная обработка бит (ABM) в 64-разрядном режиме.<br /><br /> Intel: Haswell|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Каждый из этих встроенных функций приводит к возникновению ошибки `lzcnt` инструкции.  Размер значения, `lzcnt` инструкция возвращает совпадает со значением размера аргумента.  В 32-разрядном режиме существует не 64-разрядных регистров общего назначения, поэтому не 64-разрядных `lzcnt`.  
  
 Чтобы определить аппаратную поддержку `lzcnt` вызов инструкции `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 5 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. При выполнении кода, использующего встроенную на оборудовании, которое не поддерживает `lzcnt` инструкции, результаты будут непредсказуемыми.  
  
 Для процессоров Intel®, которые не поддерживают `lzcnt` кодировку байтов инструкции выполнения инструкции, как `bsr` (бит обратного просмотра). Если важна переносимость кода, можно использовать `_BitScanReverse` встроенная функция вместо него. Дополнительные сведения см. в разделе [_BitScanReverse _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).  
  
## <a name="example"></a>Пример  
  
```  
// Compile this test with: /EHsc  
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
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__lzcnt16(0x0) = 16  
__lzcnt16(0xff) = 8  
__lzcnt16(0xffff) = 0  
__lzcnt(0x0) = 32  
__lzcnt(0xff) = 24  
__lzcnt(0xffff) = 16  
__lzcnt(0xffffffff) = 0  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Некоторые части этого содержимого, авторские права, 2007 Advanced Micro устройств, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
