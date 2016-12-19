---
title: "__vmx_vmclear | Microsoft Docs"
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
  - "__vmx_vmclear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция VMCLEAR"
  - "Встроенная функция __vmx_vmclear"
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmclear
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Инициализирует указанную структуру элемента управления виртуальной машины \(VMCS\) и наборы свое состояние запуска в `Clear`.  
  
## Синтаксис  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `VmcsPhysicalAddress`|Указатель на 64 расположение в памяти, содержащий физический адрес VMCS для очистки.|  
  
## Возвращаемое значение  
  
|Значение|Значение|  
|--------------|--------------|  
|0|Операция завершилась успешно.|  
|1|Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.|  
|2|Эта операция окончилась неудачей без доступных состояний.|  
  
## Заметки  
 Приложение может выполнить операцию Виртуальная машина\-ввестей с помощью [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) или функции [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md).  [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) Функцию можно использовать только с VMCS которого состояние запуска `Clear` и функцию [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) можно использовать только с VMCS которого состояние запуска `Launched`.  Следовательно, используйте функцию [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) чтобы задать состояние запуска VMCS к `Clear`.  Используйте функцию [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) для первой операции Виртуальная машина\-ввестей и функции [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) для последующих операций Виртуальная машина\-ввестей.  
  
 Функция `__vmx_vmclear` эквивалентна инструкцие на компьютере `VMCLEAR`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)