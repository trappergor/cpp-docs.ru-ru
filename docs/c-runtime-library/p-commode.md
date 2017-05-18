---
title: "__p__commode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1ae9ef3c73cb3b88eb33869fbbfac090acac1921
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="pcommode"></a>__p__commode
Указывает на глобальную переменную `_commode`, которая определяет значение *режима фиксации файлов* по умолчанию для операций ввода-вывода файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную переменную `_commode`.  
  
## <a name="remarks"></a>Примечания  
 Функция `__p__commode` предназначена только для внутреннего пользования и не должна вызываться из кода пользователя.  
  
 Режим фиксации файлов указывает, когда на диск записываются критические данные. Дополнительные сведения см. в разделе [fflush](../c-runtime-library/reference/fflush.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|__p\__commode|internal.h|
