---
title: "_rotr8, _rotr16 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_rotr16"
  - "_rotr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotr16 intrinsic"
  - "_rotr8 intrinsic"
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotr8, _rotr16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Поворот входных значений вправо к наименьшему значащему разряду \(LSB\) на указанное число позиций разрядов.  
  
## Синтаксис  
  
```  
unsigned char _rotr8(     unsigned char value,     unsigned char shift  ); unsigned short _rotr16(     unsigned short value,     unsigned char shift  );  
```  
  
#### Параметры  
 \[in\] `value`  
 Значение для поворота.  
  
 \[in\] `shift`  
 Число разрядов для поворота.  
  
## Возвращаемое значение  
 Итоговое значение.  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_rotr8`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_rotr16`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 В отличие от операции сдвига вправо, при выполнении правого поворота младшими, упал нулём перемещаются в позиции битов высокого порядка.  
  
## Пример  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
  **Поворот 0x41 влево на 0 разрядов дает 0x41 Поворот 0x41 влево на 1 разряд дает 0x82 Поворот 0x41 влево на 2 разряда дает 0x5 Поворот 0x41 влево на 3 разряда дает 0xa Поворот 0x41 влево на 4 разряда дает 0x14 Поворот 0x41 влево на 5 разрядов дает 0x28 Поворот 0x41 влево на 6 разрядов дает 0x50 Поворот 0x41 влево на 7 разрядов дает 0xa0 Поворот без знакового короткого 0x12 влево на 10 разрядов дает 0x480**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\_rotl8, \_rotl16](../intrinsics/rotl8-rotl16.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)