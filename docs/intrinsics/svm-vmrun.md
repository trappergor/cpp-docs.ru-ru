---
title: "__svm_vmrun | Microsoft Docs"
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
  - "__svm_vmrun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __svm_vmrun"
  - "Инструкция VMRUN"
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_vmrun
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Начинается выполнение кода гостя виртуальной машины, соответствующий указанному блоку управления виртуальной машины \(блоку управления сопоставлений тома\).  
  
## Синтаксис  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `VmcbPhysicalAddress`|Физический адрес блока управления сопоставлений тома.|  
  
## Заметки  
 Функция `__svm_vmrun` использует минимальное количество информации в блоке управления сопоставлений тома, чтобы начать выполнение кода гостя виртуальной машины.  Используйте функцию [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md) или [\_\_svm\_vmload](../intrinsics/svm-vmload.md) если требуется для получения дополнительных сведений обрабатывает сложное прерывание или переходит к другому пользователю.  
  
 Функция `__svm_vmrun` эквивалентна инструкцие на компьютере `VMRUN`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «этом 2 программиста архитектуры AMD64 ручного: Программирование системы,» документ 24593, 3,11 или более поздней версии, на [корпорация AMD](http://go.microsoft.com/fwlink/?LinkId=23746) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)