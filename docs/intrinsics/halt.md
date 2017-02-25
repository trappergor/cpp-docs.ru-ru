---
title: "__halt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__halt"
  - "__halt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __halt"
  - "Инструкция HLT"
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __halt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Останавливает микропроцессор до тех пор, пока включено прерывание, немаскируемое прерывание \(немаскируемое прерывание\) или возврат не возникнет.  
  
## Синтаксис  
  
```  
void __halt( void );  
```  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__halt`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Функция `__halt` эквивалентна инструкцие на компьютере `HLT` и доступна только в режиме ядра.  Дополнительные сведения см. в документе «руководство разработчика программного обеспечения архитектуры Intel, данном 2. Справочник по наборам инструкций,» на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)