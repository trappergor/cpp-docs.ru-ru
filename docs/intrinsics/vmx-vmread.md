---
title: __vmx_vmread | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f03ea1ea39b9202d4bb7b850bb81354a4a47f1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677384"
---
# <a name="vmxvmread"></a>__vmx_vmread
**Блок, относящийся только к системам Microsoft**  
  
 Считывает указанное поле из текущую структуру управления виртуальной машины (VMCS) и помещает его в указанном расположении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Field`|Поле VMCS для чтения.|  
|[in] `FieldValue`|Указатель на расположение для хранения значения чтения из VMCS поле, указанное параметром `Field` параметр.|  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 `__vmx_vmread` Функция эквивалентна `VMREAD` инструкции компьютера. Значение `Field` параметр является индекс кодировке поля, который описан в документации Intel. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта, а затем см. в приложении С этим документом .  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmread`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)