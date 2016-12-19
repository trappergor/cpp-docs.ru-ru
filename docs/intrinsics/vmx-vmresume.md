---
title: "__vmx_vmresume | Microsoft Docs"
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
  - "__vmx_vmresume"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __vmx_vmresume"
  - "Инструкция VMRESUME"
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmresume
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Возобновляет некорневую операцию VMX, используя текущую структуру управления виртуальной машины \(VMCS\).  
  
## Синтаксис  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## Возвращаемое значение  
  
|Значение|Смысл|  
|--------------|-----------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## Заметки  
 Приложение может выполнять операцию VM\-enter, используя функцию [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) или `__vmx_vmresume`. Функцию `__vmx_vmlaunch` можно использовать только с VMCS, состояние запуска которой — `Clear`, а функцию `__vmx_vmresume` можно использовать только с VMCS, состояние запуска которой — `Launched`. Следовательно, используйте функцию [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) для задания состояния запуска VMCS `Clear`, а затем используйте функцию `__vmx_vmlaunch` для первой операции VM\-enter и функцию `__vmx_vmresume` для последующих операций VM\-enter.  
  
 Функция `__vmx_vmresume` эквивалентна инструкции компьютера `VMRESUME`. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в PDF\-документе Intel Virtualization Technical Specification for the IA\-32 Intel Architecture \(Техническая спецификация виртуализации Intel для архитектуры Intel IA\-32\); номер документа C97063\-002, на сайте [корпорации Intel](http://go.microsoft.com/fwlink/?LinkId=127).  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)