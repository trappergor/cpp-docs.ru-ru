---
title: "Класс money_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b9c41737288a4d323057b42f809dcbf4a3f2ff2c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

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




