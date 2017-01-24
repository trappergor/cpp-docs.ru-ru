---
title: "__inbyte | Microsoft Docs"
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
  - "__inbyte"
  - "__inbyte_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция in"
  - "Встроенная функция __inbyte"
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Создает инструкцию `in`, возвращая один байт, считанный из указанного `Port` порта.  
  
## Синтаксис  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### Параметры  
 \[входящий\] `Port`  
 Порт, из которого выполняется чтение.  
  
## Возвращаемое значение  
 Байт, считанный из указанного порта.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__inbyte`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## Заметки  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)