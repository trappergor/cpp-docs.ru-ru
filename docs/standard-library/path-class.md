---
title: Класс path
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 669dfd2c8cd8576ebfb6684bab7cf63cdd51babc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372110"
---
# <a name="path-class"></a>Класс path

Класс **пути** хранит объект `string_type`типа, `myname` называемый здесь для целей экспозиции, пригодный для использования в качестве имени пути. `string_type`является `basic_string<value_type>`синонимом , где `value_type` является синонимом для **wchar_t** на Windows или **символ** на POSIX.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class path;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[Путь](#path)|Создает документ `path`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_iterator](#const_iterator)|Синоним для `iterator`.|
|[Итератор](#iterator)|Двунаправленный постоянный итератор, `path` который `myname`обозначает компоненты .|
|[string_type](#string_type)|Тип является синонимом `basic_string<value_type>`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[append](#append)|Придатки заданной последовательности к, `mypath`преобразованию и вставке preferred_separator по мере необходимости.|
|[Назначить](#assign)|`mypath` Заменяется указанной последовательностью, преобразованной по мере необходимости.|
|[Начать](#begin)|Возвращает `path::iterator` обозначение первого элемента пути в названии пути, если он присутствует.|
|[C_str](#c_str)|Возвращает указатель первому персонажу в `mypath`.|
|[Ясно](#clear)|Выполняет `mypath.clear()`.|
|[Сравнить](#compare)|Возвращает значения сравнения.|
|[Concat](#compare)|Придатит указанную последовательность к `mypath`преобразованной (но не вставляющей сепаратор) по мере необходимости.|
|[Пустой](#empty)|Возвращает `mypath.empty()`.|
|[end](#end)|Возвращает итератор типа `iterator`в конце последовательности.|
|[Расширение](#extension)|Возвращает суффикс `filename()`.|
|[Имени файла](#filename)|Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.|
|[generic_string](#generic_string)|Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u16string](#generic_u16string)|Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u32string](#generic_u32string)|Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u8string](#generic_u8string)|Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_wstring](#generic_wstring)|Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[has_extension](#has_extension)|Возвращает `!extension().empty()`.|
|[has_filename](#has_filename)|Возвращает `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Возвращает `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Возвращает `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Возвращает `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Возвращает `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Возвращает `!root_path().empty()`.|
|[has_stem](#has_stem)|Возвращает `!stem().empty()`.|
|[is_absolute](#is_absolute)|Для Windows функция `has_root_name() && has_root_directory()`возвращается. Для POSIX функция `has_root_directory()`возвращается.|
|[is_relative](#is_relative)|Возвращает `!is_absolute()`.|
|[make_preferred](#make_preferred)|Преобразует каждый сепаратор в preferred_separator по мере необходимости.|
|[Родной](#native)|Возвращает `myname`.|
|[parent_path](#parent_path)|Возвращает компонент родительского `myname`пути .|
|[preferred_separator](#preferred_separator)|Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения. |
|[relative_path](#relative_path)|Возвращает компонент относительного `myname`пути . |
|[remove_filename](#remove_filename)|Удаляет имя файла.|
|[replace_extension](#replace_extension)|Заменяет расширение `myname`. |
|[replace_filename](#replace_filename)|RЗаменяет имя файла.|
|[root_directory](#root_directory)|Возвращает компонент корневого `myname`каталога . |
|[root_name](#root_name)|Возвращает компонент корневого `myname`имени . |
|[root_path](#root_path)|Возвращает компонент корневого `myname`пути .|
|[stem](#stem)|Возвращает `stem` компонент `myname`.|
|[строка](#string)|Преобразует последовательность, `mypath`хранящуюся в .|
|[Своп](#swap)|Выполняет `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|Преобразует последовательность, `mypath` хранящуюся в UTF-16, `u16string`и возвращает ее в объект типа.|
|[u32string](#u32string)|Преобразует последовательность, `mypath` хранящуюся в UTF-32, `u32string`и возвращает ее в объект типа.|
|[u8string](#u8string)|Преобразует последовательность, `mypath` хранящуюся в UTF-8, `u8string`и возвращает ее в объект типа.|
|[Value_type](#value_type)|Тип описывает элементы пути, предпочитаемые в системе размещения.|
|[wstring](#wstring)|Преобразует последовательность, `mypath` хранящуюся в кодировании, `wchar_t` пользующееся поддержкой системы `wstring`узла, для последовательности и возвращает ее в объект типа.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_as)|Заменяет элементы пути копией другого пути.|
|[оператора](#op_add)|Различные `concat` выражения.|
|[оператор/я](#op_divide)|Различные `append` выражения.|
|[оператор string_type](#op_string)|Возвращает `myname`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<> файловой системы

**Пространство имен:** std::experimental::filesystem

## <a name="pathappend"></a><a name="append"></a>путь::приложение

Придатки заданной последовательности к, `mypath`преобразованию и вставке `preferred_separator` по мере необходимости.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*Источник*\
Указанная последовательность.

*Первый*\
Начало заданной последовательности.

*Последний*\
Конец указанной последовательности.

## <a name="pathassign"></a><a name="assign"></a>путь::назначить

`mypath` Заменяется указанной последовательностью, преобразованной по мере необходимости.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*Источник*\
Указанная последовательность.

*Первый*\
Начало заданной последовательности.

*Последний*\
Конец указанной последовательности.

## <a name="pathbegin"></a><a name="begin"></a>путь::начало

Возвращает `path::iterator` обозначение первого элемента пути в названии пути, если он присутствует.

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a>путь::c_str

Возвращает указатель первому персонажу в `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a>путь::ясно

Выполняет `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a>путь::сравнение

Первая функция возвращает `mypath.compare(pval.native())`. Вторая функция возвращает `mypath.compare(str)`. Третья функция `mypath.compare(ptr)`возвращается.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь для сравнения.

*Ул*\
Строка для сравнения.

*Ptr*\
Указатель для сравнения.

## <a name="pathconcat"></a><a name="concat"></a>путь::concat

Придатит указанную последовательность к `mypath`преобразованной (но не вставляющей сепаратор) по мере необходимости.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*Источник*\
Указанная последовательность.

*Первый*\
Начало заданной последовательности.

*Последний*\
Конец указанной последовательности.

## <a name="pathconst_iterator"></a><a name="const_iterator"></a>путь::const_iterator

Синоним для `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a>путь::пустой

Возвращает `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a>путь::конец

Возвращает итератор типа `iterator`в конце последовательности.

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a>путь::расширение

Возвращает суффикс `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Remarks

Возвращает суффикс `filename() X` такого, что:

Если `X == path(".") || X == path("..")` или `X` если не содержит точки, суффикс пуст.

В противном случае суффикс начинается с самой крайней правой точки (и включает ее).

## <a name="pathfilename"></a><a name="filename"></a>путь:filename

Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a>путь::generic_string

Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a>путь::generic_u16string

Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a>путь::generic_u32string

Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a>путь::generic_u8string

Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a>путь::generic_wstring

Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a>путь::has_extension

Возвращает `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a>путь::has_filename

Возвращает `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a>путь::has_parent_path

Возвращает `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a>путь::has_relative_path

Возвращает `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a>путь::has_root_directory

Возвращает `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a>путь::has_root_name

Возвращает `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a>путь::has_root_path

Возвращает `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a>путь::has_stem

Возвращает `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a>путь::is_absolute

Для Windows функция `has_root_name() && has_root_directory()`возвращается. Для POSIX функция `has_root_directory()`возвращается.

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a>путь::is_relative

Возвращает `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a>путь::iterator

Двунаправленный постоянный итератор, который `myname`обозначает компоненты пути .

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>Remarks

Класс описывает двунаправленный постоянный итератор, который обозначает `path` компоненты `myname` последовательности:

1. корневое имя (при наличии);

1. корневой каталог (при наличии);

1. остальные элементы каталога `path`родительского , если присутствует, заканчивая имя файла, если присутствует

Для `pval` объекта типа: `path`

1. `path::iterator X = pval.begin()`обозначает первый `path` элемент в названии пути, если присутствует.

1. `X == pval.end()`верно, `X` когда точки только мимо конца последовательности компонентов.

1. `*X`возвращает строку, которая соответствует текущему компоненту

1. `++X` указывает на следующий компонент в последовательности, если он имеется.

1. `--X` указывает на предыдущий компонент в последовательности, если он имеется.

1. `myname` Изменение недействительными все итераторы, обозначающие элементы в `myname`.

## <a name="pathmake_preferred"></a><a name="make_preferred"></a>путь::make_preferred

Преобразует каждый сепаратор `preferred_separator` в по мере необходимости.

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a>путь::родной

Возвращает `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a>путь::оператор

Заменяет элементы пути копией другого пути.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Параметры

*Правильно*\
[Путь,](../standard-library/path-class.md) скопированный `path`в .

*Источник*\
Путь источника.

### <a name="remarks"></a>Remarks

Первый оператор-член `right.myname` `myname`копирует . Второй оператор-член `right.myname` `myname`переходит к . Третий оператор-член ведет себя `*this = path(source)`так же, как .

## <a name="pathoperator"></a><a name="op_add"></a>путь::оператор

Различные `concat` выражения.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Добавленный путь.

*Ул*\
Добавленная строка.

*Ptr*\
Добавленный указатель.

*Elem*\
Добавлено `value_type` `Elem`или .

*Источник*\
Добавленный источник.

### <a name="remarks"></a>Remarks

Функции-члены работают так же, как следующие соответствующие выражения:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="pathoperator"></a><a name="op_divide"></a>путь:оператор/з.

Различные `append` выражения.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Добавленный путь.

*Источник*\
Добавленный источник.

### <a name="remarks"></a>Remarks

Функции-члены работают так же, как следующие соответствующие выражения:

1. `append(right);`

1. `append(source);`

## <a name="pathoperator-string_type"></a><a name="op_string"></a>путь::оператор string_type

Возвращает `myname`.

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a>путь::pарентаж-пати

Возвращает компонент родительского `myname`пути .

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Remarks

Возвращает компонент родительского `myname`пути, в `myname` частности `filename().native()` префикс после удаления и любые непосредственно предшествующие сепараторы каталога. (Равно, если, `begin() != end()`это объединение всех элементов `[begin(), --end())` в диапазоне `operator/=`последовательно применения .) Компонент может быть пустым.

## <a name="pathpath"></a><a name="path"></a>путь::p

Строит по-разному. `path`

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Путь, по которому построен путь должен быть копией.

*Источник*\
Источником, из которого построен путь должен быть копией.

*Loc*\
Указанная местность.

*Первый*\
Позиция первого элемента, который следует скопировать.

*Последний*\
Положение последнего элемента, подаваемый к копированию.

### <a name="remarks"></a>Remarks

Все конструкторы строят `myname` по-разному:

Ибо `path()` `myname()`это .

Для `path(const path& right`) `myname(right.myname)`это .

Ибо `path(path&& right)` `myname(right.myname)`это .

Ибо `template<class Source> path(const Source& source)` `myname(source)`это .

Ибо `template<class Source> path(const Source& source, const locale& loc)` `myname(source)`это, получение любых необходимых кодеквт-граней от `loc`.

Ибо `template<class InIt> path(InIt first, InIt last)` `myname(first, last)`это .

Ибо `template<class InIt> path(InIt first, InIt last, const locale& loc)` `myname(first, last)`это, получение любых необходимых кодеквт-граней от `loc`.

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a>путь::pупомянутый сепаратор

Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Remarks

Обратите внимание, что в большинстве контекстов в Windows в равной мере допускается использование соответствующего символа L"/".

## <a name="pathrelative_path"></a><a name="relative_path"></a>путь::relative_path

Возвращает компонент относительного `myname`пути .

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Remarks

Возвращает относительный `myname`компонент пути, в `myname` частности `root_path().native()` суффикс после удаления и любые сразу последующие избыточные сепараторы каталога. Компонент может быть пустым.

## <a name="pathremove_filename"></a><a name="remove_filename"></a>путь::remove_filename

Удаляет имя файла.

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a>путь::replace_extension

Заменяет расширение `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Параметры

*newext*\
Новое расширение.

### <a name="remarks"></a>Remarks

Первый удаляет суффикс `extension().native()` из `myname`. Затем, `!newext.empty() && newext[0] != dot` если `dot` `*path(".").c_str()`(где `dot` есть), `myname`то придатилось к . Затем *newext* прикладной к `myname`.

## <a name="pathreplace_filename"></a><a name="replace_filename"></a>путь::replace_filename

Заменяет имя файла.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Параметры

*Pval*\
Путь имени файла.

### <a name="remarks"></a>Remarks

Функция-член выполняет:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathroot_directory"></a><a name="root_directory"></a>путь::root_directory

Возвращает компонент корневого `myname`каталога .

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Remarks

Компонент может быть пустым.

## <a name="pathroot_name"></a><a name="root_name"></a>путь::root_name

Возвращает компонент корневого `myname`имени .

```cpp
path root_name() const;
```

### <a name="remarks"></a>Remarks

Компонент может быть пустым.

## <a name="pathroot_path"></a><a name="root_path"></a>путь::root_path

Возвращает компонент корневого `myname`пути .

```cpp
path root_path() const;
```

### <a name="remarks"></a>Remarks

Возвращает компонент корневого `root_name()`  /  `root_directory`пути, в частности `myname`. Компонент может быть пустым.

## <a name="pathstem"></a><a name="stem"></a>путь::stem

Возвращает `stem` компонент `myname`.

```cpp
path stem() const;
```

### <a name="remarks"></a>Remarks

Возвращает `stem` компонент, `myname`в `filename().native()` частности `extension().native()` с любым задним удалены. Компонент может быть пустым.

## <a name="pathstring"></a><a name="string"></a>путь::строка

Преобразует последовательность, `mypath`хранящуюся в .

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Remarks

Функция первого (шаблона) члена преобразует `mypath` последовательность, хранящуюся так же, как:

1. `string()` для `string<char, Traits, Alloc>()`;

1. `wstring()` для `string<wchar_t, Traits, Alloc>()`;

1. `u16string()` для `string<char16_t, Traits, Alloc>()`;

1. `u32string()` для `string<char32_t, Traits, Alloc>()`;

Функция второго члена преобразует последовательность, хранящуюся в `mypath` кодировании, пользующееся поддержкой системы узла, для последовательности **символа** и возвращает ее в объект типа. `string`

## <a name="pathstring_type"></a><a name="string_type"></a>путь::string_type

Тип является синонимом `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a>путь::swap

Выполняет `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a>путь::u16string

Преобразует последовательность, `mypath` хранящуюся в UTF-16, `u16string`и возвращает ее в объект типа.

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a>путь::u32string

Преобразует последовательность, `mypath` хранящуюся в UTF-32, `u32string`и возвращает ее в объект типа.

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a>путь::u8string

Преобразует последовательность, `mypath` хранящуюся в UTF-8, `u8string`и возвращает ее в объект типа.

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a>путь::value_type

Тип описывает `path` элементы, пользующиеся поддержкой операционной системы хоста.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a>путь::wstring

Преобразует последовательность, `mypath` хранящуюся в кодировании, пользующееся поддержкой системы хоста для **wchar_t** последовательности и возвращает ее в объект типа. `wstring`

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
