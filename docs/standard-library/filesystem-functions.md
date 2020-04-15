---
title: Функции &lt;filesystem&gt;
ms.date: 03/27/2019
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
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
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
ms.openlocfilehash: f1b48ed6f533d4ccb5f9ef5e6dbcbd6e5cc4f7a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332051"
---
# <a name="ltfilesystemgt-functions"></a>Функции &lt;filesystem&gt;

Эти бесплатные функции в [ \<файловой системе>](../standard-library/filesystem.md) заголовок делают операции изменения и запроса на путях, файлах, симссылках, каталогах и томах. Для получения дополнительной информации [File System Navigation (C++)](../standard-library/file-system-navigation.md)и примеров кода см.

## <a name="absolute"></a><a name="absolute"></a>Абсолютной

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Функция возвращает абсолютное имя пути, соответствующее *pval* относительно имени `base`пути:

1. Если `pval.has_root_name() && pval.has_root_directory()` функция возвращает *pval*.

1. Если `pval.has_root_name() && !pval.has_root_directory()` функция `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  / возвращается `pval.relative_path()`.

1. Если `!pval.has_root_name() && pval.has_root_directory()` функция `absolute(base).root_name()`  / возвращает *pval*.

1. Если `!pval.has_root_name() && !pval.has_root_directory()` функция `absolute(base)`  / возвращает *pval*.

## <a name="begin"></a><a name="begin"></a>Начать

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Обе функции возвращают *итер.*

## <a name="canonical"></a><a name="canonical"></a>Канонической

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Все функции образуют абсолютное `pabs = absolute(pval, base)` `pabs = absolute(pval)` имя пути (или для перегрузки без базового параметра), затем уменьшают его до канонической формы в следующей последовательности шагов:

1. Каждый `X` компонент `is_symlink(X)` пути, для `read_symlink(X)`которого **верно,** заменяется .

1. Каждый `.` компонент пути (точка — текущий каталог, установленный предыдущими компонентами пути) удаляется.

1. Каждая пара `X` / `..` компонентов пути (точка-точка является родительским каталогом, установленным предыдущими компонентами пути) удаляется.

Функция затем `pabs`возвращается .

## <a name="copy"></a><a name="copy"></a>Копировать

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Функции все, возможно, копировать или связать один или *opts*несколько файлов на `copy_options::none` *из-под* контроля выбирает , который берется как для перегрузок без *выбора* параметра. *to* *выборы* должны содержать не более одного из:

- `skip_existing`, `overwrite_existing` или `update_existing`

- `copy_symlinks` или `skip_symlinks`

- `directories_only`, `create_symlinks` или `create_hard_links`

Функции сначала определяют file_status `f` значения `t` для *от* и *для:*

- если, `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`позвонив`symlink_status`

- в противном случае, позвонив`status`

- в противном случае передается ошибка.

Если, `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`они затем сообщить об ошибке (и ничего не делать).

В противном случае, если `is_symlink(f)` тогда:

- Если, `options & copy_options::skip_symlinks`то ничего не делать.

- В противном случае, если `!exists(t)&& options & copy_options::copy_symlinks`, то `copy_symlink(from, to, opts)`.

- В противном случае сообщите об ошибке.

В противном случае, если, `is_regular_file(f)`то:

- Если, `opts & copy_options::directories_only`то ничего не делать.

- В противном случае, если `opts & copy_options::create_symlinks`, то `create_symlink(to, from)`.

- В противном случае, если `opts & copy_options::create_hard_links`, то `create_hard_link(to, from)`.

- В противном `copy_file(from, to`  /  `from.filename(), opts)`случае, если `is_directory(f)`, то .

- В противном случае — `copy_file(from, to, opts)`.

В противном случае, если, `is_directory(f) && (opts & copy_options::recursive || !opts)`то:

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

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Функции все, возможно, копировать файл *от* *до* под контролем *выбирает*, который берется как `copy_options::none` для перегрузок без *каких-либо выбирает* параметр. *выбирает* должны содержать в `skip_existing`большинстве один из , `overwrite_existing`или `update_existing`.

Если `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`, то сообщить об ошибке, что файл уже существует.

В противном случае, если `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`, затем попытаться скопировать содержимое и атрибуты файла *из* файла *в*. Передать как ошибку в случае сбоя попытки копирования.

Функции возвращаются **верно,** если копия предпринята и успешно, в противном случае **ложное.**

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Если `is_directory(from)`функция вызывает `create_directory_symlink(from, to)`. В противном `create_symlink(from, to)`случае, он вызывает .

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Для такого имени\/пути, как b\/c, функция\/создает каталоги a и b\/по\/мере необходимости, чтобы она мог создать каталог b c по мере необходимости. Он возвращается **верно,** только если он на самом деле создает каталог *pval*.

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

Функция создает каталог *pval* по мере необходимости. Он возвращается верно только в том случае, если он на самом деле создает каталог *pval*, и в этом случае он копирует разрешения из существующего файла *attr*, или использует `perms::all` для перегрузок без параметра *attr.*

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку в виде симлсвязи с *каталогом.*

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает ссылку в виде жесткой ссылки на каталог или *файл.*

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Функция создает *ссылку* как симлинк с *файлом.*

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Функции без параметра *pval* возвращают имя пути для текущего каталога. Остальные функции устанавливают текущий каталог на *pval*.

## <a name="end"></a><a name="end"></a>Конец

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

Первая функция `directory_iterator()` возвращается, а вторая -`recursive_directory_iterator()`

## <a name="equivalent"></a><a name="equivalent"></a>Эквивалентные

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

Функции возвращаются **верно** только в том случае, если *левый* и *правый* выбирают одну и ту же сущность файловой системы.

## <a name="exists"></a><a name="exists"></a>Существует

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `status_known && stat.type() != file_not_found`. Возвращаются `exists(status(pval))`вторая и третья функции.

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Функции возвращают размер в байтах файла, `exists(pval) && is_regular_file(pval)` выбранного *pval,* если и размер файла может быть определен. В противном случае `uintmax_t(-1)`они сообщают об ошибке и возвращаются.

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

Функция возвращает количество жестких ссылок для \- *pval,* или 1, если происходит ошибка.

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

Функция возвращает хэш-значение `pval.native()`для .

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::block`. Остальные функции `is_block_file(status(pval))`возвращаются.

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::character`. Остальные функции `is_character_file(status(pval))`возвращаются.

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::directory`. Остальные функции `is_directory_file(status(pval))`возвращаются.

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Если, `is_directory(pval)`то функция `directory_iterator(pval) == directory_iterator()`возвращается ; в противном случае он возвращается `file_size(pval) == 0`.

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::fifo`. Остальные функции `is_fifo(status(pval))`возвращаются.

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::other`. Остальные функции `is_other(status(pval))`возвращаются.

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::regular`. Остальные функции `is_regular_file(status(pval))`возвращаются.

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::socket`. Остальные функции `is_socket(status(pval))`возвращаются.

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

Первая функция возвращает `stat.type() == file_type::symlink`. Остальные функции `is_symlink(status(pval))`возвращаются.

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

Первые две функции возвращают время последней модификации `file_time_type(-1)` данных для *pval*или если происходит ошибка. Последние две функции устанавливают время последней модификации данных для *pval* *new_time.*

## <a name="permissions"></a><a name="permissions"></a>Разрешения

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

Функции устанавливают разрешения на имя пути, выбранное `perms & (perms::add_perms | perms::remove_perms)` *pval,* чтобы `mask & perms::mask` под контролем . *маска* должна содержать не `perms::add_perms` `perms::remove_perms`более одного из и .

Если `mask & perms::add_perms`функции устанавливают разрешения `status(pval).permissions() | mask & perms::mask`на. В противном случае, если `mask & perms::remove_perms`функции устанавливают разрешения на. `status(pval).permissions() & ~(mask & perms::mask)` В противном случае функции `mask & perms::mask`устанавливают разрешения на.

## <a name="proximate"></a><a name="proximate"></a>Экспресс

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a><a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Функции сообщают об `path()` ошибке и возвращаются, если `!is_symlink(pval)`. В противном случае функции возвращают объект типа `path`, содержащий символьную ссылку.

## <a name="relative"></a><a name="relative"></a>Относительно

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>Удалить

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Функции **true** возвращаются `exists(symlink_status(pval))` верно только в том случае, если файл успешно удален. Симлинк сам удаляется, а не файл, который он выбирает.

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Если *pval* является каталогом, функции повторяются удалить все записи каталога, то сама запись. В противном `remove`случае функции вызывают . Они возвращают число всех успешно удаленных элементов.

## <a name="rename"></a><a name="rename"></a>Переименовать

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

Функции переименовывать *от* *к*. Симлинк сам переименован, а не файл, который он выбирает.

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Функции изменяют размер файла таким образом, чтобы`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>Пространство

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

Функция возвращает информацию об объеме, выбранном *pval,* в структуре типа. `space_info` Структура содержит `uintmax_t(-1)` для любого значения, которое не может быть определено.

## <a name="status"></a><a name="status"></a>Статус

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

Функции возвращают статус имени пути, тип файла и разрешения, связанные с *pval.* Симлинк сам по себе не тестируется, но файл, который он выбирает.

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

Функция возвращается`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>Своп

```cpp
void swap(path& left, path& right) noexcept;
```

Функция обменивается содержимым *левого* и *правого.*

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

Функции возвращают статус симlink—ссылки на имя пути, тип файла и разрешения, связанные с *pval.* Функции ведут себя `status(pval)` так же, как и симлинк сам тестируется, а не файл, который он выбирает.

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

Функции возвращают абсолютный путь, который учитывает (при необходимости) текущий каталог, связанный с его корневым именем. \(Для POSIX, функции возвращаются. `absolute(pval)`\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

Функции возвращают путь к каталогу, подходящему для хранения временных файлов.

## <a name="u8path"></a><a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

Первая функция ведет себя `path(source)` так же, как и вторая функция, `path(first, last)` за исключением того, что выбранный источник в каждом случае воспринимается как последовательность элементов, кодированных как UTF-8, независимо от файловой системы.

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
