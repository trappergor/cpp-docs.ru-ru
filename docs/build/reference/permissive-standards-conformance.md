---
title: /permissive- (соответствие стандартам)
description: Справочное руководство по варианту компилятора компилятора Корпорации Майкрософт /разрешительное - (соответствие стандартам).
ms.date: 04/14/2020
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 695f84e64f07128ac7744dc99e736f2a71ab3e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337401"
---
# <a name="permissive--standards-conformance"></a>/permissive- (соответствие стандартам)

Укажите режим соответствия стандартам компилятора. Используйте эту опцию, чтобы помочь вам определить и исправить проблемы с соответствием в коде, чтобы сделать его более правильным и более портативным.

## <a name="syntax"></a>Синтаксис

> **/разрешительно-**

## <a name="remarks"></a>Remarks

Эта опция поддерживается в Visual Studio 2017 и позже.

Можно использовать опцию **/разрешительно-компилятор,** чтобы указать поведение компилятора, соответствующее стандартам. Этот параметр отсрочен разрешительному поведению и устанавливает параметры компилятора [/c](zc-conformance.md) для строгого соответствия. В IDE эта опция также заставляет движок IntelliSense подчеркивать несоответствующий код.

По умолчанию **опция /разрешительно-опция** устанавливается в новых проектах, созданных Visual Studio 2017 версии 15.5 и более поздних версий. Он не установлен по умолчанию в предыдущих версиях. При установке опции компилятор генерирует диагностические ошибки или предупреждения при обнаружении нестандартных языковых конструкций в коде, в ключая некоторые распространенные ошибки в коде предварительного C-11.

**Опция /разрешительной совместима** почти со всеми файлами заголовка из последних наборов Windows, таких как набор для разработки программного обеспечения (SDK) или набор драйверов Windows (WDK), начиная с Windows Fall Creators SDK (10.0.16299.0). Старые версии SDK могут не компилироваться под **/разрешительным -** по различным причинам соответствия исходного кода. Компилятор и SDKs отправляются на разные сроки выпуска, поэтому остаются некоторые проблемы. Для конкретных проблем с файлами заголовка смотрите [проблемы заголовка Windows](#windows-header-issues) ниже.

**/Допустимый вариант** устанавливает [/c:referenceBinding](zc-referencebinding-enforce-reference-binding-rules.md), [/ Кк:StrictStrings](zc-strictstrings-disable-string-literal-type-conversion.md), и [/ C:rvalueCast](zc-rvaluecast-enforce-type-conversion-rules.md) варианты соответствующей поведения. Эти параметры по умолчанию не соответствуют поведению. Вы можете пройти определенные параметры **/C** после **/допустимого-** на командной строке, чтобы переопределить это поведение.

В версиях компилятора, начинающаяся в версии Visual Studio 2017 15.3, **/разрешительно-опция** устанавливает опцию [/C:ternary.](zc-ternary.md) Компилятор также реализует больше требований для двухэтапного поиска имен. При установке **/допустимого -** опциона компилятор разбирает определения функции и шаблона класса и определяет зависимые и независимые имена, используемые в шаблонах. В этом выпуске выполняется только анализ зависимости имени.

Конкретные для окружающей среды расширения и языковые области, которые стандарт оставляет до реализации не зависит от **/ вседозволенности .** Например, конкретные, `__declspec`вызываемые Microsoft, вызывающие конвенцию и структурированные ключевые слова для обработки исключений, а также директивы или атрибуты прагмы для компилятора не помечаются компилятором в **/разрешительном** режиме.

**Опция /разрешительное используется** поддержка соответствия в текущей версии компилятора, чтобы определить, какие языковые конструкции не соответствуют требованиям. Опция не определяет, соответствует ли ваш код конкретной версии стандарта СЗЗ. Для обеспечения всей поддержки компилятора для последнего проекта стандарта используйте опцию [/std:latest.](std-specify-language-standard-version.md) Чтобы ограничить поддержку компилятора стандартом C-17, используйте опцию [/std:c'17.](std-specify-language-standard-version.md) Чтобы ограничить поддержку компилятора, чтобы более точно соответствовать стандарту C-14, используйте опцию [/std:c'14,](std-specify-language-standard-version.md) которая является по умолчанию.

Не все коды, соответствующие стандартам, поддерживаются компилятором MSVC во всех версиях Visual Studio 2017. В зависимости от версии Visual Studio, **/разрешительный вариант** может не обнаруживать проблемы, касающиеся некоторых аспектов двухфазного поиска имен, связывая неконстную ссылку на временное, рассматривая копию init как прямое инициацию, позволяя несколько пользовательских конверсий в инициализации, или альтернативные маркеры для логических операторов, и другие неподдерживаемые области соответствия. Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md). Чтобы получить максимальную отдачу от **/разрешительно-,** обновление Visual Studio до последней версии.

### <a name="how-to-fix-your-code"></a>Как исправить код

Вот несколько примеров кода, который обнаруживается как несоответствующий при использовании **/разрешительно-,** наряду с предложенными способами устранения проблем.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Используйте по умолчанию в качестве идентификатора в родном коде

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Ищите членов в зависимой базе

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>Использование квалифицированных имен в декларациях членов

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Инициализация нескольких членов профсоюза в инициализаторе членов

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>Правила поиска скрытых имен друга

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(p); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>Использование ограниченных перечислений в границах массива

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Используйте для каждого из них в родном коде

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>Использование атрибутов ATL

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be
// used to automatically obtain a *.idl file for the interfaces with
// annotation. Second, add a midl step to your build system to make
// sure that the C++ interface definitions are outputted.
// Last, adjust your existing code to use ATL directly as shown in
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>Неоднозначные условные аргументы оператора

В версиях компилятора перед версией Visual Studio 2017 15.3 компилятор принял `?:` аргументы условному оператору (или оператору ternary), которые стандарт считает неоднозначными. В **/разрешительном** режиме компилятор теперь выдает одну или несколько диагностических средств в случаях, которые компилировались без диагностики в более ранних версиях.

Общие ошибки, которые могут возникнуть в результате этого изменения включают в себя:

- ошибка C2593: "оператор? является неоднозначным

- ошибка C2679: двоичный '?': не найдено оператора, который принимает правую часть работы типа 'B' (или нет приемлемого преобразования)

- ошибка C2678: двоичный '?': не найдено оператора, который принимает левую операнду типа 'A' (или нет приемлемого преобразования)

- ошибка C2446: ':': нет преобразования с 'B' в 'A'

Типичный шаблон кода, который может вызвать эту проблему, когда какой-то класс C предоставляет как неявный конструктор от другого типа T, так и неявный оператор преобразования для ввода Т. В этом случае являются допустимыми являются как преобразование второго аргумента в тип третьего аргумента, так и преобразование третьего аргумента в тип второго аргумента. Поскольку оба являются действительными, это неоднозначно в соответствии со стандартом.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

Есть важное исключение из этого общего шаблона, когда T представляет один из `const char *` `const char16_t *`типов строксс с нулевым `?:` завершением (например, и так далее), а фактическим аргументом является строка буквального соответствующего типа. СМЗ-17 изменил семантику по сравнению с СЗ14. В результате, код в примере 2 принимается под **/std:c'14** и отклонен под **/std:c'17,** когда **используется /c:ternary** или **/permissive-.**

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s;
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

Другой случай, когда вы можете увидеть ошибки `void`в условных операторов с одним аргументом типа . Этот случай может быть распространен в assert-подобных макросах.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Вы также можете увидеть ошибки в метапрограммировании шаблонов, где условные типы результатов оператора могут меняться в соответствии с **/C:ternary** и **/вседозволенным-**. Один из способов решения этой проблемы заключается в использовании [std::remove_reference](../../standard-library/remove-reference-class.md) на результирующем типе.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>Двухэтапный поиск имен

При установке **/допустимого -** опциона компилятор разбирает определения функции и шаблона класса, идентифицируя зависимые и независимые имена, используемые в шаблонах, как это требуется для поиска двухфазных имен. В версии Visual Studio 2017 15.3 проводится анализ зависимости имени. В частности, независимые имена, которые не объявляться в контексте определения шаблона, вызывают диагностическое сообщение, как того требуют стандарты ISO C. В версии Visual Studio 2017 2017 также выполняется привязка независимых имен, требующих аргументозависимости в контексте определения.

```cpp
// dependent base
struct B {
    void g() {}
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

Если вы хотите устаревающее поведение для двухэтапного поиска, но в противном случае хотите **/разрешительное поведение,** добавьте опцию **/C:twoPhase-** опция.

### <a name="windows-header-issues"></a>Проблемы заголовка Windows

**Опция /разрешительность** слишком строгая для версий комплектов Windows до обновления Создателей Windows SDK (10.0.16299.0) или версии 1709 windows Driver Kit (WDK). Мы рекомендуем вам обновить до последних версий комплектов Windows, чтобы использовать **/разрешительно-** в коде драйвера Windows или устройства.

Некоторые файлы заголовка в Windows Апрель 2018 Обновление SDK (10.0.17134.0), Windows Fall Создатели Обновление SDK (10.0.16299.0), или Windows Driver Kit (WDK) 1709, по-прежнему имеют проблемы, которые делают их несовместимыми с использованием **/ разрешительно-**. Для устранения этих проблем мы рекомендуем ограничить использование этих заголовков только теми файлами исходного кода, которые требуют их, и удалить **опцию /разрешительного при** компилировании этих конкретных файлов исходного кода.

Эти заголовки WinRT WRL, выпущенные в Windows April 2018 Update SDK (10.0.17134.0) не являются чистыми с **/вседозволенным-**. Для работы вокруг этих вопросов, либо не использовать **/ вседозволенность,** или использовать **/ вседозволенность-** с **/ C: дваPhase-когда** вы работаете с этими заголовками:

- Проблемы в вините/вл/async.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Выпуск в виниле/вкл/реалистам.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Эти заголовки пользовательского режима, выпущенные в Windows April 2018 Обновление SDK (10.0.17134.0) не являются чистыми с **/вседозволенным-**. Для работы над этими вопросами, не используйте **/ вседозволенность-** при работе с этими заголовками:

- Проблемы в um/Tune.h

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Выпуск в um/spddkhlp.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Проблемы в um/refptrco.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Эти проблемы специфичны для заголовков пользовательского режима в обновлении Windows Fall Creators SDK (10.0.16299.0):

- Выпуск в um/query.h

   При использовании коммутатора **/разрешительного** компилятора `tagRESTRICTION` структура не компилируется из-за участника (RTOr) или'.

   ```cpp
   struct tagRESTRICTION
   {
       ULONG rt;
       ULONG weight;
       /* [switch_is][switch_type] */ union _URes
       {
           /* [case()] */ NODERESTRICTION ar;
           /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
           /* [case()] */ NODERESTRICTION pxr;
           /* [case()] */ VECTORRESTRICTION vr;
           /* [case()] */ NOTRESTRICTION nr;
           /* [case()] */ CONTENTRESTRICTION cr;
           /* [case()] */ NATLANGUAGERESTRICTION nlr;
           /* [case()] */ PROPERTYRESTRICTION pr;
           /* [default] */  /* Empty union arm */
       } res;
   };
   ```

   Для решения этой проблемы составить файлы, которые включают query.h без **/разрешительного варианта.**

- Выпуск в um/cellularapi_oem.h

   При использовании **/разрешительно-компиляторный** компитер, передовая декларация `enum UICCDATASTOREACCESSMODE` причин предупреждения:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Передний декларирование нескопированный enum — это расширение Корпорации Майкрософт. Чтобы решить эту проблему, компилировать файлы, которые включают cellularapi_oem без **/допустимого-** опции, или использовать опцию [/wd,](compiler-option-warning-level.md) чтобы заставить замолчать предупреждение C4471.

- Выпуск в um/omscript.h

   В C-03, преобразование из строки буквального в BSTR (который является typedef на "wchar_t) является устаревшей, но разрешено. В C-11 конверсия больше не допускается.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Для решения этой проблемы компилировать файлы, которые включают omscript.h без **/разрешительного -** опции, или использовать **/ C: StrictStrings-вместо.**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

В Visual Studio 2017 версии 15.5 и более поздних версиях, используйте эту процедуру:

1. Откройте диалоговую будку **Страниц ы свойства** вашего проекта.

1. Выберите страницу**свойства** **свойства Configuration Properties** > **C/C'.** > 

1. Измените значение свойства **режима соответствия** на **Да (/разрешительное-)**. Выберите **OK** или **применить,** чтобы сохранить изменения.

В версиях перед Visual Studio 2017 версия 15.5, использовать эту процедуру:

1. Откройте диалоговую будку **Страниц ы свойства** вашего проекта.

1. Выберите страницу свойства **командной** > **строки** Configuration Properties**C/C'.** > 

1. Введите **опцию /разрешительно-компилятор** в поле **дополнительных опций.** Выберите **OK** или **применить,** чтобы сохранить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)\
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
