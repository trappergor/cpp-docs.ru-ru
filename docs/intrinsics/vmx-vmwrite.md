---
title: __vmx_vmwrite | Документы Microsoft
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
ms.openlocfilehash: b87aeafd1b9c0c1a35e3f5d99ab5b9d76410b4d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337721"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Блок, относящийся только к системам Microsoft**  
  
 Записывает заданное значение указанного поля в текущую структуру управления виртуальной машины (VMCS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Field`|VMCS поле для записи.|  
|[in] `FieldValue`|Значение для записи в поле VMCS.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 0  
 Операция успешно выполнена.  
  
 1  
 Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.  
  
 2  
 Сбой операции без сведений о состоянии.  
  
## <a name="remarks"></a>Примечания  
 `__vmx_vmwrite` Функция эквивалентна `VMWRITE` инструкции компьютера. Значение `Field` параметра является индексом кодировке поля, как описано в документации Intel. Для поиска документа «Intel виртуализации технические спецификации для архитектуры IA-32 Intel,» Дополнительные сведения документа номера C97063-002, на [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта, а затем изучите приложения C, документ.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)