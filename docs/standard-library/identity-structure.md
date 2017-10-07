---
title: "Структура identity | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: dd840dba1de5e389e2fa1d8585d677d3be255f8e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="identity-structure"></a>Структура identity
Структура, предоставляющая определение типа как параметр шаблона.  
  
## <a name="syntax"></a>Синтаксис  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Значение, которое необходимо идентифицировать.|  
  
## <a name="remarks"></a>Примечания  
 Класс содержит определение открытого типа `type`, которое совпадает с типом параметра-шаблона. Он используется в сочетании с функцией шаблона [forward](../standard-library/utility-functions.md#forward) для проверки того, что параметр функции имеет требуемый тип.  
  
 Для обеспечения совместимости со старым кодом этот класс также определяет функцию identity `operator()`, которая возвращает свой аргумент `left`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<utility>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<utility>](../standard-library/utility.md)




