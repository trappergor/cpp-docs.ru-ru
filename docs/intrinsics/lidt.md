---
title: __lidt | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs:
- C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd972d2a7e8d75f7149b2dc2766ffca86b0b2e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lidt"></a>__lidt
**Блок, относящийся только к системам Microsoft**  
  
 Загружает регистр таблицы дескриптора прерывания (IDTR) со значением в заданном расположении памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Source`|Указатель на значение для копирования IDTR.|  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__lidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 `__lidt` Функция эквивалентна `LIDT` инструкции компьютера и доступен только в режиме ядра. Дополнительные сведения, выполните поиск документа, «руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник набор инструкций,» в [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)