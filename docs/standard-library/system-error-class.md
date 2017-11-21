---
title: "Класс system_error | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::system_error
dev_langs: C++
helpviewer_keywords: system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 975fcf228191695e419df2b04bd5578e15924f6b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="systemerror-class"></a>Класс system_error
Представляет базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>Примечания  
 Значение, возвращаемое `what` в классе [exception](../standard-library/exception-class.md), создается на основе `_Message` и хранимого объекта типа [error_code](../standard-library/error-code-class.md) (`code` или `error_code(_Errval, _Errcat)`).  
  
 Функция-член `code` возвращает хранимый объект [error_code](../standard-library/error-code-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<system_error>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<system_error>](../standard-library/system-error.md)

