---
title: "__nop | Microsoft Docs"
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
  - "__nop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция nop"
  - "Встроенная функция __nop"
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __nop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Создает платформа\-специфического машинный код, который не выполняет никакой операции.  
  
## Синтаксис  
  
```  
void __nop();  
```  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## Заметки  
 Функция `__nop` эквивалентна инструкцие на компьютере `NOP`.  Дополнительные сведения см. в документе «руководство разработчика программного обеспечения архитектуры Intel, данном 2. Справочник по наборам инструкций,» на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_noop](../intrinsics/noop.md)