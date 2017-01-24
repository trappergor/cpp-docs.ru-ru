---
title: "__vmx_on | Microsoft Docs"
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
  - "__vmx_on"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция VMXON"
  - "Встроенная функция __vmx_on"
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_on
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Активировать операция расширений виртуальной машины \(VMX\) в процессоре.  
  
## Синтаксис  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### Параметры  
 \[входящий\] `VmsSupportPhysicalAddress`  
 Указатель к физическому адресу с пакетом обновления 64 \(sp2\), указывающий на структуре элемента управления виртуальной машины \(VMCS\).  
  
## Возвращаемое значение  
  
|Значение|Значение|  
|--------------|--------------|  
|0|Операция завершилась успешно.|  
|1|Операция завершилась неуспешно с расширенным доступным текущего состояния в `VM-instruction error field` VMCS.|  
|2|Эта операция окончилась неудачей без доступных состояний.|  
  
## Заметки  
 Функция `__vmx_on` соответствует инструкцие на компьютере `VMXON`.  Эта функция поддерживает взаимодействие монитора виртуальной машины узла с операционной системой для виртуальной машине и своими приложениями.  Дополнительные сведения см. в документе «технические данные виртуализации Intel для IA\-32 архитектуры Intel,» номер документа C97063\-002, на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__vmx_on`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)