---
title: "__lidt | Microsoft Docs"
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
  - "__lidt"
  - "__lidt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция LIDT"
  - "Встроенная функция __lidt"
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Загружает регистр таблицы дескриптора прерывания \(IDTR\) со значением на определенном области памяти.  
  
## Синтаксис  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `Source`|Указатель на значение, которое требуется скопировать в IDTR.|  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__lidt`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Функция `__lidt` эквивалентна инструкцие на компьютере `LIDT` и доступна только в режиме ядра.  Дополнительные сведения см. в документе «руководство разработчика программного обеспечения архитектуры Intel, данном 2. Справочник по наборам инструкций,» на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_sidt](../Topic/__sidt.md)