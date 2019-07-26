---
title: Перечисления &lt;filesystem&gt;
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::filesystem::copy_options
- filesystem/std::experimental::filesystem::copy_options
- filesystem/std::filesystem::directory_options
- filesystem/std::experimental::filesystem::directory_options
- filesystem/std::filesystem::file_type
- filesystem/std::experimental::filesystem::file_type
- filesystem/std::filesystem::perms
- filesystem/std::experimental::filesystem::perms
ms.assetid: 0096c046-d101-464c-8259-b878a48280b0
ms.openlocfilehash: dfbcf65462f0bb7bc6ca44f43507efa7b753e7bc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457711"
---
# <a name="ltfilesystemgt-enumerations"></a>Перечисления &lt;filesystem&gt;

В этом разделе рассматриваются перечисления в заголовке файловой системы.

## <a name="requirements"></a>Требования

**Заголовок:** \<experimental/filesystem>

**Пространство имен:** std::experimental::filesystem

## <a name="copy_options"></a>  copy_options

Перечисление значений битовой маски, используемое с функциями [copy](filesystem-functions.md#copy) и [copy_file](filesystem-functions.md#copy_file), чтобы указать поведение.

### <a name="syntax"></a>Синтаксис

```cpp
enum class copy_options {
   none = 0,
   skip_existing = 1,
   overwrite_existing = 2,
   update_existing = 4,
   recursive = 8,
   copy_symlinks = 16,
   skip_symlinks = 32,
   directories_only = 64,
   create_symlinks = 128,
   create_hard_links = 256
};
```

### <a name="values"></a>Значения

|`Name`|Описание|
|------------|-----------------|
|`none`|Выполнять поведение по умолчанию для операции.|
|`skip_existing`|Не копировать, если файл уже существует, не сообщать об ошибке.|
|`overwrite_existing`|Перезаписать файл, если он уже существует.|
|`update_existing`|Перезаписать файл, если он уже существует и старше, чем его замена.|
|`recursive`|Копировать рекурсивно подкаталоги и их содержимое.|
|`copy_symlinks`|Копировать символические ссылки как символические ссылки, а не копирование файлов, на которые они указывают.|
|`skip_symlinks`|Игнорировать символические ссылки.|
|`directories_only`|Выполнять итерацию только по каталогам, файлы игнорировать.|
|`create_symlinks`|Создать символические ссылки вместо копирования файлов. В качестве исходного пути должен использоваться абсолютный путь, если назначением является текущий каталог.|
|`create_hard_links`|Создать жесткие связи вместо копирования файлов.|

## <a name="directory_options"></a> directory_options

Определяет, следует выполнить символьные ссылки на каталоги или их игнорировать.

### <a name="syntax"></a>Синтаксис

```cpp
enum class directory_options {
   none = 0,
   follow_directory_symlink
};
```

### <a name="values"></a>Значения

|name|Описание|
|----------|-----------------|
|`none`|Поведение по умолчанию: игнорировать символические ссылки на каталоги. Отказ в разрешении является ошибкой.|
|`follow_directory_symlink`|Символьные ссылки на каталоги можно рассматривать как фактические каталоги.|

## <a name="file_type"></a>  file_type

Перечисление для типов файлов. Поддерживаются значения Regular, Directory, not_found и Unknown.

### <a name="syntax"></a>Синтаксис

```cpp
enum class file_type {
    not_found = -1,
    none,
    regular,
    directory,
    symlink,
    block,
    character,
    fifo,
    socket,
    unknown
};
```

### <a name="values"></a>Значения

|Имя|Значение|Описание|
|----------|-----------|-----------------|
|`not_found`|-1|Представляет несуществующий файл.|
|`none`|0|Представляет файл, у которого нет атрибута типа. (Не поддерживается.)|
|`regular`|1|Представляет обычный файл на диске.|
|`directory`|2|Представляет каталог.|
|`symlink`|3|Представляет символьную ссылку. (Не поддерживается.)|
|`block`|4|Представляет блочный файл в системе UNIX. (Не поддерживается.)|
|`character`|5|Представляет символьный файл в системе UNIX. (Не поддерживается.)|
|`fifo`|6|Представляет файл FIFO в системе UNIX. (Не поддерживается.)|
|`socket`|7|Представляет сокет в системе UNIX. (Не поддерживается.)|
|`unknown`|8|Представляет файл, состояние которого невозможно определить.|

## <a name="perm_options"></a>perm_options

Включает значения `replace` `add` ,,и`nofollow`. `remove`

```cpp
enum class perm_options;
```

## <a name="perms"></a>  perms

Флаги разрешений файла. Поддерживаются значения: readonly (только для чтения) и all (все). Для файла с доступом "только для чтения" не установлен ни один из разрядов * _write. В противном случае установлен разряд `all` (0x0777).

### <a name="syntax"></a>Синтаксис

```cpp
enum class perms {// names for permissions
   none = 0,
   owner_read = 0400,  // S_IRUSR
   owner_write = 0200, // S_IWUSR
   owner_exec = 0100,  // S_IXUSR
   owner_all = 0700,   // S_IRWXU
   group_read = 040,   // S_IRGRP
   group_write = 020,  // S_IWGRP
   group_exec = 010,   // S_IXGRP
   group_all = 070,    // S_IRWXG
   others_read = 04,   // S_IROTH
   others_write = 02,  // S_IWOTH
   others_exec = 01,   // S_IXOTH
   others_all = 07,    // S_IRWXO
   all = 0777,
   set_uid = 04000,    // S_ISUID
   set_gid = 02000,    // S_ISGID
   sticky_bit = 01000, // S_ISVTX
   mask = 07777,
   unknown = 0xFFFF,
   add_perms = 0x10000,
   remove_perms = 0x20000,
   resolve_symlinks = 0x40000
};
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)
