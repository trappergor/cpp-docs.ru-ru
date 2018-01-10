---
title: "Класс future_error | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: future/std::future_error
dev_langs: C++
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc5ba9a34ee5c1a29892e4ba6ebc25366e408be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="futureerror-class"></a>Класс future_error
Описывает объект исключения, который можно вызывать методами типов, управляющих объектами [future](../standard-library/future-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<будущих >  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс logic_error](../standard-library/logic-error-class.md)   
 [Класс error_code](../standard-library/error-code-class.md)
