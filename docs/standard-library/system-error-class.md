---
title: "Класс system_error | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::system_error"
  - "std.system_error"
  - "std::system_error"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error - класс"
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс system_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет базовый класс для всех исключений, сгенерированных сообщить низкоуровневые Системная ошибка.  
  
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
  
## <a name="remarks"></a>Заметки  
 Значение, возвращаемое `what` в классе [исключение](../standard-library/exception-class1.md) состоит из `_Message` и сохраненный объект типа [error_code](../standard-library/error-code-class.md) (либо `code` или `error_code(_Errval, _Errcat)`).  
  
 Функция-член `code` Возвращает сохраненный [error_code](../standard-library/error-code-class.md) объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< system_error >  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\< system_error >](../standard-library/system-error.md)

