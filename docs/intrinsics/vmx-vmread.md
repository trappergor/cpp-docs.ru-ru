---
title: "__vmx_vmread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция VMREAD"
  - "Встроенная функция __vmx_vmread"
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_vmread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Считывает указанное поле из текущей структуры элемента управления виртуальной машины \(VMCS\) и мест в указанном месте.  
  
## Синтаксис  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[входящий\] `Field`|Поле VMCS для чтения.|  
|\[входящий\] `FieldValue`|Указатель на место для хранения значения, считанные из поля VMCS, заданного параметром `Field`.|  
  
## Возвращаемое значение  
  
|Значение|Значение|  
|--------------|--------------|  
|0|Операция завершилась успешно.|  
|1|Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.|  
|2|Эта операция окончилась неудачей без доступных состояний.|  
  
## Заметки  
 Функция `__vmx_vmread` эквивалентна инструкцие на компьютере `VMREAD`.  Значение параметра `Field` закодированный показатель неоднородности поля, описанный в документации Intel.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте, затем советует с приложением C\# этого документа.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmwrite](../intrinsics/vmx-vmwrite.md)