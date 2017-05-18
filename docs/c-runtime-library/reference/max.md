---
title: "__max | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __max
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a73c66cc0d1e49c514f8f451aa01a0c8ca7a9277
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="max"></a>__max
Возвращает большее из двух значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Любой числовой тип данных.  
  
 `a, b`  
 Сравниваемые значения любого числового типа данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `__max` возвращает больший из двух своих аргументов.  
  
## <a name="remarks"></a>Примечания  
 Макрос `__max` сравнивает два значения и возвращает значение большего. Аргументы могут быть любого числового типа данных со знаком или без знака. Оба аргумента и возвращаемое значение должны принадлежать к одному типу данных.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>Пример  
 Дополнительные сведения см. в приведенных ниже примерах для функции [__min](../../c-runtime-library/reference/min.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)
