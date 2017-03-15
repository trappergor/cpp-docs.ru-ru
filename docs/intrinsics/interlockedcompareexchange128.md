---
title: "_InterlockedCompareExchange128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchange128_cpp"
  - "_InterlockedCompareExchange128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция cmpxchg16b"
  - "Встроенная функция _InterlockedCompareExchange128"
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _InterlockedCompareExchange128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Выполняет 128 бит сравнивает предоставленный и обменивает.  
  
## Синтаксис  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### Параметры  
 \[in, out\] `Destination`  
 Указатель на массив назначения, 2 64 целые числа рассматриваемых в поле 128 бит.  Данные назначения должны быть байтом 16 выравниванным, чтобы избежать общая ошибка защиты.  
  
 \[входящий\] `ExchangeHigh`  
 64 \- Целое число, которое может быть обменяно с высокой частью назначения.  
  
 \[входящий\] `ExchangeLow`  
 64 \- Целое число, которое может быть обменяно с нижней частью назначения.  
  
 \[in, out\] `ComparandResult`  
 Указатель на массив 2 64 целые числа рассматриваемых в виде поля \(128 бит\), сравниваемый с назначением.  На выходе, это заменено с исходным значением назначения.  
  
## Возвращаемое значение  
 Сравниваемый операнд 128 бит равен 1, если исходное значение.  `ExchangeHigh` и `ExchangeLow` перезапись назначение 128 бит.  
  
 Сравниваемый операнд не равен 0, если исходное значение.  Целевое значение не меняется и значение сравниваемый операнд заменено значением назначения.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный создает инструкцию `cmpxchg16b` \(с префиксом `lock` \) для выполнения блокирована 128 бит сравнивает и обменивает.  Предыдущие версии оборудования AMD 64 не поддерживают эту инструкцию edition.  Для проверки аппаратной поддержки для инструкции `cmpxchg16b`, вызовите внутреннего элемента `__cpuid` с `InfoType=0x00000001 (standard function 1)`.  Бит 13 `CPUInfo[2]`\(ECX\) 1, если инструкция поддерживается.  
  
> [!NOTE]
>  Значение `ComparandResult` всегда перезаписывается.  После инструкции `lock` этот встроенный немедленно копирует начальное значение `Destination` к `ComparandResult`.  По этой причине `ComparandResult` и `Destination` должны указывать для разделения областей памяти, чтобы избежать непредвиденной функциональности.  
  
 Хотя можно использовать для синхронизации потоков `_InterlockedCompareExchange128` низкого уровня не требуется синхронизировать через 128 битами если можно использовать более малые функции синхронизации \(как и другие встроенные функции `_InterlockedCompareExchange` \).  Используйте `_InterlockedCompareExchange128` если требуется является атомарным доступ к значению 128 бита в памяти.  
  
 Если запустить код, который использует этот встроенный на оборудовании, не поддерживает инструкцию `cmpxchg16b` результаты становятся непредсказуемыми.  
  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## Пример  
 В этом примере используется `_InterlockedCompareExchange128`, чтобы заменить высокое слово массива 2 64 целых чисел на сумму своих повсюду слов и увеличения низкое слово.  Доступ к массиву BigInt.Int атомн, но в этом примере используется однозаходную поток и игнорирует блокировать для простоты.  
  
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
  
  **BigInt.Int \[1\] \= 34, BigInt.Int \[0\] \= 12**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
 Авторские права 2007 предварительными микро\- Устройствами, Inc все права защищены.  Воспроизведено с разрешением от предварительных микро\- Устройств, Inc  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_InterlockedCompareExchange Intrinsic Functions](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)