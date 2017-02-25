---
title: "__lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__lzcnt64"
  - "__lzcnt16"
  - "__lzcnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __lzcnt"
  - "Инструкция lzcnt"
  - "Встроенная функция lzcnt16"
  - "Встроенная функция lzcnt"
  - "Встроенная функция __lzcnt16"
  - "Встроенная функция lzcnt64"
  - "Встроенная функция __lzcnt64"
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __lzcnt16, __lzcnt, __lzcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Подсчитывает количество ведущих нулей в целое число 16 \- 32 \- или 64 байт.  
  
## Синтаксис  
  
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
  
#### Параметры  
 \[входящий\] `value`  
 16 \- 32 \- 64 \(Sp2\) или целых чисел без знака для просмотра для ведущих нулей.  
  
## Возвращаемое значение  
 Количество битов ведущих нулей в параметре `value`.  Если `value` нулю, то возвращаемое значение размер операнда ввода \(16, 32 или 64\).  Если `value` значащий бит, то возвращаемое значение равно нулю.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__lzcnt16`|Предварительная обработка данных bit|  
|`__lzcnt`|Предварительная обработка данных bit|  
|`__lzcnt64`|Предварительная обработка данных 64 бита в 64\-разрядном режиме.|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Каждый из этих встроенных функций формирует инструкцию `lzcnt`.  Размер значений, инструкция `lzcnt` возвращает такое же, как и размер аргумента.  В 64\-разрядном режиме не 32 с пакетом обновления 64 \(sp2\) регистры общего назначения, следовательно, нет пакетом обновления 64 \(sp2 `lzcnt`.  
  
 Чтобы определить аппаратную поддержку для инструкции `lzcnt` вызов внутренним `__cpuid` с `InfoType=0x80000001` и контрольный двоичный разряд 5 `CPUInfo[2] (ECX)`.  Этот бит будет 1, если инструкция поддерживается, и 0 \- в противном случае.  Если запустить код, который использует этот встроенный на оборудовании, не поддерживает инструкцию `lzcnt` результаты становятся непредсказуемыми.  
  
## Пример  
  
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
  
  **\_\_lzcnt16 \(0x0\) \= 16 \_\_lzcnt16 \(0xff\) \= 8 \_\_lzcnt16 \(0xffff\) \= 0 \_\_lzcnt 32 \_\_lzcnt \(0x0\) \= \(0xff\) \= 24 \_\_lzcnt \_\_lzcnt 16 \(0xffff\) \= \(0xffffffff\) \= 0**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
 Авторские права 2007 предварительными микро\- Устройствами, Inc все права защищены.  Воспроизведено с разрешением от предварительных микро\- Устройств, Inc  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)