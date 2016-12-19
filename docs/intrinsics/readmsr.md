---
title: "__readmsr | Microsoft Docs"
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
  - "__readmsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Чтение модельнозависимого регистра"
  - "Инструкция rdmsr"
  - "Встроенная функция __readmsr"
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readmsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Создает инструкцию `rdmsr`, которая считывает регистр модель\-специфического указанный `register` и возвращает его значение.  
  
## Синтаксис  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### Параметры  
 \[входящий\] `register`  
 Модели определенный регистр для чтения.  
  
## Возвращаемое значение  
 Значение в указанном регистре.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__readmsr`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Эта функция доступна только в режиме ядра и процедура доступна только в качестве внутреннего элемента.  
  
 Дополнительные сведения см. в документации AMD.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)