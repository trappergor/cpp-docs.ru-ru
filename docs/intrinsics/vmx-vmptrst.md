---
title: "__vmx_vmptrst | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmptrst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __vmx_vmptrst"
  - "Инструкция VMPTRST"
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmptrst
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Сохраняет указатель на текущий структуре элемента управления виртуальной машины \(VMCS\) по указанному адресу.  
  
## Синтаксис  
  
```  
void __vmx_vmptrst(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### Параметры  
 \[in\] \*`VmcsPhysicalAddress`  
 Адрес, в котором хранится указатель текущего VMCS.  
  
## Заметки  
 Указатель VMCS пакетом обновления 64 \(sp2\) физический адрес.  
  
 Функция `__vmx_vmptrst` эквивалентна инструкцие на компьютере `VMPTRST`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmptrst`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrld](../intrinsics/vmx-vmptrld.md)