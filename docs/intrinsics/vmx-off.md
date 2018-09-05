---
title: __vmx_off | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_off
dev_langs:
- C++
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 924cd8f502b6fe41aa4733df3dc59a372c27e6cb
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683639"
---
# <a name="vmxoff"></a>__vmx_off
**Блок, относящийся только к системам Microsoft**  
  
 Деактивирует операции расширения (VMX) виртуальной машины в процессоре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __vmx_off();  
```  
  
## <a name="remarks"></a>Примечания  
 `__vmx_off` Функция эквивалентна `VMXOFF` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_off`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)