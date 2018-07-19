---
title: __vmx_vmclear | Документы Microsoft
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
ms.openlocfilehash: 8da1e3d2c5b1a2018df0e46f085fede9b923fff8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332414"
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Блок, относящийся только к системам Microsoft**  
  
 Инициализирует структуру управления указанной виртуальной машины (VMCS) и задает ее состояние запуска `Clear`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `VmcsPhysicalAddress`|Указатель памяти 64-разрядных расположение, которое содержит физический адрес VMCS для очистки.|  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 Приложение может выполнять операцию VM-enter, используя либо [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) функция может использоваться только с VMCS, состояние запуска которой `Clear`и [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функция может использоваться только с VMCS, состояние запуска которой — `Launched`. Следовательно, используют [__vmx_vmclear](../intrinsics/vmx-vmclear.md) функцию для задания состояния запуска VMCS `Clear`. Используйте [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) функции для первой операции VM-enter и [__vmx_vmresume](../intrinsics/vmx-vmresume.md) функции для последующих операций VM-enter.  
  
 `__vmx_vmclear` Функция эквивалентна `VMCLEAR` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Для поиска документа «Intel виртуализации технические спецификации для архитектуры IA-32 Intel,» Дополнительные сведения документа номера C97063-002, на [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)