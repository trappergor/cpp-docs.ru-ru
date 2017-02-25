---
title: "__stosq | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__stosq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция rep stosq"
  - "Инструкция stosq"
  - "Встроенная функция __stosq"
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# __stosq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Формирует инструкцию строки хранилища \(`rep stosq`\).  
  
## Синтаксис  
  
```  
void __stosb(   
   unsigned __int64* Dest,   
   unsigned __int64 Data,   
   size_t Count   
);  
```  
  
#### Параметры  
 \[исходящий\] `Dest`  
 Назначение операции.  
  
 \[входящий\] `Data`  
 Сохраняемые данные.  
  
 \[входящий\] `Count`  
 Длина блока quadwords, которые требуется записать.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__stosq`|AMD64|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 В результате quadword `Data` помещается в блок quadwords `Count` в строке `Dest`.  
  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## Пример  
  
```  
// stosq.c  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosq)  
  
int main()  
{  
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;  
   unsigned __int64 a[10];  
   memset(a, 0, sizeof(a));  
   __stosq(a+1, val, 2);  
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
## Output  
  
```  
0 ffffffffffff ffffffffffff 0  
```  
  
### ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)