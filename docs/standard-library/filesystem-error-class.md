---
title: "Класс filesystem_error | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::experimental::filesystem::filesystem_error
dev_langs: C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0012a895dbda27ce26d50ae49b3752d13963a89f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="filesystemerror-class"></a>Класс filesystem_error
Базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class filesystem_error    : public system_error;  
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс служит базовым классом для всех исключений, уведомляющих об ошибке в функциях \<filesystem>. Он хранит объект типа string (называемый здесь mymesg в целях демонстрации). Он также хранит два объекта типа path, называемые mypval1 и mypval2.  
  
## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error  
  
```  
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    const path& pval2,
    error_code ec);
```  
  
 Первый конструктор создает сообщение из what_arg и ec. Второй конструктор также создает сообщение из pval1, которое он сохраняет в mypval1. Третий конструктор также создает сообщение из pval1, которое он сохраняет в mypval1, и из pval2, которое он сохраняет в mypval2.  
  
## <a name="filesystemerrorpath1"></a>filesystem_error::path1  
  
```  
const path& path1() const noexcept;  
```  
  
 Функция-член возвращает значение mypval1.  
  
## <a name="filesystemerrorpath2"></a>filesystem_error::path2  
  
```  
const path& path2() const noexcept;  
```  
  
 Функция-член возвращает значение mypval2.  
  
## <a name="filesystemerrorwhat"></a>filesystem_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 Функция-член возвращает указатель на строку NTBS, предпочтительно состоящую из runtime_error::what(), system_error::what(), mymesg, mypval1.native_string() и mypval2.native_string().  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<filesystem >  
  
 **Пространство имен:** std::experimental::filesystem  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс system_error](../standard-library/system-error-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [\<exception>](../standard-library/exception.md)

