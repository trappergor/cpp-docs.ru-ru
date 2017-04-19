---
title: "Класс directory_entry | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- FILESYSTEM/std::experimental::filesystem::directory_entry::directory_entry
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator=
- FILESYSTEM/std::experimental::filesystem::directory_entry::assign
- FILESYSTEM/std::experimental::filesystem::directory_entry::replace_filename
- FILESYSTEM/std::experimental::filesystem::directory_entry::path
- FILESYSTEM/std::experimental::filesystem::directory_entry::status
- FILESYSTEM/std::experimental::filesystem::directory_entry::symlink_status
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator==
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator!=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator<=
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>
- FILESYSTEM/std::experimental::filesystem::directory_entry::operator>=
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 2b28a11cc3b1c27029e7ac0ced52c9b898163b66
ms.lasthandoff: 02/24/2017

---
# <a name="directoryentry-class"></a>Класс directory_entry
Описывает объект, возвращаемый `*X`, где *X* — [directory_iterator](../standard-library/directory-iterator-class.md) или [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class directory_entry;  
```  
  
## <a name="remarks"></a>Примечания  
 Класс сохраняет объект типа [path](../standard-library/path-class.md). Сохраненный `path` может быть экземпляром [класса path](../standard-library/path-class.md) или типом, производным от `path`. Он также сохраняет два значения [file_type](../standard-library/filesystem-enumerations.md#filesystem__file_type); одно из них представляет то, что известно о состоянии сохраненного имени файла, а другое представляет то, что известно о состоянии символьной ссылки имени файла.  
  
 Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="assign"></a>assign  
  
```  
void assign(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Функция-член назначает pval объекту mypath, stat объекту mystat и symstat объекту mysymstat.  
  
## <a name="directoryentry"></a>directory_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Установленные по умолчанию конструкторы работают корректно. Четвертый конструктор инициализирует mypath значением pval, mystat значением stat_arg и mysymstat значением symstat_arg.  
  
## <a name="operator"></a>operator!=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение !(*this == right).  
  
## <a name="operator"></a>operator=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
```  
  
 Операторы-члены присваивания по умолчанию работают корректно.  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение mypath == right.mypath.  
  
## <a name="operator"></a>operator<  
  
```  
 
bool operator<(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение mypath < right.mypath.  
  
## <a name="operator"></a>operator<=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение !(right \< *this).  
  
## <a name="operator"></a>operator>  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение right \< *this.  
  
## <a name="operator"></a>operator>=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
```  
  
 Функция-член возвращает значение !(*this < right)  
  
## <a name="operator-const-pathtype"></a>operator const path_type&  
  
``` 
 operator const std::experimental::filesystem::path&() const; 
```  
  
 Оператор-член возвращает mypath.  
  
## <a name="path"></a>путем  
  
```  
const std::experimental::filesystem::path& path() const noexcept;  
```  
  
 Функция-член возвращает значение mypath.  
  
## <a name="replacefilename"></a>replace_filename  
  
```  
void replace_filename(
    const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 Функция-член заменяет mypath значением mypath.parent_path() / pval, mystat значением stat_arg и mysymstat значением symstat_arg.  
  
## <a name="status"></a>status  
  
```  
file_status status() const; 
file_status status(error_code& ec) const noexcept;  
```  
  
 Обе функции-члены возвращают mystat, возможно, сначала изменив его следующим образом:  
  
1.  если status_known(mystat), не выполнять никаких действий.  
  
2.  В противном случае, если !status_known(mysymstat) && !is_symlink(mysymstat), то mystat = mysymstat.  
  
## <a name="symlinkstatus"></a>symlink_status  
  
```  
file_status symlink_status() const; 
file_status symlink_status(error_code& ec) const noexcept;  
```  
  
 Обе функции-члены возвращают mysymstat, возможно, сначала изменив его следующим образом: если status_known(mysymstat), не выполнять никаких действий. В противном случае mysymstat = symlink_status(mypval).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<experimental/filesystem>  
  
 **Пространство имен:** std::experimental::filesystem  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)


