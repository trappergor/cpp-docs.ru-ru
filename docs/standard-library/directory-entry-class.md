---
title: "Класс directory_entry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator const std::experimental::filesystem::v1::path &"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator="
  - "std::experimental::filesystem::v1::directory_entry::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::assign"
  - "std::experimental::filesystem::v1::directory_entry::assign"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::path"
  - "std::experimental::filesystem::v1::directory_entry::path"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::status"
  - "std::experimental::filesystem::v1::directory_entry::status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<"
  - "std::experimental::filesystem::v1::directory_entry::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator=="
  - "std::experimental::filesystem::v1::directory_entry::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator!="
  - "std::experimental::filesystem::v1::directory_entry::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<="
  - "std::experimental::filesystem::v1::directory_entry::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>"
  - "std::experimental::filesystem::v1::directory_entry::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>="
  - "std::experimental::filesystem::v1::directory_entry::operator>="
dev_langs: 
  - "C++"
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс directory_entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, возвращаемый `*X`, где *X* — [directory\_iterator](../Topic/directory_iterator%20Class.md) или [recursive\_directory\_iterator](../Topic/recursive_directory_iterator%20Class.md).  
  
## Синтаксис  
  
```  
class directory_entry;  
```  
  
## Заметки  
 Класс сохраняет объект типа [Класс path](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md).`path` может быть как [путем](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md), так и типом, производным от `path`. Он также сохраняет два значения [file\_type](../Topic/file_type%20Enumeration.md); одно из них представляет то, что известно о состоянии сохраненного имени файла, а другое представляет то, что известно о состоянии символьной ссылки имени файла.  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## assign  
  
```  
void assign(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Функция\-член назначает pval объекту mypath, stat объекту mystat и symstat объекту mysymstat.  
  
## directory\_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Установленные по умолчанию конструкторы работают корректно. Четвертый конструктор инициализирует mypath значением pval, mystat значением stat\_arg и mysymstat значением symstat\_arg.  
  
## operator\!\=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
  
```  
  
 Функция\-член возвращает значение \!\(\*this \=\= right\).  
  
## operator\=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
  
```  
  
 Операторы\-члены присваивания по умолчанию работают корректно.  
  
## operator\=\=  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 Функция\-член возвращает значение mypath \=\= right.mypath.  
  
## operator\<  
  
```  
  
bool operator<(const directory_entry& right) const noexcept;  
  
```  
  
 Функция\-член возвращает значение mypath \< right.mypath.  
  
## operator\<\=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 Функция\-член возвращает значение \!\(right \< \*this\).  
  
## operator\>  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 Функция\-член возвращает значение right \< \*this.  
  
## operator\>\=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
  
```  
  
 Функция\-член возвращает значение \!\(\*this \< right\)  
  
## operator const path\_type&  
  
```  
operator const path&() const; // retained  
```  
  
 Оператор\-член возвращает mypath.  
  
## path  
  
```  
const PFX path& path() const noexcept;  
```  
  
 Функция\-член возвращает значение mypath.  
  
## replace\_filename  
  
```  
void replace_filename(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 Функция\-член заменяет mypath значением mypath.parent\_path\(\) \/ pval, mystat значением stat\_arg и mysymstat значением symstat\_arg.  
  
## status  
  
```  
file_status status() const;  
file_status status(  
    error_code& ec) const noexcept;  
Otherwise, mystat = status(mypval).  
  
```  
  
 Обе функции\-члены возвращают mystat, возможно, сначала изменив его следующим образом:  
  
1.  если status\_known\(mystat\), не выполнять никаких действий.  
  
2.  В противном случае, если \!status\_known\(mysymstat\) && \!is\_symlink\(mysymstat\), то mystat \= mysymstat.  
  
## symlink\_status  
  
```  
file_status symlink_status() const;  
file_status symlink_status(  
    error_code& ec) const noexcept;  
```  
  
 Обе функции\-члены возвращают mysymstat, возможно, сначала изменив его следующим образом: если status\_known\(mysymstat\), не выполнять никаких действий. В противном случае mysymstat \= symlink\_status\(mypval\).  
  
## Требования  
 **Заголовок:** filesystem  
  
 **Пространство имен:** std::tr2::sys  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)