---
title: "__vmx_vmptrld | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmptrld"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __vmx_vmptrld"
  - "Инструкция VMPTRLD"
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmptrld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Загружает указатель на текущий структуре элемента управления виртуальной машины \(VMCS\) из указанного адреса.  
  
## Синтаксис  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### Параметры  
 \[in\] \*`VmcsPhysicalAddress`  
 Адрес, в котором хранится указатель VMCS.  
  
## Возвращаемое значение  
 0  
 Операция завершилась успешно.  
  
 1  
 Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.  
  
 2  
 Эта операция окончилась неудачей без доступных состояний.  
  
## Заметки  
 Указатель VMCS пакетом обновления 64 \(sp2\) физический адрес.  
  
 Функция `__vmx_vmptrld` эквивалентна инструкцие на компьютере `VMPTRLD`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrst](../intrinsics/vmx-vmptrst.md)