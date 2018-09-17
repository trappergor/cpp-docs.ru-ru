---
title: Класс Path | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::path
dev_langs:
- C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8fa524d0c41d437575a61ff4e4456fd9933404
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725313"
---
# <a name="path-class"></a>Класс path

**Путь** класс сохраняет объект типа `string_type`, который называется `myname` здесь в целях надстройках, подходящий для использования в качестве пути. `string_type` является синонимом для `basic_string<value_type>`, где `value_type` является синонимом **char** в группе Windows или **wchar_t** в Posix.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class path;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[path](#path)|Создает документ `path`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_iterator](#const_iterator)|Синоним для `iterator`.|
|[iterator](#iterator)|Двунаправленный постоянный итератор, указывающий `path` компоненты `myname`.|
|[string_type](#string_type)|Тип является синонимом `basic_string<value_type>`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[append](#append)|Добавляет указанную последовательность в `mypath`и вставляют preferred_separator при необходимости.|
|[assign](#assign)|Заменяет `mypath` с указанной последовательностью, преобразованной при необходимости.|
|[begin](#begin)|Возвращает `path::iterator` обозначающий первый элемент пути в имени пути, если он имеется.|
|[c_str](#c_str)|Возвращает указатель на первый символ в `mypath`.|
|[clear](#clear)|Выполняет `mypath.clear()`.|
|[compare](#compare)|Возвращает значения для сравнения.|
|[Concat](#compare)|Добавляет к указанной последовательности `mypath`, преобразовать (но не вставляют разделитель) при необходимости.|
|[empty](#empty)|Возвращает `mypath.empty()`.|
|[end](#end)|Возвращает итератор конец последовательности типа `iterator`.|
|[Расширение](#extension)|Возвращает суффикс `filename()`.|
|[filename](#filename)|Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.|
|[generic_string](#generic_string)|Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.|
|[generic_u16string](#generic_u16string)|Возвращает `u16string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.|
|[generic_u32string](#generic_u32string)|Возвращает `u32string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.|
|[generic_u8string](#generic_u8string)|Возвращает `u8string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.|
|[generic_wstring](#generic_wstring)|Возвращает `wstring()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.|
|[has_extension](#has_extension)|Возвращает `!extension().empty()`.|
|[has_filename](#has_filename)|Возвращает `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Возвращает `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Возвращает `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Возвращает `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Возвращает `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Возвращает `!root_path().empty()`.|
|[has_stem](#has_stem)|Возвращает `!stem().empty()`.|
|[is_absolute](#is_absolute)|Для Windows, функция возвращает `has_root_name() && has_root_directory()`. Для Posix функция возвращает `has_root_directory()`.|
|[is_relative](#is_relative)|Возвращает `!is_absolute()`.|
|[make_preferred](#make_preferred)|Преобразует каждый разделитель в preferred_separator при необходимости.|
|[native](#native)|Возвращает `myname`.|
|[parent_path](#parent_path)|Возвращает родительский компонент пути `myname`.|
|[preferred_separator при](#preferred_separator)|Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения. |
|[relative_path](#relative_path)|Возвращает компонент относительного пути `myname`. |
|[remove_filename](#remove_filename)|Удаляет имя файла.|
|[replace_extension](#replace_extension)|Заменяет расширение `myname`. |
|[replace_filename](#replace_filename)|RReplaces имя файла.|
|[root_directory](#root_directory)|Возвращает компонент корневого каталога `myname`. |
|[root_name](#root_name)|Возвращает компонент корневого имени `myname`. |
|[путь_к_корню](#root_path)|Возвращает компонент корневого пути `myname`.|
|[точные науки](#stem)|Возвращает `stem` компонент `myname`.|
|[string](#string)|Преобразует последовательность, хранимую в `mypath`.|
|[swap](#swap)|Выполняет `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|Преобразует последовательность, хранимую в `mypath` UTF-16 и возвращает ее, сохранив в объект типа `u16string`.|
|[u32string](#u32string)|Преобразует последовательность, хранимую в `mypath` UTF-32 и возвращает ее, сохранив в объект типа `u32string`.|
|[u8string](#u8string)|Преобразует последовательность, хранимую в `mypath` UTF-8 и возвращает ее, сохранив в объект типа `u8string`.|
|[value_type](#value_type)|Тип описывает элементы пути, предпочитаемые в системе размещения.|
|[wstring](#wstring)|Преобразует последовательность, хранимую в `mypath` кодировку, предпочитаемую в системе размещения для `wchar_t` последовательности и возвращает ее, сохранив в объект типа `wstring`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_as)|Заменяет элементы пути копию другой путь.|
|[оператор+=](#op_add)|Различные `concat` выражения.|
|[оператор/=](#op_divide)|Различные `append` выражения.|
|[оператор string_type](#op_string)|Возвращает `myname`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="append"></a> PATH::append

Добавляет указанную последовательность для `mypath`, преобразованный, так и вставки `preferred_separator` при необходимости.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*source*<br/>
Указанной последовательности.

*Первый*<br/>
Начало указанной последовательности.

*последний*<br/>
Конец указанной последовательности.

## <a name="assign"></a> PATH::Assign

Заменяет `mypath` с указанной последовательностью, преобразованной при необходимости.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*source*<br/>
Указанной последовательности.

*Первый*<br/>
Начало указанной последовательности.

*последний*<br/>
Конец указанной последовательности.

## <a name="begin"></a> PATH::BEGIN

Возвращает `path::iterator` обозначающий первый элемент пути в имени пути, если он имеется.

```cpp
iterator begin() const;
```

## <a name="c_str"></a> PATH::c_str

Возвращает указатель на первый символ в `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a> PATH::Clear

Выполняет `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="compare"></a> PATH::Compare

Первая функция возвращает `mypath.compare(pval.native())`. Вторая функция возвращает `mypath.compare(str)`. Третья функция возвращает `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь для сравнения.

*str*<br/>
Строка для сравнения.

*ptr*<br/>
Указатель для сравнения.

## <a name="concat"></a> PATH::concat

Добавляет к указанной последовательности `mypath`, преобразовать (но не вставляют разделитель) при необходимости.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Параметры

*source*<br/>
Указанной последовательности.

*Первый*<br/>
Начало указанной последовательности.

*последний*<br/>
Конец указанной последовательности.

## <a name="const_iterator"></a> PATH::const_iterator

Синоним для `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a> PATH::Empty

Возвращает `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a> PATH::End

Возвращает итератор конец последовательности типа `iterator`.

```cpp
iterator end() const;
```

## <a name="extension"></a> PATH::Extension

Возвращает суффикс `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Примечания

Возвращает суффикс `filename() X` таким образом, чтобы:

Если `X == path(".") || X == path("..")` или, если `X` не содержит точки, суффикс пуст.

В противном случае суффикс начинается с самой крайней правой точки (и включает ее).

## <a name="filename"></a> PATH::filename

Возвращает компонент корневого каталога myname, а именно `empty() path() : *--end()`. Компонент может быть пустым.

```cpp
path filename() const;
```

## <a name="generic_string"></a> PATH::generic_string

Возвращает значение `this->string<Elem, Traits, Alloc>(al)` с (в Windows) любой обратной косой чертой, преобразованной в прямую косую черту.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a> PATH::generic_u16string

Возвращает `u16string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a> PATH::generic_u32string

Возвращает `u32string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a> PATH::generic_u8string

Возвращает `u8string()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a> PATH::generic_wstring

Возвращает `wstring()` с (в Windows) преобразованием любой обратной косой черты в прямую косую черту.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a> PATH::has_extension

Возвращает `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a> PATH::has_filename

Возвращает `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> PATH::has_parent_path

Возвращает `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> PATH::has_relative_path

Возвращает `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a> PATH::has_root_directory

Возвращает `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a> PATH::has_root_name

Возвращает `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a> PATH::has_root_path

Возвращает `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a> PATH::has_stem

Возвращает `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a> PATH::is_absolute

Для Windows, функция возвращает `has_root_name() && has_root_directory()`. Для Posix функция возвращает `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a> PATH::is_relative

Возвращает `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a> PATH::iterator

Двунаправленный постоянный итератор, указывающий компоненты пути `myname`.

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

### <a name="remarks"></a>Примечания

Этот класс описывает двунаправленный постоянный итератор, указывающий `path` компоненты `myname` в последовательности:

1. корневое имя (при наличии);

1. корневой каталог (при наличии);

1. остальные элементы каталога родительского `path`, если он присутствует, заканчивая именем файла, при его наличии

Для `pval` объект типа `path`:

1. `path::iterator X = pval.begin()` Определяет первый `path` элемент в имени пути, если он имеется.

1. `X == pval.end()` верно, когда `X` точек просто за концом последовательности компонентов.

3. `*X` Возвращает строку, совпадающую с текущим компонентом

1. `++X` указывает на следующий компонент в последовательности, если он имеется.

1. `--X` указывает на предыдущий компонент в последовательности, если он имеется.

1. Изменение `myname` делает недействительными все итераторы, указывающие элементы в `myname`.

## <a name="make_preferred"></a> PATH::make_preferred

Преобразует каждый разделитель для `preferred_separator` при необходимости.

```cpp
path& make_preferred();
```

## <a name="native"></a> PATH::Native

Возвращает `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a> PATH::operator =

Заменяет элементы пути копию другой путь.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Путь](../standard-library/path-class.md) копируется в `path`.

*source*<br/>
Исходный путь.

### <a name="remarks"></a>Примечания

Первый оператор копий член `right.myname` для `myname`. Второй оператор-член перемещает `right.myname` для `myname`. Третий оператор-член ведет себя так же, как `*this = path(source)`.

## <a name="op_add"></a> PATH::operator +=

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

*right*<br/>
Добавленном контуре.

*str*<br/>
Добавлена строка.

*ptr*<br/>
Добавлен указатель.

*Elem*<br/>
Добавленный `value_type` или `Elem`.

*source*<br/>
Добавлен источник.

### <a name="remarks"></a>Примечания

Функции-члены работают так же, как следующие соответствующие выражения:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a> PATH::operator / =

Различные `append` выражения.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Добавленном контуре.

*source*<br/>
Добавлен источник.

### <a name="remarks"></a>Примечания

Функции-члены работают так же, как следующие соответствующие выражения:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a> PATH::operator string_type

Возвращает `myname`.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> PATH::parent_path

Возвращает родительский компонент пути `myname`.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает родительский компонент пути `myname`, а именно префикс `myname` после удаления `filename().native()` и любой непосредственно предшествующих разделителей каталога. (Аналогично, если `begin() != end()`, это сочетание всех элементов в диапазоне `[begin(), --end())` путем последовательного применения `operator/=`.) Компонент может быть пустым.

## <a name="path"></a> PATH::path

Создает `path` различными способами.

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

*right*<br/>
Путь, из которых созданного пути является копией.

*source*<br/>
Источник, из которых созданного пути является копией.

*Loc*<br/>
Указанный языковой стандарт.

*Первый*<br/>
Позиция первого элемента, который следует скопировать.

*последний*<br/>
Позиция последнего элемента для копирования.

### <a name="remarks"></a>Примечания

Конструкторы, все построения `myname` различными способами:

Для `path()` это `myname()`.

Для `path(const path& right`) это `myname(right.myname)`.

Для `path(path&& right)` это `myname(right.myname)`.

Для `template<class Source> path(const Source& source)` это `myname(source)`.

Для `template<class Source> path(const Source& source, const locale& loc)` это `myname(source)`, получающий все необходимые аспекты codecvt из `loc`.

Для `template<class InIt> path(InIt first, InIt last)` это `myname(first, last)`.

Для `template<class InIt> path(InIt first, InIt last, const locale& loc)` это `myname(first, last)`, получающий все необходимые аспекты codecvt из `loc`.

## <a name="preferred_separator"></a> PATH::preferred_separator

Постоянный объект предоставляет предпочтительный символ для разделения компонентов пути в зависимости от операционной системы размещения.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Примечания

Обратите внимание, что в большинстве контекстов в Windows в равной мере допускается использование соответствующего символа L"/".

## <a name="relative_path"></a> PATH::relative_path

Возвращает компонент относительного пути `myname`.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает компонент относительного пути `myname`, а именно суффикс `myname` после удаления `root_path().native()` и любой непосредственно последующих избыточных разделителей каталога. Компонент может быть пустым.

## <a name="remove_filename"></a> PATH::remove_filename

Удаляет имя файла.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> PATH::replace_extension

Заменяет расширение `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Параметры

*newext*<br/>
Новое расширение.

### <a name="remarks"></a>Примечания

Сначала удаляет суффикс `extension().native()` из `myname`. Затем, если `!newext.empty() && newext[0] != dot` (где `dot` — `*path(".").c_str()`), затем `dot` добавляется к `myname`. Затем *newext* добавляется к `myname`.

## <a name="replace_filename"></a> PATH::replace_filename

Заменяет имя файла.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь к имени файла.

### <a name="remarks"></a>Примечания

Функция-член выполняет:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a> PATH::root_directory

Возвращает компонент корневого каталога `myname`.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Примечания

Компонент может быть пустым.

## <a name="root_name"></a> PATH::root_name

Возвращает компонент корневого имени `myname`.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Примечания

Компонент может быть пустым.

## <a name="root_path"></a> PATH::root_path

Возвращает компонент корневого пути `myname`.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Примечания

Возвращает компонент корневого пути `myname`, в частности `root_name()`  /  `root_directory`. Компонент может быть пустым.

## <a name="stem"></a> PATH::stem

Возвращает `stem` компонент `myname`.

```cpp
path stem() const;
```

### <a name="remarks"></a>Примечания

Возвращает `stem` компонент `myname`, в частности `filename().native()` любой завершающими `extension().native()` удалены. Компонент может быть пустым.

## <a name="string"></a> PATH::String

Преобразует последовательность, хранимую в `mypath`.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Примечания

Первая функция-член (шаблон) преобразует последовательность, хранимую в `mypath` так же, как:

1. `string()` для `string<char, Traits, Alloc>()`

1. `wstring()` для `string<wchar_t, Traits, Alloc>()`

1. `u16string()` для `string<char16_t, Traits, Alloc>()`

1. `u32string()` для `string<char32_t, Traits, Alloc>()`

Вторая функция-член преобразует последовательность, хранимую в `mypath` кодировку, предпочитаемую в системе размещения для **char** последовательности и возвращает ее, сохранив в объект типа `string`.

## <a name="string_type"></a> PATH::STRING_TYPE

Тип является синонимом `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a> PATH::Swap

Выполняет `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a> PATH::u16string

Преобразует последовательность, хранимую в `mypath` UTF-16 и возвращает ее, сохранив в объект типа `u16string`.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a> PATH::u32string

Преобразует последовательность, хранимую в `mypath` UTF-32 и возвращает ее, сохранив в объект типа `u32string`.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a> PATH::u8string

Преобразует последовательность, хранимую в `mypath` UTF-8 и возвращает ее, сохранив в объект типа `u8string`.

```cpp
string u8string() const;
```

## <a name="value_type"></a> PATH::value_type

Этот тип описывает `path` элементы по операционной системы.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a> PATH::wstring

Преобразует последовательность, хранимую в `mypath` кодировку, предпочитаемую в системе размещения для **wchar_t** последовательности и возвращает ее, сохранив в объект типа `wstring`.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
