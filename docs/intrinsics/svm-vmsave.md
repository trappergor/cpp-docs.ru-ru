---
title: "__svm_vmsave | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmsave"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция VMSAVE"
  - "Встроенная функция __svm_vmsave"
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# __svm_vmsave
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Хранит подмножество состоянии процессоров в указанном блоке управления виртуальной машины \(блоке управления сопоставлений тома\).  
  
## Синтаксис  
  
```  
void __svm_vmsave(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `VmcbPhysicalAddress`|Физический адрес блока управления сопоставлений тома.|  
  
## Заметки  
 Функция `__svm_vmsave` эквивалентна инструкцие на компьютере `VMSAVE`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «этом 2 программиста архитектуры AMD64 ручного: Программирование системы,» документ 24593, 3,11 или более поздней версии, на [AMD Корпорация](http://go.microsoft.com/fwlink/?LinkId=23746) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__svm_vmsave`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmrun](../intrinsics/svm-vmrun.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)