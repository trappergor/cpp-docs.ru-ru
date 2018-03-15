---
title: "-разрешительным - (соответствие стандартам) | Документы Microsoft"
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
dev_langs:
- C++
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09b24e96752e61f4d09efc3780e0e60ffed8effd
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="permissive--standards-conformance"></a>/ разрешительным-(соответствие стандартам)

Укажите режим соответствия стандартам для компилятора. Используйте этот параметр для обнаружения и устранения проблем совместимости в коде, чтобы сделать его более правильный и более переносимым.

## <a name="syntax"></a>Синтаксис

> **/permissive-**

## <a name="remarks"></a>Примечания

Можно использовать **/ разрешительным-** компилятора параметр, чтобы указать поведение компилятора стандартам. Этот параметр отключает разрешительным поведений и устанавливает [/Zc](../../build/reference/zc-conformance.md) параметры компилятора для строгого соответствия. В Интегрированной среде разработки этот параметр также делает engine подчеркивание несоответствующих кода IntelliSense.

По умолчанию **/ разрешительным-** был установлен в новых проектах, созданных с версии Visual Studio 2017 г 15,5 и более поздних версиях. В более ранних версиях по умолчанию не задано. Если параметр имеет значение, компилятор создает диагностики ошибки или предупреждения при стандартным языковые конструкции обнаружении в коде, включая некоторые распространенные ошибки перед-коде C ++ 11.

**/ Разрешительным-** режим совместим с почти все файлы заголовков из последние пакеты Windows, например средств разработки программного обеспечения (SDK) или набор драйверов Windows (WDK), начиная с Windows SDK создатели Осень (10.0.16299.0). Старые версии пакета SDK может не компилироваться при использовании **/ разрешительным-** для различных исходных причин соответствие кода. Компилятор и пакеты SDK отгрузки на другой выпуск временные шкалы, таким образом, существуют некоторые оставшиеся проблемы. Вопросы файлов определенного заголовка, в разделе [проблемы заголовок Windows](#windows-header-issues) ниже.

**/ Разрешительным-** параметр наборы [/Zc: strictstrings](../../build/reference/zc-conformance.md) и [/Zc: rvaluecast](../../build/reference/zc-conformance.md) параметры соответствующих поведению. Они по умолчанию поведение, не соответствующий требованиям. Вы можете передать конкретных **/Zc** параметры после **/ разрешительным-** в командной строке, чтобы переопределить это поведение.

В версиях начиная компилятора в Visual Studio 2017 г. версия 15,3 **/ разрешительным-** параметр наборы [/Zc:ternary](../../build/reference/zc-ternary.md) параметр. Компилятор реализует несколько требований для подстановки двухфазной имя. Когда **/ разрешительным-** параметр задан, компилятор анализирует функций и классов определения шаблонов, идентификация зависимых и не зависит от имен, используемых в шаблонах. В этом выпуске выполняется анализ зависимостей только имя.

Расширения среды и язык области, с которыми стандартной оставляет зависит от реализации не подвержены **/ разрешительным-**. Например, характерные для Майкрософт `__declspec`, соглашение о вызовах и обработке ключевые слова и директивы pragma специфичные для компилятора или атрибуты структурированных исключений не отмечены компилятором в **/ разрешительным-** режим.

**/ Разрешительным-** параметр использует поддержки соответствия в текущей версии компилятора для определения, какие языковые конструкции, не соответствующий требованиям. Этот параметр не определить, если код соответствует определенной версии стандарта C++. Чтобы включить все реализованные в компиляторе стандарта последнюю черновика, используйте [/std:latest](../../build/reference/std-specify-language-standard-version.md) параметр. Чтобы ограничить поддержку компилятора для текущей реализации стандарт C ++ 17, используйте [/std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) параметр. Чтобы ограничить поддержку компилятора для более точного соответствия стандарту C ++ 14, используйте [/std: c ++ 14](../../build/reference/std-specify-language-standard-version.md) параметр, который используется по умолчанию.

Не все C ++ 11 C ++ 14 и C ++ 17 стандартам код поддерживается компилятором Visual C++ в Visual Studio 2017 г. **/ Разрешительным-** параметр не может обнаружить проблемы в отношении некоторых аспектов поиск имени двухфазной, привязки неконстантная ссылка во временный, обработке init копирования как прямой инициализации, позволяя несколько пользовательских преобразований в Инициализация или альтернативные токены для логических операторов и других областях, соответствия не поддерживается. Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="how-to-fix-your-code"></a>Устранение кода

Вот несколько примеров кода, который распознается как недопустимые при использовании **/ разрешительным-**, а также предлагаемые способы устранения проблемы.

#### <a name="use-default-as-an-identifier-in-native-code"></a>По умолчанию в качестве идентификатора в машинном коде

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>Поиск элементов в зависимых базы

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

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Инициализировать несколько членов объединения в инициализатор члена

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

#### <a name="hidden-friend-name-lookup-rules"></a>Правила подстановки имен скрытые friend

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

#### <a name="use-for-each-in-native-code"></a>Используйте для каждого в машинном коде

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

#### <a name="use-of-atl-attributes"></a>Использование атрибутов библиотеки ATL

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

В версиях до Visual Studio 2017 г. версия 15,3 компилятора компилятор принял аргументы условный оператор (или троичный оператор) `?:` , неоднозначны стандартом. В **/ разрешительным-** режиме, компилятор теперь выдает диагностики в случаях, когда скомпилирован без диагностики в более ранних версиях.

Следующие частых ошибок, которые могут возникнуть в результате этого изменения.

- Ошибка C2593: «оператор»? является неоднозначным

- Ошибка C2679: двоичный '?': не найден оператор, принимающий правый операнд типа «B» (или отсутствует приемлемое преобразование отсутствует)

- Ошибка C2678: двоичный '?': не найден оператор, принимающий левый операнд типа «A» (или отсутствует приемлемое преобразование отсутствует)

- Ошибка C2446: ":": преобразование из «B» на «A»

Шаблон обычного кода, которая может вызвать эту проблему при некоторых класс C предоставляет неявную конструктора из другого типа T и оператор без явного преобразования типа T. В этом случае преобразование второй аргумент в тип третьей и преобразование третий аргумент в тип вторая являются допустимые преобразования, которая определяется неоднозначно в соответствии со стандартом.

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

Нет важное исключение для этой общей схемой при T представляет собой один из типов, идентифицирующий (например, `const char *`, `const char16_t *`и так далее) и фактического аргумента `?:` представляет собой строку литерала соответствующего типа. Семантика c ++ 17 изменено с C ++ 14. В результате код в примере 2 принимается под **/std: c ++ 14** и отклоненные под **/std: c ++ 17** при **/Zc:ternary** или **/permissive-**используется.

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

Другой случай, где могут возникнуть ошибки, в условных операторов с одним аргументом типа `void`. Этот случай может применяться в напоминают ASSERT.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Также могут возникнуть ошибки в шаблоне метапрограммирования, где типы результата условного оператора может изменять в соответствии с **/Zc:ternary** и **/ разрешительным-**. Один из способов устранения этой проблемы заключается в использовании [std::remove_reference](../../standard-library/remove-reference-class.md) для результирующего типа.

```cpp
// Example 4: different result types 
extern bool cond;
extern int count;
char  a = 'A'; 
const char  b = 'B'; 
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary 
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary 
```

#### <a name="two-phase-name-look-up-partial"></a>Для поиска имени двухфазной (частично)

Когда **/ разрешительным-** был установлен в Visual Studio 2017 г. версия 15,3, компилятор анализирует функций и классов определения шаблонов, имена зависимых и не зависит от используемого в шаблонах, при необходимости двухфазной имени подстановки. В этом выпуске выполняется анализ зависимостей только имя. В частности не зависимые имена, которые не объявлены в контексте определение шаблона вызвать диагностическое сообщение при необходимости по стандартам ISO C++. Однако привязки имен независимые, требующие аргумент зависимый поиск в контексте определение не выполняется.

```cpp
// dependent base
struct B {
    void g();
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

### <a name="windows-header-issues"></a>Заголовок проблемы Windows

**/ Разрешительным-** параметр слишком строгие для версии наборы средств Windows перед Осень создатели обновления пакета SDK для Windows (10.0.16299.0), или набор драйверов Windows (WDK) 1709. Рекомендуется обновить до последних версий наборы средств Windows для использования **/ разрешительным-** в коде драйвера Windows или устройства.

Некоторые файлы заголовков в Осень создатели обновления пакета SDK Windows (10.0.16299.0) или 1709, набор драйверов Windows (WDK) возникают проблемы, обеспечивающие их несовместимы с использованием **/ разрешительным-**. Для решения этих проблем, рекомендуется ограничить использование этих заголовков к только эти файлы исходного кода, требует от них, а затем удалите **/ разрешительным-** параметр при компиляции этих файлов определенного исходного кода. Следующие проблемы относятся только к Осень создатели обновления пакета SDK Windows (10.0.16299.0).

#### <a name="issue-in-umqueryh"></a>Проблема um\Query.h

При использовании **/ разрешительным-** переключатель компилятора `tagRESTRICTION` структуры не компилируется из-за case(RTOr) член «или».

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

Чтобы устранить эту проблему, скомпилировать файлы, содержащие Query.h без **/ разрешительным-** параметр.

#### <a name="issue-in-umcellularapioemh"></a>Проблема um\cellularapi_oem.h

При использовании **/ разрешительным-** переключатель компилятора, опережающее объявление `enum UICCDATASTOREACCESSMODE` вызывает предупреждение:

```cpp
typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
```

Прямого объявления неограниченного перечисления является расширением Майкрософт. Чтобы устранить эту проблему, скомпилировать файлы, содержащие cellularapi_oem.h без **/ разрешительным-** параметр или используйте [/wd](../../build/reference/compiler-option-warning-level.md) параметр, чтобы отключить предупреждение C4471.

#### <a name="issue-in-umomscripth"></a>Проблема um\omscript.h

В C ++ 03, преобразование из строкового литерала в тип BSTR (который является typedef для "wchar_t *") является устаревшей, но разрешено. В C ++ 11 больше не допускается преобразование.

```cpp
virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
    /* [in] */ __RPC__in BSTR propname,
    /* [in] */ __RPC__in BSTR expression,
    /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
```

Чтобы устранить эту проблему, скомпилировать файлы, содержащие omscript.h без **/ разрешительным-** параметр или используйте **/Zc:strictStrings-** вместо него.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

В Visual Studio 2017 г. версия 15,5 и более поздних версий используйте следующую процедуру:

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **языка** страницу свойств.

1. Изменение **режим совместимости** значение свойства **Да (/ разрешительным-)**. Выберите **ОК** или **применить** для сохранения изменений.

В версиях до Visual Studio 2017 г. версия 15,5 используйте следующую процедуру:

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите **/ разрешительным-** параметра компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
