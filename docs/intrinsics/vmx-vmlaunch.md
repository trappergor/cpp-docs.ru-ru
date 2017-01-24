---
title: "__vmx_vmlaunch | Microsoft Docs"
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
  - "__vmx_vmlaunch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция VMLAUNCH"
  - "Встроенная функция __vmx_vmlaunch"
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmlaunch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Устанавливает вызывающее приложение в состоянии операции \(VMX \(кроме корневого\) введите виртуальной машины\) с помощью текущей структуры элемента управления виртуальной машины \(VMCS\).  
  
## Синтаксис  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## Возвращаемое значение  
  
|Значение|Значение|  
|--------------|--------------|  
|0|Операция завершилась успешно.|  
|1|Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.|  
|2|Эта операция окончилась неудачей без доступных состояний.|  
  
## Заметки  
 Приложение может выполнить операцию Виртуальная машина\-ввестей с помощью [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) или функции [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md).  [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) Функцию можно использовать только с VMCS которого состояние запуска `Clear` и функцию [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) можно использовать только с VMCS которого состояние запуска `Launched`.  Следовательно, используйте функцию [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) чтобы задать состояние запуска VMCS к `Clear`, а затем используйте функцию [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) для первой операции Виртуальная машина\-ввестей и функции [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) для последующих операций Виртуальная машина\-ввестей.  
  
 Функция `__vmx_vmlaunch` эквивалентна инструкцие на компьютере `VMLAUNCH`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)