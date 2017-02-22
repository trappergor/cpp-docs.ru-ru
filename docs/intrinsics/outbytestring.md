---
title: "__outbytestring | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outbytestring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция rep outsb"
  - "Встроенная функция __outbytestring"
  - "Инструкция outsb"
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Создает инструкцию `rep outsb`, которая отправляет первый байт `Count` данных, указанных в `Buffer` к порту, заданному `Port`.  
  
## Синтаксис  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### Параметры  
 \[входящий\] `Port`  
 Порт отправлять данные.  
  
 \[входящий\] `Buffer`  
 Данные, которые будут отправляться вне указанному порту.  
  
 \[входящий\] `Count`  
 Число байтов данных.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__outbytestring`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)