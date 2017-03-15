---
title: "__svm_vmload | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __svm_vmload"
  - "Инструкция VMLOAD"
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_vmload
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Загружает подмножество состоянии процессора из заданного блока элемента управления виртуальной машины \(блока управления сопоставлений тома\).  
  
## Синтаксис  
  
```  
void __svm_vmload(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `VmcbPhysicalAddress`|Физический адрес блока управления сопоставлений тома.|  
  
## Заметки  
 Функция `__svm_vmload` эквивалентна инструкцие на компьютере `VMLOAD`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «этом 2 программиста архитектуры AMD64 ручного: Программирование системы,» документ 24593, 3,11, на [корпорация AMD](http://go.microsoft.com/fwlink/?LinkId=23746) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__svm_vmload`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmrun](../intrinsics/svm-vmrun.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)