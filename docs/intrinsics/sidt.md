---
title: __sidt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 202e982d30fd0877814fa0c0fe967091057f920f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685981"
---
# <a name="sidt"></a>__sidt
**Блок, относящийся только к системам Microsoft**  
  
 Сохраняет значение регистра таблицу дескриптора прерываний (IDTR) в указанной области памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Destination`|Указатель на область памяти, где хранится IDTR.|  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__sidt`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 `__sidt` Функция эквивалентна `SIDT` инструкции компьютера. Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)