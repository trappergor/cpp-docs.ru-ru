---
title: Функции &lt;filesystem&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 4dc53bff438830cfb8a7b0414c4e5cfb111f8f31
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691501"
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


## <a name="absolute"></a> Абсолютный

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Функция возвращает абсолютный путь, соответствующий *pval* относительно имени пути `base`:

1. Если `pval.has_root_name() && pval.has_root_directory()` функция возвращает *pval*.

1. Если `pval.has_root_name() && !pval.has_root_directory()` функция возвращает `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  /  `pval.relative_path()`.

1. Если `!pval.has_root_name() && pval.has_root_directory()` функция возвращает `absolute(base).root_name()`  /  *pval*.

1. Если `!pval.has_root_name() && !pval.has_root_directory()` функция возвращает `absolute(base)`  /  *pval*.

## <a name="begin"></a>  begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Обе функции возвращают *iter*.

## <a name="canonical"></a>  canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Все функции формируют абсолютный путь `pabs = absolute(pval, base)` (или `pabs = absolute(pval)` для перегрузки без параметра base), затем сокращают его до канонической формы следующую последовательность шагов:

1. Каждый компонент пути `X` для которого `is_symlink(X)` — **true** заменяется `read_symlink(X)`.

1. Каждый компонент пути `.` (точка обозначает текущий каталог, заданный предыдущими компонентами пути) удаляется.

1. Каждая пара компонентов пути `X` / `..` (точка точка является родительский каталог, заданный предыдущими компонентами пути) удаляется.

Затем функция возвращает `pabs`.

## <a name="copy"></a>  copy

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Функции все могут копировать или связывать один или несколько файлов в *из* для *для* под контролем *opts*, который рассматривается как `copy_options::none` для перегрузок без *opts* параметра. *opts* должен содержать максимум одну из:

- `skip_existing`, `overwrite_existing`или `update_existing`

- `copy_symlinks` или `skip_symlinks`

- `directories_only`, `create_symlinks`или `create_hard_links`

Функции сначала определяют значения file_status `f` для *из* и `t` для *для*:

- Если `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`, путем вызова `symlink_status`

- в противном случае — путем вызова `status`

- в противном случае передается ошибка.

Если `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, затем они передают ошибку (и больше ничего не делать).

В противном случае, если `is_symlink(f)` затем:

- Если `options & copy_options::skip_symlinks` не выполнять никаких действий.

- В противном случае, если `!exists(t)&& options & copy_options::copy_symlinks` затем `copy_symlink(from, to, opts)`.

- в противном случае передается ошибка.

В противном случае, если `is_regular_file(f)` затем:

- Если `opts & copy_options::directories_only` не выполнять никаких действий.

- В противном случае, если `opts & copy_options::create_symlinks` затем `create_symlink(to, from)`.

- В противном случае, если `opts & copy_options::create_hard_links` затем `create_hard_link(to, from)`.

- В противном случае, если `is_directory(f)` затем `copy_file(from, to`  /  `from.filename(), opts)`.

- В противном случае — значение `copy_file(from, to, opts)`.

В противном случае, если `is_directory(f) && (opts & copy_options::recursive || !opts)` затем:

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

## <a name="copy_file"></a>  copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Все функции могут копировать файл в *из* для *для* под контролем *opts*, который рассматривается как `copy_options::none` для перегрузок без *opts*  параметра. *opts* должен содержать максимум одну из `skip_existing`, `overwrite_existing`, или `update_existing`.

Если `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))` затем отчет как ошибку, что файл уже существует.

В противном случае, если `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))` попытаться скопировать содержимое и атрибуты файла *из* к файлу *для*. Передать как ошибку в случае сбоя попытки копирования.

Функции возвращают **true** Если попытка копирования выполняется и завершается успешно, в противном случае **false**.

## <a name="copy_symlink "></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Если `is_directory(from)` эта функция вызывает `create_directory_symlink(from, to)`. В противном случае он вызывает `create_symlink(from, to)`.

## <a name="create_directories"></a>  create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Для имени пути, например a\/b\/c, функция создает каталоги a и a\/b по мере необходимости, чтобы можно было создать каталог a\/b\/c при необходимости. Он возвращает **true** только в том случае, если фактически создает каталог *pval*.

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

Функция создает каталог *pval* при необходимости. Он возвращает значение true, только если фактически создает каталог *pval*, в этом случае она копирует разрешения из существующего файла *attr*, или использует `perms::all` для перегрузок без *attr*  параметра.

## <a name="create_directory_symlink "></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку как символьную ссылку на каталог *для*.

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку как жесткую ссылку на каталог или файл *для*.

## <a name="create_symlink "></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает *ссылку* как символьную ссылку на файл *для*.

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Функции без параметра *pval* возвращают путь к текущему каталогу. Остальные функции задают текущий каталог *pval*.

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

Первая функция возвращает `directory_iterator()` и вторая функция возвращает `recursive_directory_iterator()`

## <a name="equivalent"></a>  equivalent

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

Функции возвращают **true** только если *левой* и *правой* назначить одну и ту же сущность файловой системы.

## <a name="exists"></a>  exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `status_known && stat.type() != file_not_found`. Вторая и третья функции возвращают `exists(status(pval))`.

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Функции возвращают размер в байтах файла, назначенному с помощью *pval*, если `exists(pval) && is_regular_file(pval)` и размер файла может быть определено. В противном случае они передают ошибку и возвращают `uintmax_t(-1)`.

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

Функция возвращает число жестких связей для *pval*, или \-1, если произошла ошибка.

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

Функция возвращает значение хэша для `pval.native()`.

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::block`. Остальные функции возвращают `is_block_file(status(pval))`.

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::character`. Остальные функции возвращают `is_character_file(status(pval))`.

## <a name="is_directory "></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::directory`. Остальные функции возвращают `is_directory_file(status(pval))`.

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Если `is_directory(pval)` функция возвращает значение `directory_iterator(pval) == directory_iterator()`; в противном случае возвращается `file_size(pval) == 0`.

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::fifo`. Остальные функции возвращают `is_fifo(status(pval))`.

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::other`. Остальные функции возвращают `is_other(status(pval))`.

## <a name="s_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::regular`. Остальные функции возвращают `is_regular_file(status(pval))`.

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::socket`. Остальные функции возвращают `is_socket(status(pval))`.

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::symlink`. Остальные функции возвращают `is_symlink(status(pval))`.

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

Первые две функции возвращают время последнего изменения данных для *pval*, или `file_time_type(-1)` при возникновении ошибки. Последние две функции задают время последнего изменения данных для *pval* для *new_time*.

## <a name="permissions"></a>  permissions

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

Функции задают разрешения для пути, указанного *pval* для `mask & perms::mask` под контролем `perms & (perms::add_perms | perms::remove_perms)`. *Маска* должен содержать максимум одну из `perms::add_perms` и `perms::remove_perms`.

Если `mask & perms::add_perms` функции задают разрешения `status(pval).permissions() | mask & perms::mask`. В противном случае, если `mask & perms::remove_perms` функции задают разрешения `status(pval).permissions() & ~(mask & perms::mask)`. В противном случае функции задают разрешения `mask & perms::mask`.

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Функции передают ошибку и возвращают `path()` Если `!is_symlink(pval)`. В противном случае функции возвращают объект типа `path`, содержащий символьную ссылку.

## <a name="remove"></a>  remove

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Функции возвращают **true** только если `exists(symlink_status(pval))` и файл успешно удален. Удаляется сама символьная ссылка, а не указываемый ею файл.

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Если *pval* является каталогом, функции рекурсивно удаляют все записи каталога, а затем саму запись. В противном случае функции вызывают `remove`. Они возвращают число всех успешно удаленных элементов.

## <a name="rename"></a>  rename

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

Функции переименовывают *из* для *для*. Переименовывается сама символьная ссылка, а не указываемый ею файл.

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Функции изменяют размер файла таким образом, чтобы `file_size(pval) == size`

## <a name="space"></a>  space

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

Функция возвращает сведения о томе, указанном *pval*, в структуре типа `space_info`. Эта структура содержит `uintmax_t(-1)` для любого значения, которое невозможно определить.

## <a name="status"></a>  status

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

Функции возвращают состояние пути, тип файла и разрешения, связанные с *pval*. Сама символьная ссылка не проверяется, но проверяется указываемый ею файл.

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

Функция возвращает `stat.type() != file_type::none`

## <a name="swap"></a>  swap

```cpp
void swap(path& left, path& right) noexcept;
```

Функция меняет местами содержимое *левой* и *правой*.

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

Функции возвращают состояние символьной ссылки пути, тип файла и разрешения, связанные с *pval*. Функции работают так же, как `status(pval)` за исключением того, что проверяется сама Символьная ссылка, не указываемый ею файл.

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

Функции возвращают абсолютный путь, который учитывает (при необходимости) текущий каталог, связанный с его корневым именем. \(Для Posix функции возвращают `absolute(pval)`.\)

## <a name="temp_directory_path"></a>  temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

Функции возвращают путь к каталогу, подходящему для хранения временных файлов.

## <a name="u8path"></a>  u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

Первая функция ведет себя так же, как `path(source)` и вторая функция ведет себя так же, как `path(first, last)` за исключением того, что указанный источник в каждом случае рассматривается как последовательность элементов char в кодировке UTF-8, независимо от того, в файловой системе.
