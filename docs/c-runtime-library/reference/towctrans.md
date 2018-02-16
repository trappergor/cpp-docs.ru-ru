---
title: "towctrans | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79bd4c48b5462d0d7b3cc7145a3044da80869af1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="towctrans"></a>towctrans
Преобразует символ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется преобразовать.  
  
 `category`  
 Идентификатор, который содержит возвращаемое значение [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Символ `c` после того, как функция `towctrans` использовала правило преобразования в категории `category`.  
  
## <a name="remarks"></a>Примечания  
 Значение `category` должно возвращаться предыдущим успешным вызовом функции [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Пример использования функции `wctrans` см. в разделе `towctrans`.  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)