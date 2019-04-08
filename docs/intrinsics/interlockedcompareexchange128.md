---
title: _InterlockedCompareExchange128
ms.date: 11/04/2016
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
ms.openlocfilehash: 9330b1405ca247364cd04d3ab399f66e4f332273
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037874"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128

**Блок, относящийся только к системам Microsoft**

Выполняет заблокированное сравнение 128-разрядный и exchange.

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

*Назначение*<br/>
[in, out] Указатель на целевой объект, который представляет собой массив из двух 64-разрядных целых чисел, считается как 128-битовое поле. Целевых данных должен быть 16-байтовое выравнивание во избежание общие сбой защиты.

*ExchangeHigh*<br/>
[in] 64-разрядное целое число, могут быть заменены верхняя часть назначения.

*ExchangeLow*<br/>
[in] 64-разрядное целое число, могут быть заменены младшей части назначения.

*ComparandResult*<br/>
[in, out] Указатель на массив из двух 64-разрядных целых чисел (рассматривается как 128-битовое поле) для сравнения с назначением.  На выводе это будет перезаписано в исходное значение массива назначения.

## <a name="return-value"></a>Возвращаемое значение

1, если сравниваемый операнд 128-разрядный равен значению исходного массива назначения. `ExchangeHigh` и `ExchangeLow` перезаписать целевой 128-разрядный.

0, если сравниваемый операнд не равен исходное значение массива назначения. Значение массива назначения остается неизменным, а значение сравниваемый операнд будет перезаписан со значением массива назначения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_InterlockedCompareExchange128`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция создает `cmpxchg16b` инструкций (с `lock` префикс) для выполнения сравнения заблокированные 128-разрядный и exchange. Более ранние версии AMD 64-разрядное оборудование не поддерживают этой инструкции. Для проверки поддержки оборудования для `cmpxchg16b` инструкция, вызов `__cpuid` встроенная функция с `InfoType=0x00000001 (standard function 1)`. Бит 13 `CPUInfo[2]` (ECX)-1, если инструкция поддерживается.

> [!NOTE]
>  Значение `ComparandResult` всегда перезаписывается. После `lock` инструкции, эта встроенная функция немедленно копирует начальное значение `Destination` для `ComparandResult`. По этой причине `ComparandResult` и `Destination` должен указывать на отдельные ячейки памяти во избежание непредвиденного поведения.

Несмотря на то, что можно использовать `_InterlockedCompareExchange128` для синхронизации потоков нижнего уровня, не нужно синхронизировать более чем 128 бит, если можно использовать более мелкие функции синхронизации (например, другой `_InterlockedCompareExchange` встроенные функции) вместо этого. Используйте `_InterlockedCompareExchange128` Если атомарный доступ к 128-разрядное значение в памяти.

Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `cmpxchg16b` инструкции, результаты будут непредсказуемыми.

Эта процедура доступна только как встроенная.

## <a name="example"></a>Пример

В этом примере используется `_InterlockedCompareExchange128` для замены старшее слово массива из двух 64-разрядных целых чисел с суммой свои слова высокой и низкой, так и для увеличения младшее слово. Доступ к массиву BigInt.Int является атомарной, но в этом примере используется отдельный поток и игнорирует блокировки для простоты.

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

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Встроенные функции _InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)<br/>
[Конфликты с компилятором x86](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)