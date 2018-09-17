---
title: __svm_invlpga | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_invlpga
dev_langs:
- C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2f962ec4a348cca7ffdf43852cb01d673f3fb18
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706606"
---
# <a name="svminvlpga"></a>__svm_invlpga
**Блок, относящийся только к системам Microsoft**  
  
 Запись сопоставления адресов в буфере ассоциативные перевода компьютера не делает недействительными. Параметры определяют виртуальный адрес и адрес места идентификатор страницы, чтобы сделать недействительным.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|*VA*|[in] Виртуальный адрес страницы, чтобы сделать недействительным.|  
|*ASID*|[in] Адрес места идентификатор (ASID) страницы, чтобы сделать недействительным.|  
  
## <a name="remarks"></a>Примечания  
 `__svm_invlpga` Функция эквивалентна `INVLPGA` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер 24593, 3.11, версия документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__svm_invlpga`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)