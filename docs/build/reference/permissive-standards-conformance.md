---
title: / permissive-(соответствие стандартам)
ms.date: 03/08/2019
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 05089ef4f0a516f932d82f13be979da572701ae2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320049"
---
# <a name="permissive--standards-conformance"></a>/ permissive-(соответствие стандартам)

Укажите режим соответствия стандартам в компилятор. Используйте этот параметр, чтобы определить и устранить проблемы совместимости в коде, чтобы сделать его более точные и более переносимым.

## <a name="syntax"></a>Синтаксис

> **/ permissive-**

## <a name="remarks"></a>Примечания

Этот параметр поддерживается в Visual Studio 2017 и более поздних версий.

Можно использовать **/ permissive-** параметр компилятора, чтобы указать поведение, соответствующее стандартам компилятора. Этот параметр отключает широкие поведения и задает [/Zc](zc-conformance.md) параметры компилятора для строгого соответствия. В интегрированной среде разработки этот параметр также делает код несоответствующих подчеркивание обработчик IntelliSense.

По умолчанию **/ permissive-** параметр установлен в новых проектах, созданных с Visual Studio 2017 версии 15.5 и более поздних версий. Он не имеет значение по умолчанию в более ранних версий. Если параметр установлен, компилятор создает диагностики ошибок или предупреждений при нестандартные языковые конструкции обнаружены в коде, включая некоторые распространенные ошибки перед-C ++ 11 код.

**/ Permissive-** режим совместим с почти все файлы заголовков из последней комплекты Windows, например Software Development Kit (SDK) или Windows Driver Kit (WDK), начиная с версии Windows Fall Creators SDK (10.0.16299.0). Более старых версиях пакета SDK может не компилироваться при использовании **/ permissive-** для различных источника кода причины соответствия. Компилятор и пакеты SDK для поставки на временных шкалах для разных выпусков, поэтому существуют некоторые оставшиеся проблемы. Определенный заголовок файла проблемы, см. в разделе [проблемы заголовка Windows](#windows-header-issues) ниже.

**/ Permissive-** наборы параметров [/Zc: referencebinding](zc-referencebinding-enforce-reference-binding-rules.md), [/Zc: strictstrings](zc-strictstrings-disable-string-literal-type-conversion.md), и [/Zc: rvaluecast](zc-rvaluecast-enforce-type-conversion-rules.md) параметры для соответствующих поведение. Эти параметры по умолчанию используется несоответствующее поведение. Вы можете передавать параметры определенного **/Zc** параметры после **/ permissive-** в командной строке, чтобы переопределить это поведение.

В версиях начиная компилятора в Visual Studio 2017 версии 15.3 **/ permissive-** наборы параметров [/Zc: ternary](zc-ternary.md) параметр. Компилятор также реализует несколько требований для поиска двухфазной имя. Когда **/ permissive-** используется параметр, компилятор выполняет синтаксический анализ определения шаблонов функций и классов и определяет зависимых и не зависимых от имен, используемых в шаблонах. В этом выпуске выполняется только анализ зависимостей имя.

Расширения конкретной среды и области языка, которые стандарте оставляет зависит от реализации, не подвержены **/ permissive-**. Например, характерные для Майкрософт `__declspec`, соглашение о вызовах и обработки ключевые слова и директивы pragma специфичные для компилятора или атрибуты структурированных исключений не были отмечены компилятором в **/ permissive-** режим.

**/ Permissive-** параметр использует поддержку соответствия в текущей версии компилятора, чтобы определить, какие языковые конструкции, не соответствующий требованиям. Параметр не определить, соответствует ли ваш код для определенной версии стандарта C++. Чтобы включить поддержку всех реализованных компилятором в последний черновик стандарта, используйте [/std:latest](std-specify-language-standard-version.md) параметр. Чтобы ограничить поддержку компилятора для текущей реализации стандарт C ++ 17, используйте [/std: c ++ 17](std-specify-language-standard-version.md) параметр. Чтобы ограничить поддержку компилятора для более точного соответствия стандарту C ++ 14, используйте [/std: c ++ 14](std-specify-language-standard-version.md) параметр, который используется по умолчанию.

Не все C ++ 11, C ++ 14 и C ++ 17 соответствующее стандартам код поддерживается компилятором MSVC во всех версиях Visual Studio 2017. В зависимости от версии Visual Studio **/ permissive-** параметр может не обнаружить проблемы в отношении некоторых аспектов двухфазного поиска имени, привязки неконстантная ссылка во временный, обработке init копирования как прямой инициализации, позволяя несколько пользовательских преобразований в инициализации или альтернативные маркеры для логических операторов и других аспектах соответствия, не поддерживается. Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md). Чтобы получить максимум **/ permissive-**, обновление до последней версии Visual Studio.

### <a name="how-to-fix-your-code"></a>Как для исправления кода

Ниже приведены некоторые примеры кода, который определяется как несоответствующее при использовании **/ permissive-**, а также предлагаемые способы их устранения проблем.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Использовать значение по умолчанию в качестве идентификатора в машинном коде

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Поиск элементов в зависимых базовых

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Использование полных имен в объявлениях членов

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Инициализация нескольких элементов объединения в инициализаторе члена

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

#### <a name="hidden-friend-name-lookup-rules"></a>Правила подстановки имен скрытых friend

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
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>Использование ограниченных перечислений в границы массива

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Используйте for each в машинном коде

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Аргументы неоднозначным условный оператор

В версиях компилятора до Visual Studio 2017 версии 15.3 компилятор принимало аргументы условный оператор (или троичный оператор) `?:` , неоднозначны со стандартом. В **/ permissive-** режим, компилятор теперь выдает одну или несколько диагностических в случаях, когда компилируется без диагностики в более ранних версий.

Перечислены распространенные ошибки, которые могут возникнуть в результате этого изменения.

- Ошибка C2593: «operator»? является неоднозначным

- Ошибка C2679: двоичный "?": не найден оператор, принимающий правый операнд типа «B» (или отсутствует приемлемое преобразование отсутствует)

- Ошибка C2678: двоичный "?": не найден оператор, принимающий левый операнд типа «A» (или отсутствует приемлемое преобразование отсутствует)

- Ошибка C2446: ":": преобразование из «B» на «A»

Шаблон типичный код, который может вызвать эту проблему — Если какие-либо классы C предоставляет неявную конструктора из другого типа T и оператор неявную преобразования для типа T. В этом случае преобразование второго аргумента в тип третьего аргумента и преобразование третьего аргумента в тип второго аргумента, являются допустимые преобразования. Так как оба являются допустимыми, он является неоднозначным в соответствии со стандартом.

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

Нет важное исключение, чтобы этот распространенный шаблон при T представляет один из типов заканчивающуюся нулем строку (например, `const char *`, `const char16_t *`, и т. д) и фактического аргумента `?:` представляет собой строку литерала надлежащего типа. C ++ 17 изменилось семантику с C ++ 14. Таким образом, код в примере 2 принимается в разделе **/std: c ++ 14** и отклоненных под **/std: c ++ 17** при **/Zc: ternary** или **/permissive-** используется.

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

Еще один случай, где могут возникнуть ошибки находится в условных операторов с одним аргументом типа `void`. Возможно, этот вариант часто встречается в стиле ASSERT макросы.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Также могут возникнуть ошибки в шаблоне метапрограммирование, где типы результатов условный оператор может измениться в разделе **/Zc: ternary** и **/ permissive-**. Один из способов устранения этой проблемы является использование [std::remove_reference](../../standard-library/remove-reference-class.md) для результирующего типа.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>Имя двухэтапного поиска

Когда **/ permissive-** используется параметр, компилятор анализирует функций и классов определения шаблонов, идентификация зависимых и независимые, используемых в шаблонах, при необходимости для поиска двухфазной имя. В Visual Studio 2017 версии 15.3 выполняется анализ зависимостей имя. В частности не зависимые имена, которые не объявлены в рамках определения шаблона к созданию диагностического сообщения, при необходимости по стандартам ISO C++. В Visual Studio 2017 версии 15.7 привязки имен независимые, требующих поиска зависимостью от аргументов в контексте определение, также выполняются.

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

Если вы устаревшее поведение для двухэтапного поиска, но в противном случае **/ permissive-** поведение, добавьте **/Zc:twoPhase-** параметр.

### <a name="windows-header-issues"></a>Заголовок проблемы Windows

**/ Permissive-** параметр слишком строгие для версии комплекты Windows до Windows Fall Creators Update SDK (10.0.16299.0) или набор драйверов Windows (WDK) версии 1709. Мы рекомендуем обновить до последних версий комплекты Windows для использования **/ permissive-** в коде драйвера Windows или устройства.

Некоторые файлы заголовков Windows апреля 2018 г. Обновление пакета SDK для (10.0.17134.0), Windows Fall Creators Update SDK (10.0.16299.0) или Windows Driver Kit (WDK) 1709, возникают проблемы, которые не позволяют несовместимы с использование **/permissive-**. Чтобы обойти эти проблемы, рекомендуется ограничить использование этих заголовков к только эти файлы исходного кода, которые они требуются и удалите **/ permissive-** параметр при компиляции этих файлов конкретного исходного кода.

Эти заголовки WinRT WRL выпущена в Windows апреля 2018 г. Обновление пакета SDK (10.0.17134.0) не являются чистыми с **/ permissive-**. Чтобы обойти эти проблемы, не используйте **/ permissive-**, или использовать **/ permissive-** с **/Zc:twoPhase-** при работе с такими заголовками:

- Проблемы в winrt/wrl/async.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Проблема winrt/wrl/implements.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Эти заголовки пользовательском режиме выпущена в Windows апреля 2018 г. Обновление пакета SDK (10.0.17134.0) не являются чистыми с **/ permissive-**. Чтобы обойти эти проблемы, не используйте **/ permissive-** при работе с такими заголовками:

- Проблемы в um/Tune.h

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Проблема um/spddkhlp.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Проблемы в um/refptrco.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Эти проблемы относятся только к заголовкам режима пользователя в Windows Fall Creators Update SDK (10.0.16299.0).

- Проблема um/Query.h

   При использовании **/ permissive-** переключатель компилятора `tagRESTRICTION` структуры не компилируется из-за case(RTOr) член «или».

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

   Чтобы устранить эту проблему, скомпилировать файлы, содержащие Query.h без **/ permissive-** параметр.

- Проблема um/cellularapi_oem.h

   При использовании **/ permissive-** параметр компилятора, опережающее объявление типа `enum UICCDATASTOREACCESSMODE` вызывает предупреждение:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Прямого объявления неограниченного перечисления является расширением Майкрософт. Чтобы устранить эту проблему, скомпилировать файлы, содержащие cellularapi_oem.h без **/ permissive-** параметр или используйте [/wd](compiler-option-warning-level.md) параметр, чтобы отключить предупреждение C4471.

- Проблема um/omscript.h

   В C ++ 03, преобразования из строкового литерала в BSTR (который является typedef для "wchar_t *") является устаревшей, но разрешено. В C ++ 11 больше не допускается преобразование.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Чтобы устранить эту проблему, скомпилировать файлы, содержащие omscript.h без **/ permissive-** параметр или используйте **/Zc:strictStrings-** вместо этого.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

В Visual Studio 2017 версии 15.5 и более поздних версий используйте следующую процедуру:

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. Выберите **свойства конфигурации** > **C/C++** > **языка** страницу свойств.

1. Изменение **режим совместимости** значение свойства **Да (/ permissive-)**. Выберите **ОК** или **применить** для сохранения изменений.

В версиях до Visual Studio 2017 версии 15.5 используйте следующую процедуру:

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите **/ permissive-** параметр компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора MSVC](compiler-options.md)
- [Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
