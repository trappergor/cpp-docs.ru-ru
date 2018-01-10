---
title: "__sidt | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __sidt
dev_langs: C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d67e671f2f374790c50e45777d62317d3899c383
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="sidt"></a>__sidt
**Блок, относящийся только к системам Microsoft**  
  
 Сохраняет значение регистра таблицы дескриптора прерываний (IDTR) в заданном расположении памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `Destination`|Указатель на область памяти, в котором хранится IDTR.|  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 `__sidt` Функция эквивалентна `SIDT` инструкции компьютера. Дополнительные сведения, выполните поиск документа, «руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник набор инструкций,» в [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)