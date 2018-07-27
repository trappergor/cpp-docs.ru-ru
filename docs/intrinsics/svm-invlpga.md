---
title: __svm_invlpga | Документы Microsoft
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
ms.openlocfilehash: 2e48fc39fd972387ee9fbbe587dc53bf61f2ae59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330399"
---
# <a name="svminvlpga"></a>__svm_invlpga
**Блок, относящийся только к системам Microsoft**  
  
 Делает недействительным запись сопоставления адресов в буфере ассоциативные перевода компьютера. Параметры задают виртуальный адрес и адрес места идентификатор страницы, чтобы сделать недействительными.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Va`|Виртуальный адрес страницы, которую требуется сделать недействительной.|  
|[in] `ASID`|Адрес места идентификатор (ASID) страницы, чтобы сделать недействительными.|  
  
## <a name="remarks"></a>Примечания  
 `__svm_invlpga` Функция эквивалентна `INVLPGA` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения, выполните поиск документа, «AMD64 архитектура программист вручную тома 2: программирование системы» номер 24593, 3.11, редакции документа в [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__svm_invlpga`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)