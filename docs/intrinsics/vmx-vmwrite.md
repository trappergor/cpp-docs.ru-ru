---
title: __vmx_vmwrite | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec022fe2d317ec38bc1d9b06f459b9efc7818c92
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541870"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Блок, относящийся только к системам Microsoft**  
  
 Записывает заданное значение указанного поля в текущей структуре управления виртуальной машины (VMCS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `Field`|Поле VMCS для записи.|  
|[in] `FieldValue`|Значение для записи в поле VMCS.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 0  
 Операция успешно выполнена.  
  
 1  
 Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.  
  
 2  
 Сбой операции без сведений о состоянии.  
  
## <a name="remarks"></a>Примечания  
 `__vmx_vmwrite` Функция эквивалентна `VMWRITE` инструкции компьютера. Значение `Field` параметр является индекс кодировке поля, который описан в документации Intel. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](http://go.microsoft.com/fwlink/p/?linkid=127) к сайту, а затем изучите приложения C, документ.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmwrite`|X64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)