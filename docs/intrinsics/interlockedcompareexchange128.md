---
title: _InterlockedCompareExchange128 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs:
- C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f491f59289a2e3b951e1bad60f260a801ea68bea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Блок, относящийся только к системам Microsoft**  
  
 Выполняет заблокированное сравнение 128-разрядным и exchange.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in, out] `Destination`  
 Указатель в место назначения, который является массивом из двух 64-разрядных целых чисел, считается 128-битовое поле. Данные назначения должен быть 16-байтовое выравнивание во избежание общие сбой защиты.  
  
 [in] `ExchangeHigh`  
 64-разрядное целое, могут быть заменены старшую часть назначения.  
  
 [in] `ExchangeLow`  
 64-разрядное целое, могут быть заменены младшую часть назначения.  
  
 [in, out] `ComparandResult`  
 Указатель на массив из двух 64-разрядных целых чисел (рассматривается как поле 128-разрядный) для сравнения с назначением.  На выходе оно перезаписывается исходное значение назначения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 1, если исходное значение назначения равно 128-разрядный сравниваемый операнд. `ExchangeHigh` и `ExchangeLow` перезаписать 128-разрядным конечным.  
  
 0, если сравниваемый операнд не равно исходное значение назначения. Значение назначения не меняется, и значение сравниваемый операнд перезаписывается значением назначения.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция приводит к возникновению ошибки `cmpxchg16b` инструкций (с `lock` префикс) для выполнения сравнения заблокированные 128-разрядный и exchange. AMD 64-разрядном оборудовании ранних версий не поддерживают эту инструкцию. Для проверки поддержки оборудования для `cmpxchg16b` инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x00000001 (standard function 1)`. Бит 13 `CPUInfo[2]` (ECX)-1, если инструкция поддерживается.  
  
> [!NOTE]
>  Значение `ComparandResult` всегда перезаписывается. После `lock` инструкции, эта встроенная функция немедленно копирует начальное значение `Destination` для `ComparandResult`. По этой причине `ComparandResult` и `Destination` должен указывать на отдельные ячейки памяти, чтобы избежать непредсказуемого поведения.  
  
 Несмотря на то, что можно использовать `_InterlockedCompareExchange128` для синхронизации потоков нижнего уровня, необязательно для синхронизации более чем 128 бит, если используется более мелкие функции синхронизации (например, другой `_InterlockedCompareExchange` встроенных функций) вместо. Используйте `_InterlockedCompareExchange128` atomic доступа для 128-разрядное значение в памяти.  
  
 При выполнении кода, использующего встроенную на оборудовании, которое не поддерживает `cmpxchg16b` инструкции, результаты будут непредсказуемыми.  
  
 Эта процедура доступна только как встроенная функция.  
  
## <a name="example"></a>Пример  
 В этом примере используется `_InterlockedCompareExchange128` для замены старшее слово массив из двух 64-разрядных целых чисел на сумму в его верхней и нижней слов и для увеличения младшее слово. Доступ к массиву BigInt.Int является атомарной, но в этом примере использует один поток и игнорирует блокировки для простоты.  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
```Output  
BigInt.Int[1] = 34, BigInt.Int[0] = 12  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Встроенные функции _InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)