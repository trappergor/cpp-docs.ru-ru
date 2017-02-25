---
title: "Класс filesystem_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::filesystem_error"
dev_langs: 
  - "C++"
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Класс filesystem_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Базовый класс для всех исключений, создаваемых для отчета о переполнении системы низкого уровня.  
  
## Синтаксис  
  
```  
class filesystem_error    : public system_error;  
```  
  
## Заметки  
 Этот класс служит базовым классом для всех исключений, уведомляющих об ошибке в функциях \<filesystem\>. Он хранит объект типа string \(называемый здесь mymesg в целях демонстрации\). Он также хранит два объекта типа path, называемые mypval1 и mypval2.  
  
## filesystem\_error::filesystem\_error  
  
```  
filesystem_error(const string& what_arg, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, const path& pval2, error_code ec);  
```  
  
 Первый конструктор создает сообщение из what\_arg и ec. Второй конструктор также создает сообщение из pval1, которое он сохраняет в mypval1. Третий конструктор также создает сообщение из pval1, которое он сохраняет в mypval1, и из pval2, которое он сохраняет в mypval2.  
  
## filesystem\_error::path1  
  
```  
const path& path1() const noexcept;  
  
```  
  
 Функция\-член возвращает значение mypval1.  
  
## filesystem\_error::path2  
  
```  
const path& path2() const noexcept;  
  
```  
  
 Функция\-член возвращает значение mypval2.  
  
## filesystem\_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 Функция\-член возвращает указатель на строку NTBS, предпочтительно состоящую из runtime\_error::what\(\), system\_error::what\(\), mymesg, mypval1.native\_string\(\) и mypval2.native\_string\(\).  
  
## Требования  
 **Заголовок:** filesystem  
  
 **Пространство имен:** std::tr2::sys  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс system\_error](../standard-library/system-error-class.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)   
 [\<exception\>](../standard-library/exception.md)