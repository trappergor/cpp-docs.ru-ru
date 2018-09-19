---
title: __vmx_on | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_on
dev_langs:
- C++
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cefe61fc6fb651933a76cfc36b3039d48ea9de9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713405"
---
# <a name="vmxon"></a>__vmx_on
**Блок, относящийся только к системам Microsoft**  
  
 Активирует операции расширения (VMX) виртуальной машины в процессоре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
*VmsSupportPhysicalAddress*<br/>
[in] Указатель на 64-разрядный физический адрес, который указывает на структуру управления виртуальной машины (VMCS).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 `__vmx_on` Соответствует функции `VMXON` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_on`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)