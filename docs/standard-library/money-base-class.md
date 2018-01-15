---
title: "Класс money_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocmon/std::money_base
dev_langs: C++
helpviewer_keywords: money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9b3243807c407fa4deeb30b8f35aa6f7acb13707
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="moneybase-class"></a>Класс money_base
Данный класс описывает перечисление и структуру, общие для всех специализаций класса-шаблона [moneypunct](../standard-library/moneypunct-class.md).  
  
## <a name="syntax"></a>Синтаксис  
```    
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};  
```  
## <a name="remarks"></a>Примечания  
 Перечисление **часть** описывает возможные значения в элементах поля массива в шаблоне структуры. Значения **часть**:  
  
- **none** для соответствия нулю или более пробелам или для формирования пустого значения.  
  
- **sign** для соответствия или формирования знака плюс или минус.  
  
- **space** для соответствия нулю или более пробелам или для формирования пробела.  
  
- **symbol** для соответствия или формирования символа валюты.  
  
- **value** для соответствия или формирования денежного значения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



