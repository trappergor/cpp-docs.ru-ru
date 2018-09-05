---
title: __svm_vmload | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmload
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d3f82633c9bd48ede71853dbe383352b0b3d6f5
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692868"
---
# <a name="svmvmload"></a>__svm_vmload
**Блок, относящийся только к системам Microsoft**  
  
 Загружает часть состояния процессора из блока управления указанной виртуальной машины (VMCB).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __svm_vmload(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|Физический адрес VMCB.|  
  
## <a name="remarks"></a>Примечания  
 `__svm_vmload` Функция эквивалентна `VMLOAD` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер 24593, 3.11, версия документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__svm_vmload`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmrun](../intrinsics/svm-vmrun.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)