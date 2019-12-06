---
title: Класс path
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 0bc26bb04464c52ed08d46e6a12c12cae6909d6f
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898798"
---
# <a name="path-class"></a>Класс path

Класс **path** сохраняет объект типа `string_type`, который вызывается `myname` здесь для целей демонстрации, которые можно использовать в качестве пути. `string_type` является синонимом для `basic_string<value_type>`, где `value_type` является синонимом для **wchar_t** в Windows или **char** в POSIX.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class path;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[path](#path)|Создает документ `path`.|

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[const_iterator](#const_iterator)|Синоним для `iterator`.|
|[iterator](#iterator)|Итератор двунаправленной константы, обозначающий `path` компоненты `myname`.|
|[string_type](#string_type)|Тип является синонимом `basic_string<value_type>`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[append](#append)|Добавляет указанную последовательность к `mypath`, преобразует и вставляет preferred_separator по мере необходимости.|
|[assign](#assign)|Заменяет `mypath` указанной последовательностью, преобразованной при необходимости.|
|[begin](#begin)|Возвращает `path::iterator`, обозначающее первый элемент пути в пути, если он есть.|
|[c_str](#c_str)|Возвращает указатель на первый символ в `mypath`.|
|[clear](#clear)|Выполняет `mypath.clear()`.|
|[compare](#compare)|Возвращает значения сравнения.|
|[concat](#compare)|Добавляет указанную последовательность к `mypath`, преобразуется (но не вставляет разделитель) по мере необходимости.|
|[empty](#empty)|Возвращает значение `mypath.empty()`.|
|[end](#end)|Возвращает итератор конца последовательности типа `iterator`.|
|[продлен](#extension)|Возвращает суффикс `filename()`.|
|[filename](#filename)|Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.|
|[generic_string](#generic_string)|Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u16string](#generic_u16string)|Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u32string](#generic_u32string)|Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u8string](#generic_u8string)|Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_wstring](#generic_wstring)|Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[has_extension](#has_extension)|Возвращает значение `!extension().empty()`.|
|[has_filename](#has_filename)|Возвращает значение `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Возвращает значение `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Возвращает значение `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Возвращает значение `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Возвращает значение `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Возвращает значение `!root_path().empty()`.|
|[has_stem](#has_stem)|Возвращает значение `!stem().empty()`.|
|[is_absolute](#is_absolute)|Для Windows функция возвращает `has_root_name() && has_root_directory()`. Для POSIX функция возвращает `has_root_directory()`.|
|[is_relative](#is_relative)|Возвращает значение `!is_absolute()`.|
|[make_preferred](#make_preferred)|При необходимости преобразует каждый разделитель в preferred_separator.|
|[native](#native)|Возвращает значение `myname`.|
|[parent_path](#parent_path)|Возвращает компонент родительского пути `myname`.|
|[preferred_separator](#preferred_separator)|Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения. |
|[relative_path](#relative_path)|Возвращает компонент относительных путей `myname`. |
|[remove_filename](#remove_filename)|Удаляет имя файла.|
|[replace_extension](#replace_extension)|Заменяет расширение `myname`. |
|[replace_filename](#replace_filename)|Рреплацес имя файла.|
|[root_directory](#root_directory)|Возвращает компонент корневого каталога `myname`. |
|[root_name](#root_name)|Возвращает компонент корневого имени `myname`. |
|[root_path](#root_path)|Возвращает компонент корневого пути `myname`.|
|[слов](#stem)|Возвращает компонент `stem` `myname`.|
|[string](#string)|Преобразует последовательность, хранящуюся в `mypath`.|
|[swap](#swap)|Выполняет `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|Преобразует последовательность, сохраненную в `mypath`, в UTF-16 и возвращает ее, хранящуюся в объекте типа `u16string`.|
|[u32string](#u32string)|Преобразует последовательность, хранящуюся в `mypath`, в UTF-32 и возвращает ее, хранящуюся в объекте типа `u32string`.|
|[u8string](#u8string)|Преобразует последовательность, хранящуюся в `mypath`, в кодировку UTF-8 и возвращает ее, хранящуюся в объекте типа `u8string`.|
|[value_type](#value_type)|Тип описывает элементы пути, предпочитаемые в системе размещения.|
|[wstring](#wstring)|Преобразует последовательность, хранящуюся в `mypath`, в кодировку, предпочитаемую хост-системой для последовательности `wchar_t`, и возвращает ее, хранящуюся в объекте типа `wstring`.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[оператор=](#op_as)|Заменяет элементы пути копией другого пути.|
|[оператор+=](#op_add)|Различные выражения `concat`.|
|[оператор/=](#op_divide)|Различные выражения `append`.|
|[Оператор string_type](#op_string)|Возвращает значение `myname`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<FileSystem >

**Пространство имен:** std::experimental::filesystem

## <a name="append"></a>путь:: Append

Добавляет указанную последовательность к `mypath`, преобразует и вставляет `preferred_separator` по мере необходимости.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*исходный*\
Указанная последовательность.

*первый*\
Начало указанной последовательности.

*последние*\
Конец указанной последовательности.

## <a name="assign"></a>путь:: Assign

Заменяет `mypath` указанной последовательностью, преобразованной при необходимости.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*исходный*\
Указанная последовательность.

*первый*\
Начало указанной последовательности.

*последние*\
Конец указанной последовательности.

## <a name="begin"></a>путь:: начало

Возвращает `path::iterator`, обозначающее первый элемент пути в пути, если он есть.

```cpp
iterator begin() const;
```

## <a name="c_str"></a>путь:: c_str

Возвращает указатель на первый символ в `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>путь:: Clear

Выполняет `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="compare"></a>путь:: Compare

Первая функция возвращает `mypath.compare(pval.native())`. Вторая функция возвращает `mypath.compare(str)`. Третья функция возвращает `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Параметры

*pval*\
Путь для сравнения.

\ *str*
Сравниваемая строка.

\ *ptr*
Указатель на сравниваемый.

## <a name="concat"></a>путь:: Concat

Добавляет указанную последовательность к `mypath`, преобразуется (но не вставляет разделитель) по мере необходимости.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*исходный*\
Указанная последовательность.

*первый*\
Начало указанной последовательности.

*последние*\
Конец указанной последовательности.

## <a name="const_iterator"></a>путь:: const_iterator

Синоним для `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>путь:: Empty

Возвращает значение `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>путь:: конец

Возвращает итератор конца последовательности типа `iterator`.

```cpp
iterator end() const;
```

## <a name="extension"></a>путь:: расширение

Возвращает суффикс `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Заметки

Возвращает суффикс `filename() X` таким образом:

Если `X == path(".") || X == path("..")` или если `X` не содержит точку, суффикс будет пустым.

В противном случае суффикс начинается с самой крайней правой точки (и включает ее).

## <a name="filename"></a>путь:: имя файла

Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.

```cpp
path filename() const;
```

## <a name="generic_string"></a>путь:: generic_string

Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>путь:: generic_u16string

Возвращает значение `u16string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a>путь:: generic_u32string

Возвращает значение `u32string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a>путь:: generic_u8string

Возвращает значение `u8string()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a>путь:: generic_wstring

Возвращает значение `wstring()` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>путь:: has_extension

Возвращает значение `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>путь:: has_filename

Возвращает значение `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> path::has_parent_path

Возвращает значение `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> path::has_relative_path

Возвращает значение `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>путь:: has_root_directory

Возвращает значение `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>путь:: has_root_name

Возвращает значение `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>путь:: has_root_path

Возвращает значение `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>путь:: has_stem

Возвращает значение `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>путь:: is_absolute

Для Windows функция возвращает `has_root_name() && has_root_directory()`. Для POSIX функция возвращает `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>путь:: is_relative

Возвращает значение `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>путь:: итератор

Итератор двунаправленной константы, обозначающий компоненты пути `myname`.

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

### <a name="remarks"></a>Заметки

Класс описывает двунаправленный константный итератор, обозначающий `path` компоненты `myname` в последовательности:

1. корневое имя (при наличии);

1. корневой каталог (при наличии);

1. остальные элементы каталога родительского `path`, если они есть, заканчивая именем файла, если оно есть

Для `pval` объект типа `path`:

1. `path::iterator X = pval.begin()` обозначает первый элемент `path` в пути, если он есть.

1. `X == pval.end()` имеет значение true, когда `X` точки сразу после конца последовательности компонентов.

3. `*X` возвращает строку, соответствующую текущему компоненту

1. `++X` указывает на следующий компонент в последовательности, если он имеется.

1. `--X` указывает на предыдущий компонент в последовательности, если он имеется.

1. Изменение `myname` делает недействительными все итераторы, обозначающие элементы в `myname`.

## <a name="make_preferred"></a>путь:: make_preferred

При необходимости преобразует каждый разделитель в `preferred_separator`.

```cpp
path& make_preferred();
```

## <a name="native"></a>путь:: собственный

Возвращает значение `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a>путь:: оператор =

Заменяет элементы пути копией другого пути.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Параметры

*справа*\
[Путь](../standard-library/path-class.md) , который копируется в `path`.

*исходный*\
Исходный путь.

### <a name="remarks"></a>Заметки

Первый оператор члена копирует `right.myname` в `myname`. Второй оператор члена перемещает `right.myname` в `myname`. Третий оператор члена ведет себя так же, как `*this = path(source)`.

## <a name="op_add"></a>путь:: operator + =

Различные выражения `concat`.

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

*справа*\
Добавленный путь.

\ *str*
Добавленная строка.

\ *ptr*
Добавленный указатель.

*elem*\
Добавленный `value_type` или `Elem`.

*исходный*\
Добавленный источник.

### <a name="remarks"></a>Заметки

Функции-члены работают так же, как следующие соответствующие выражения:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a>путь:: оператор/=

Различные выражения `append`.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Параметры

*справа*\
Добавленный путь.

*исходный*\
Добавленный источник.

### <a name="remarks"></a>Заметки

Функции-члены работают так же, как следующие соответствующие выражения:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>путь:: оператор string_type

Возвращает значение `myname`.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> path::parent_path

Возвращает компонент родительского пути `myname`.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Заметки

Возвращает компонент родительского пути `myname`, в частности префикс `myname` после удаления `filename().native()` и всех непосредственно предшествующих разделителей каталогов. (То же, если `begin() != end()`, то это сочетание всех элементов в диапазоне `[begin(), --end())`, последовательно применяя `operator/=`.) Компонент может быть пустым.

## <a name="path"></a>путь::p ь

Конструирует `path` различными способами.

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

*справа*\
Путь, по которому сконструированный путь должен быть копией.

*исходный*\
Источник, для которого сконструированный путь должен быть копией.

*loc*\
Указанный языковой стандарт.

*первый*\
Позиция первого элемента, который следует скопировать.

*последние*\
Расположение последнего элемента для копирования.

### <a name="remarks"></a>Заметки

Конструкторы всех конструкций `myname` различными способами:

Для `path()` `myname()`.

Для `path(const path& right`) это `myname(right.myname)`.

Для `path(path&& right)` `myname(right.myname)`.

Для `template<class Source> path(const Source& source)` `myname(source)`.

Для `template<class Source> path(const Source& source, const locale& loc)` `myname(source)`, чтобы получить все необходимые аспекты codecvt из `loc`.

Для `template<class InIt> path(InIt first, InIt last)` `myname(first, last)`.

Для `template<class InIt> path(InIt first, InIt last, const locale& loc)` `myname(first, last)`, чтобы получить все необходимые аспекты codecvt из `loc`.

## <a name="preferred_separator"></a> path::preferred_separator

Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Заметки

Обратите внимание, что в большинстве контекстов в Windows в равной мере допускается использование соответствующего символа L"/".

## <a name="relative_path"></a> path::relative_path

Возвращает компонент относительных путей `myname`.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Заметки

Возвращает компонент относительных путей `myname`, в частности суффикс `myname`, после удаления `root_path().native()` и всех последующих избыточных разделителей каталогов. Компонент может быть пустым.

## <a name="remove_filename"></a>путь:: remove_filename

Удаляет имя файла.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> path::replace_extension

Заменяет расширение `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Параметры

*newext*\
Новое расширение.

### <a name="remarks"></a>Заметки

Сначала удаляет суффикс `extension().native()` из `myname`. Затем, если `!newext.empty() && newext[0] != dot` (где `dot` `*path(".").c_str()`), к `myname`добавляется `dot`. Затем *newext* добавляется к `myname`.

## <a name="replace_filename"></a>путь:: replace_filename

Заменяет имя файла.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Параметры

*pval*\
Путь к имени файла.

### <a name="remarks"></a>Заметки

Функция-член выполняет:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a>путь:: root_directory

Возвращает компонент корневого каталога `myname`.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Заметки

Компонент может быть пустым.

## <a name="root_name"></a>путь:: root_name

Возвращает компонент корневого имени `myname`.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Заметки

Компонент может быть пустым.

## <a name="root_path"></a> path::root_path

Возвращает компонент корневого пути `myname`.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Заметки

Возвращает компонент корневого пути `myname`, в частности `root_name()` / `root_directory`. Компонент может быть пустым.

## <a name="stem"></a>путь:: ресурс

Возвращает компонент `stem` `myname`.

```cpp
path stem() const;
```

### <a name="remarks"></a>Заметки

Возвращает `stem` компонент `myname`, в частности `filename().native()` с любым удаленным `extension().native()`ом. Компонент может быть пустым.

## <a name="string"></a>путь:: строка

Преобразует последовательность, хранящуюся в `mypath`.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Заметки

Первая функция-член (шаблон) преобразует последовательность, хранящуюся в `mypath` так же, как:

1. `string()` для `string<char, Traits, Alloc>()`

1. `wstring()` для `string<wchar_t, Traits, Alloc>()`

1. `u16string()` для `string<char16_t, Traits, Alloc>()`

1. `u32string()` для `string<char32_t, Traits, Alloc>()`

Вторая функция-член преобразует последовательность, хранящуюся в `mypath`, в кодировку, предпочитаемую хост-системой для последовательности **символов** , и возвращает ее, хранящуюся в объекте типа `string`.

## <a name="string_type"></a> path::string_type

Тип является синонимом `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>путь:: swap

Выполняет `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>путь:: u16string

Преобразует последовательность, сохраненную в `mypath`, в UTF-16 и возвращает ее, хранящуюся в объекте типа `u16string`.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>путь:: u32string

Преобразует последовательность, хранящуюся в `mypath`, в UTF-32 и возвращает ее, хранящуюся в объекте типа `u32string`.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>путь:: u8string

Преобразует последовательность, хранящуюся в `mypath`, в кодировку UTF-8 и возвращает ее, хранящуюся в объекте типа `u8string`.

```cpp
string u8string() const;
```

## <a name="value_type"></a>путь:: value_type

Тип описывает элементы `path`, которые используются операционной системой узла.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>путь:: wstring

Преобразует последовательность, хранящуюся в `mypath`, в кодировку, предпочитаемую хост-системой для последовательности **wchar_t** , и возвращает ее, хранящуюся в объекте типа `wstring`.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>См. также:

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
