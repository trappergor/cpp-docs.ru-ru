---
title: __vmx_vmlaunch | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmlaunch
dev_langs:
- C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a0d7b5b26c5cf805e0fef8c5fb2785ebf3712b4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678481"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch
**Блок, относящийся только к системам Microsoft**  
  
 Помещает вызывающего приложения в состоянии некорневую операцию VMX (введите виртуальной Машины), используя текущую структуру управления виртуальной машины (VMCS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 Приложение может выполнять операцию VM-enter, либо при помощи [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) функция может использоваться только с VMCS, состояние запуска которой — `Clear`и [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функция может использоваться только с VMCS, состояние запуска которой — `Launched`. Следовательно, используйте [__vmx_vmclear](../intrinsics/vmx-vmclear.md) функцию для задания состояния запуска VMCS `Clear`, а затем с помощью [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) для первой операции VM-enter и функцию[__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции для последующих операций VM-enter.  
  
 `__vmx_vmlaunch` Функция эквивалентна `VMLAUNCH` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmlaunch`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)