---
title: __vmx_vmptrld | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 599e15414a944602ee196f3910a1c5dd561c906d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Блок, относящийся только к системам Microsoft**  
  
 Загружает ссылку на текущую структуру управления виртуальной машины (VMCS) из указанного адреса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] *`VmcsPhysicalAddress`  
 Адрес, где хранятся VMCS указателя.  
  
## <a name="return-value"></a>Возвращаемое значение  
 0  
 Операция успешно выполнена.  
  
 1  
 Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.  
  
 2  
 Сбой операции без сведений о состоянии.  
  
## <a name="remarks"></a>Примечания  
 Указатель VMCS — это физический адрес 64-разрядной.  
  
 `__vmx_vmptrld` Функция эквивалентна `VMPTRLD` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Для поиска документа «Intel виртуализации технические спецификации для архитектуры IA-32 Intel,» Дополнительные сведения документа номера C97063-002, на [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)