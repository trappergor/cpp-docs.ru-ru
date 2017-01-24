---
title: "_rotl8, _rotl16 | Microsoft Docs"
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
  - "_rotl8"
  - "_rotl16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotl16 intrinsic"
  - "_rotl8 intrinsic"
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotl8, _rotl16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Поворачивает входные значения влево к наиболее значащему биту \(MSB\) на указанное число разрядов .  
  
## Синтаксис  
  
```  
unsigned char _rotl8(     unsigned char value,     unsigned char shift  ); unsigned short _rotl16(     unsigned short value,     unsigned char shift  );  
```  
  
#### Параметры  
 \[in\] `value`  
 Значение для поворота.  
  
 \[in\] `shift`  
 Число битов для поворота.  
  
## Возвращаемое значение  
 Итоговое значение.  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_rotl8`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_rotl16`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 В отличие от операции сдвига влево, при выполнении левого поворота старшие разряды, попавшие за верхний предел, перемещаются в наименьшие разряды.  
  
## Пример  
  
```  
// rotl.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotl8, _rotl16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,  
               i, _rotl8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",  
            s, nBit, _rotl16(s, nBit));  
}  
```  
  
  **Поворот 0x41 влево на 0 разрядов дает 0x41 Поворот 0x41 влево на 1 разрядов дает 0x82 Поворот 0x41 влево на 2 разрядов дает 0x5 Поворот 0x41 влево на 3 разрядов дает 0xa Поворот 0x41 влево на 4 разрядов дает 0x14 Поворот 0x41 влево на 5 разрядов дает 0x28 Поворот 0x41 влево на разрядов дает 0x50 Поворот 0x41 влево на 7 разрядов дает 0xa0 Поворот без знакового короткого 0x12 влево на 10 разрядов дает 0x4800**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\_rotr8, \_rotr16](../intrinsics/rotr8-rotr16.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)