---
title: "__vmx_vmwrite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmwrite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __vmx_vmwrite"
  - "Инструкция VMWRITE"
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmwrite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Записывает указанное значение к указанному полю в текущей структуре элемента управления виртуальной машины \(VMCS\).  
  
## Синтаксис  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `Field`|Поле VMCS, которые требуется записать.|  
|\[входящий\] `FieldValue`|Записываемое значение в поле VMCS.|  
  
## Возвращаемое значение  
 0  
 Операция завершилась успешно.  
  
 1  
 Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.  
  
 2  
 Эта операция окончилась неудачей без доступных состояний.  
  
## Заметки  
 Функция `__vmx_vmwrite` эквивалентна инструкцие на компьютере `VMWRITE`.  Значение параметра `Field` закодированный показатель неоднородности поля, описанный в документации Intel.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте, а затем советуют с приложением C\# этого документа.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmread](../intrinsics/vmx-vmread.md)