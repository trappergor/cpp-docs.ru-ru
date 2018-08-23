---
title: __svm_vmrun | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4711238c45955ee7067e3e418212bcdb0fae09ca
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540504"
---
# <a name="svmvmrun"></a>__svm_vmrun
**Блок, относящийся только к системам Microsoft**  
  
 Запускает выполнение кода гостевой виртуальной машины, соответствующий блок управления указанной виртуальной машины (VMCB).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|Физический адрес VMCB.|  
  
## <a name="remarks"></a>Примечания  
 `__svm_vmrun` Функция использует минимальный объем сведений в VMCB, чтобы начать выполнение кода гостевой виртуальной машины. Используйте [__svm_vmsave](../intrinsics/svm-vmsave.md) или [__svm_vmload](../intrinsics/svm-vmload.md) работать, если вам требуется больше информации для обработки сложных прерывания или переключиться на другой виртуальной машины.  
  
 `__svm_vmrun` Функция эквивалентна `VMRUN` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер документа 24593, редакция 3.11 и более поздних версиях в [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__svm_vmrun`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)