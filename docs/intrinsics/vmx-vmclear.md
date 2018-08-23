---
title: __vmx_vmclear | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d93cff5c1be0847a6c88f0d60b89527388e4d8b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538358"
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Блок, относящийся только к системам Microsoft**  
  
 Инициализирует структуру управления указанной виртуальной машины (VMCS) и устанавливает состояние запуска `Clear`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `VmcsPhysicalAddress`|Указатель на адрес памяти 64-разрядной, содержащий физический адрес VMCS для очистки.|  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 Приложение может выполнять операцию VM-enter, либо при помощи [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) функция может использоваться только с VMCS, состояние запуска которой — `Clear`и [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функция может использоваться только с VMCS, состояние запуска которой — `Launched`. Следовательно, используйте [__vmx_vmclear](../intrinsics/vmx-vmclear.md) функцию для задания состояния запуска VMCS `Clear`. Используйте [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) функции для первой операции VM-enter и [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции для последующих операций VM-enter.  
  
 `__vmx_vmclear` Функция эквивалентна `VMCLEAR` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmclear`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)