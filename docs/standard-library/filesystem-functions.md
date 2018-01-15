---
title: "Функции &lt;filesystem&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
dev_langs: C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.workload: cplusplus
ms.openlocfilehash: edd850087249769fce9e96110dfa29ca37450b0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ltfilesystemgt-functions"></a>Функции &lt;filesystem&gt;
Эти свободные функции в заголовке [\<filesystem>](../standard-library/filesystem.md) выполняют операции изменения и запроса для путей, файлов, символических ссылок, каталогов и томов. Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
||||  
|-|-|-|  
|[absolute](#absolute)|[begin](#begin)|[canonical](#canonical)|
|[copy](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[end](#end)|[equivalent](#equivalent)|[exists](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[permissions](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[rename](#rename)|
|[resize_file](#resize_file)|[space](#space)|[status](#status)|
|[status_known](#status_known)|[swap](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|  


## <a name=""></a>  <a name="absolute"></a> absolute  
  
```  
path absolute(const path& pval, const path& base = current_path());
```  
  
 Функция возвращает абсолютный путь, соответствующий `pval`, относительно имени пути `base`:  
  
1.  Если pval.has_root_name() && pval.has_root_directory(), функция возвращает pval.  
  
2.  Если pval.has_root_name() && !pval.has_root_directory(), функция возвращает pval.root_name() / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path().  
  
3.  Если !pval.has_root_name() && pval.has_root_directory(), функция возвращает absolute(base).root_name() / pval.  
  
4.  Если !pval.has_root_name() && pval.has_root_directory(), функция возвращает absolute(base) / pval.  
  
## <a name="begin"></a>  begin  
  
```  
const directory_iterator& begin(const directory_iterator& iter) noexcept;  
const recursive_directory_iterator& 
    begin(const recursive_directory_iterator& iter) noexcept;  
```  
  
 Обе функции возвращают значение `iter`.  
  
## <a name="canonical"></a>  canonical  
  
```  
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```  
  
 Все функции формируют абсолютный путь pabs = absolute(pval, base) (или pabs = absolute(pval) для перегрузки без параметра base), затем сокращают его до канонической формы, выполняя следующую последовательность действий:  
  
1.  Каждый компонент пути X, для которого is_symlink(X) имеет значение true, заменяется read_symlink(X).  
  
2.  Каждый компонент пути . (точка обозначает текущий каталог, заданный предыдущими компонентами пути) удаляется.  
  
3.  Каждая пара компонентов пути X/ . (две точки обозначают родительский каталог, заданный предыдущими компонентами пути) удаляется.  
  
 Затем функция возвращает pabs.  
  
## <a name="copy"></a>  copy  
  
```  
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;  
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 Все функции могут копировать или связывать один или несколько файлов из `from` в `to` под управлением `opts`, что принимается как copy_options::none для перегрузок без параметра `opts`. Параметр `opts` должен содержать максимум одну из функций:  
  
-   skip_existing, overwrite_existing или update_existing;  
  
-   copy_symlinks или skip_symlinks;  
  
-   directories_only, create_symlinks или create_hard_links.  
  
 Функции сначала определяют значения file_status: f для `from` и t для `to`:  
  
-   если opts & (copy_options::create_symlinks &#124; copy_options::skip_symlinks), путем вызова symlink_status  
  
-   в противном случае путем вызова status;  
  
-   в противном случае передается ошибка.  
  
 Если !exists(f) &#124;&#124; equivalent(f, t) &#124;&#124; is_other(f) &#124;&#124; is_other(t) &#124;&#124; is_directory(f)&& is_regular_file(t), они передают ошибку (и не выполняют никаких других действий).  
  
 В противном случае, если is_symlink(f), то:  
  
-   если options & copy_options::skip_symlinks, не выполнять никаких действий;  
  
-   в противном случае, если !exists(t)&& options & copy_options::copy_symlinks, то copy_symlink(from, to, opts);  
  
-   в противном случае передается ошибка.  
  
 В противном случае, если is_regular_file(f), то:  
  
-   если opts & copy_options::directories_only, не выполнять никаких действий;  
  
-   в противном случае, если opts & copy_options::create_symlinks, то create_symlink(to, from);  
  
-   в противном случае, если opts & copy_options::create_hard_links, то create_hard_link(to, from);  
  
-   в противном случае, если is_directory(f), то copy_file(from, to / from.filename(), opts);  
  
-   в противном случае copy_file(from, to, opts).  
  
 В противном случае, если is_directory(f) && (opts & copy_options::recursive &#124;&#124; !opts), то:  
  
```cpp  
if (!exists(t))
{  // copy directory contents recursively  
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }

}
```  
  
 В противном случае не выполнять никаких действий.  
  
## <a name="opy_file"></a>  copy_file  
  
```  
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;  
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 Все функции могут копировать файл из `from` в `to` под управлением `opts`, что принимается как copy_options::none для перегрузок без параметра `opts`. Параметр `opts` должен содержать максимум одну из функций: skip_existing, overwrite_existing или update_existing.  
  
 Если exists\(to\) && \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\)\), передать ошибку "файл уже существует".  
  
 В противном случае, если \!exists\(to\) &#124;&#124; opts & copy_options::overwrite_existing &#124;&#124; opts & copy_options::update_existing&& last_write_time\(to\) \< last_write_time\(from\) &#124;&#124; \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options:update_existing\)\), попытаться скопировать содержимое и атрибуты файла from в файл to. Передать как ошибку в случае сбоя попытки копирования.  
  
 Функции возвращают значение true, если попытка копирования выполняется и завершается успешно; в противном случае — значение false.  
  
## <a name="copy_symlink "></a>  copy_symlink  
  
```  
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;  
```  
  
 Если is_directory\(from\), функция вызывает create_directory_symlink\(from, to\). В противном случае она вызывает create_symlink\(from, to\).  
  
## <a name="create_directories"></a>  create_directories  
  
```  
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;  
```  
  
 Для имени пути, например a\/b\/c, функция создает каталоги a и a\/b по мере необходимости, чтобы можно было создать каталог a\/b\/c при необходимости. Она возвращает значение true только в том случае, если фактически создает каталог `pval`.  
  
## <a name="create_directory"></a>  create_directory  
  
```  
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;  
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;  
```  
  
 Функция создает каталог `pval` при необходимости. Она возвращает значение true только в том случае, если фактически создает каталог `pval`. В этом случае она копирует разрешения из существующего параметра `attr` файла или использует perms::all для перегрузок без параметра `attr`.  
  
## <a name="create_directory_symlink "></a>  create_directory_symlink  
  
```  
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 Функция создает ссылку как символическую ссылку на каталог `to`.  
  
## <a name="create_hard_link"></a>  create_hard_link  
  
```  
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 Функция создает ссылку как жесткую ссылку на каталог или файл `to`.  
  
## <a name="create_symlink "></a>  create_symlink  
  
```  
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 Функция создает `link` как символическую ссылку на файл `to`.  
  
## <a name="current_path"></a>  current_path  
  
```  
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;  
```  
  
 Функции, для которых нет параметра `pval`, возвращают путь к текущему каталогу. Остальные функции задают `pval` для текущего каталога.  
  
## <a name="end"></a>  end  
  
```  
directory_iterator& end(const directory_iterator& iter) noexcept;  
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;  
```  
  
 Первая функция возвращает directory_iterator\(\), а вторая функция — recursive_directory_iterator\(\)  
  
## <a name="equivalent"></a>  equivalent  
  
```  
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;  
```  
  
 Функции возвращают значение true, только если части `left` и `right` обозначают одну и ту же сущность файловой системы.  
  
## <a name="exists"></a> существует  
  
```  
bool exists(file_status stat) noexcept;  
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает status_known && stat.type\(\) \!\= file_not_found. Вторая и третья функции возвращают exists\(status\(pval\)\).  
  
## <a name="file_size"></a>  file_size  
  
```  
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;  
```  
  
 Функции возвращают размер в байтах файла, заданного `pval`, если exists\(pval\) && is_regular_file\(pval\) и размер файла можно определить. В противном случае они передают ошибку и возвращают значение uintmax_t\(\-1\).  
  
## <a name="hard_link_count"></a>  hard_link_count  
  
```  
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;  
```  
  
 Функция возвращает число жестких связей для `pval` или значение \-1 при возникновении ошибки.  
  
## <a name="hash_value"></a>  hash_value  
  
```  
size_t hash_value(const path& pval) noexcept;  
```  
  
 Функция возвращает значение хэша для pval.native\(\).  
  
## <a name="is_block_file"></a>  is_block_file  
  
```  
bool is_block_file(file_status stat) noexcept;  
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::block. Остальные функции возвращают is_block_file\(status\(pval\)\).  
  
## <a name="is_character_file"></a>  is_character_file  
  
```   
bool is_character_file(file_status stat) noexcept;  
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::character. Остальные функции возвращают is_character_file\(status\(pval\)\).  
  
## <a name="is_directory "></a>  is_directory  
  
```   
bool is_directory(file_status stat) noexcept;  
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::directory. Остальные функции возвращают is_directory_file\(status\(pval\)\).  
  
## <a name="is_empty"></a>  is_empty  
  
```   
bool is_empty(file_status stat) noexcept;  
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;  
```  
  
 Если is_directory\(pval\), то функция возвращает directory_iterator\(pval\) \=\= directory_iterator\(\); в противном случае она возвращает file_size\(pval\) \=\= 0.  
  
## <a name="is_fifo"></a>  is_fifo  
  
```  
bool is_fifo(file_status stat) noexcept;  
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::fifo. Остальные функции возвращают is_fifo\(status\(pval\)\).  
  
## <a name="is_other"></a>  is_other  
  
```  
bool is_other(file_status stat) noexcept;  
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::other. Остальные функции возвращают is_other\(status\(pval\)\).  
  
## <a name="s_regular_file"></a>  is_regular_file  
  
```   
bool is_regular_file(file_status stat) noexcept;  
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::regular. Остальные функции возвращают is_regular_file\(status\(pval\)\).  
  
## <a name="is_socket"></a>  is_socket  
  
```   
bool is_socket(file_status stat) noexcept;  
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::socket. Остальные функции возвращают is_socket\(status\(pval\)\).  
  
## <a name="is_symlink"></a>  is_symlink  
  
```   
bool is_symlink(file_status stat) noexcept;  
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;  
```  
  
 Первая функция возвращает stat.type\(\) \=\= file_type::symlink. Остальные функции возвращают is_symlink\(status\(pval\)\).  
  
## <a name="last_write_time"></a>  last_write_time  
  
```   
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;  
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;  
```  
  
 Первые две функции возвращают время последнего изменения данных для `pval` или значение file_time_type\(\-1\) при возникновении ошибки. Последние две функции задают время последнего изменения данных для `pval` равным new_time.  
  
## <a name="permissions"></a>  permissions  
  
```  
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;  
```  
  
 Функции задают разрешения для пути, указанного `pval`, равным mask & perms::mask под управлением perms & \(perms::add_perms &#124; perms::remove_perms\). Параметр mask должен содержать максимум один из объектов perms::add_perms и perms::remove_perms.  
  
 Если mask & perms::add_perms, функция задает разрешения равными status\(pval\).permissions\(\) &#124; mask & perms::mask. В противном случае, если mask & perms::remove_perms, функция задает разрешения равными status\(pval\).permissions\(\) & ~\(mask & perms::mask\). В противном случае функции задают разрешения равными mask & perms::mask.  
  
## <a name="read_symlink"></a>  read_symlink  
  
```  
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```  
  
 Функции передают ошибку и возвращают path\(\) if \!is_symlink\(pval\). В противном случае функции возвращают объект типа `path`, содержащий символьную ссылку.  
  
## <a name="remove"></a>  remove  
  
```  
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;  
```  
  
 Функции возвращают значение true, только если exists\(symlink_status\(pval\)\), и файл успешно удален. Удаляется сама символьная ссылка, а не указываемый ею файл.  
  
## <a name="remove_all"></a>  remove_all  
  
```  
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;  
```  
  
 Если `pval` является каталогом, функции рекурсивно удаляют все записи каталога, а затем саму запись. В противном случае функции вызывают remove. Они возвращают число всех успешно удаленных элементов.  
  
## <a name="rename"></a>  rename  
  
```  
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;  
```  
  
 Функции переименовывают объект `from` в объект `to`. Переименовывается сама символьная ссылка, а не указываемый ею файл.  
  
## <a name="resize_file"></a>  resize_file  
  
```  
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;  
```  
  
 Функции изменяют размер файла так, чтобы file_size\(pval\) \=\= size  
  
## <a name="space"></a>  space  
  
```  
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;  
```  
  
 Функция возвращает сведения о томе, указанном `pval`, в структуре типа `space_info`. Структура содержит значение uintmax_t\(\-1\) для любого значения, которое невозможно определить.  
  
## <a name="status"></a>  status  
  
```  
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;  
```  
  
 Функции возвращают состояние пути, тип файла и разрешения, связанные с `pval`. Сама символьная ссылка не проверяется, но проверяется указываемый ею файл.  
  
## <a name="status_known"></a>  status_known  
  
```  
bool status_known(file_status stat) noexcept;  
```  
  
 Функция возвращает stat.type\(\) \!\= file_type::none  
  
## <a name="swap"></a>  swap  
  
```  
void swap(path& left, path& right) noexcept;  
```  
  
 Функция меняет местами содержимое `left` и `right`.  
  
## <a name="symlink_status"></a>  symlink_status  
  
```  
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;  
```  
  
 Функции возвращают состояние символьной ссылки пути, тип файла и разрешения, связанные с `pval`. Функции работают так же, как status\(pval\), за исключением того, что проверяется сама символьная ссылка, а не указываемый ею файл.  
  
## <a name="system_complete"></a>  system_complete  
  
```  
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```  
  
 Функции возвращают абсолютный путь, который учитывает (при необходимости) текущий каталог, связанный с его корневым именем. \(Для Posix функции возвращают absolute\(pval\).\)  
  
## <a name="temp_directory_path"></a>  temp_directory_path  
  
```  
path temp_directory_path();
path temp_directory_path(error_code& ec);
```  
  
 Функции возвращают путь к каталогу, подходящему для хранения временных файлов.  
  
## <a name="u8path"></a>  u8path  
  
```  
template <class Source>  
path u8path(const Source& source);

template <class InIt>  
path u8path(InIt first, InIt last);
```  
  
 Первая функция работает так же, как path(source), а вторая функция работает так же, как path(first, last), за исключением того, что указанный источник в каждом случае принимается как последовательность элементов char в кодировке UTF-8, независимо от файловой системы.


