---
title: /permissive- (соответствие стандартам)
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
ms.openlocfilehash: aca0fbc6a2ca36ceae26ba060b5bf92fea79c32c
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273725"
---
# <a name="permissive--standards-conformance"></a>/permissive- (соответствие стандартам)

Укажите режим соответствия стандартам для компилятора. Используйте этот параметр, чтобы определить и исправить проблемы соответствия в коде, чтобы сделать его более правильным и переносимым.

## <a name="syntax"></a>Синтаксис

> **/permissive-**

## <a name="remarks"></a>Примечания

Этот параметр поддерживается в Visual Studio 2017 и более поздних версиях.

Параметр компилятора **/permissive-** можно использовать для указания стандартных стандартов поведения компилятора. Этот параметр отключает разрешающее поведение и устанавливает параметры компилятора [/Zc](zc-conformance.md) для более строгего соответствия. В интегрированной среде разработки этот параметр также делает подчеркивание подсистемой IntelliSense несогласованным кодом.

По умолчанию параметр **/permissive-** задается в новых проектах, созданных Visual Studio 2017 версии 15,5 и более поздних версий. По умолчанию он не задан в более ранних версиях. Если задан параметр, компилятор создает диагностические ошибки или предупреждения при обнаружении нестандартных конструкций языка в коде, включая некоторые распространенные ошибки в коде pre-C + 11.

Параметр **/permissive-** совместим с практически всеми файлами заголовков из последних комплектов Windows, таких как пакет средств разработки программного обеспечения (SDK) или Windows Driver Kit (WDK), начиная с пакета SDK для дизайнеров Windows (10.0.16299.0). Более старые версии пакета SDK могут не компилироваться в **/permissive-** для различных целей обеспечения соответствия исходного кода. Компилятор и пакеты SDK поставляются на разных временных шкалах выпуска, поэтому существуют некоторые другие проблемы. Конкретные проблемы с файлами заголовков см. ниже в разделе [проблемы с заголовком Windows](#windows-header-issues) .

Параметр **/permissive-** задает параметры [/Zc: referenceBinding](zc-referencebinding-enforce-reference-binding-rules.md), [/Zc: strictStrings](zc-strictstrings-disable-string-literal-type-conversion.md)и [/Zc: rvalueCast](zc-rvaluecast-enforce-type-conversion-rules.md) для согласования поведения. Эти параметры по умолчанию имеют несогласованное поведение. Чтобы переопределить это поведение, можно передать определенные параметры **/Zc** после **/permissive-** в командной строке.

В версиях компилятора, начиная с Visual Studio 2017 версии 15,3, параметр **/permissive-** устанавливает параметр [/Zc: ternary](zc-ternary.md) . Компилятор также реализует больше требований к состановке имен с двумя этапами. Если задан параметр **/permissive-** , компилятор анализирует определения шаблонов функций и классов и определяет зависимые и независимые имена, используемые в шаблонах. В этом выпуске выполняется только анализ зависимостей имен.

Модули, зависящие от среды, и языковые области, на которые стандарт оставляет реализацию, не затрагиваются **/permissive-** . Например, ключевые слова, связанные `__declspec`с корпорацией Майкрософт, соглашением о вызовах и структурированной обработкой исключений, а также директивы pragma или атрибуты, относящиеся к компилятору, не помечаются компилятором в режиме **/permissive-** .

Параметр **/permissive-** использует поддержку соответствия в текущей версии компилятора, чтобы определить, какие языковые конструкции не являются согласованными. Параметр не определяет, соответствует ли код определенной версии C++ стандарта. Чтобы включить поддержку всех реализованных компиляторов для последнего чернового стандарта, используйте параметр [/std: Latest](std-specify-language-standard-version.md) . Чтобы ограничить поддержку компилятора на текущий реализованный стандарт C++ 17, используйте параметр [/std: c++ 17](std-specify-language-standard-version.md) . Чтобы обеспечить более точное соответствие поддержки компилятора стандарту C++ 14, используйте параметр [/std: c++ 14](std-specify-language-standard-version.md) , который является значением по умолчанию.

Не все стандарты C++ 11, C++ 14 или C++ 17 поддерживаются компилятором КОМПИЛЯТОРОМ MSVC во всех версиях Visual Studio 2017. В зависимости от версии Visual Studio параметр **/permissive-** может не обнаруживать проблемы, связанные с некоторыми аспектами поиска имен с двумя этапами, привязывая неконстантную ссылку на временную, соблюдая инициализацию копирования в качестве прямой инициализации, разрешая несколько определяемых пользователем преобразования в инициализации или альтернативные токены для логических операторов и другие неподдерживаемые области соответствия. Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md). Чтобы максимально эффективно воспользоваться **/permissive-** , обновите Visual Studio до последней версии.

### <a name="how-to-fix-your-code"></a>Как исправить код

Ниже приведено несколько примеров кода, которые обнаруживаются как не соответствующие требованиям при использовании **/permissive-** , а также предлагаются способы устранения проблем.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Использовать значение по умолчанию в качестве идентификатора в машинном коде

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Поиск элементов в зависимом базовом

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

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Инициализация нескольких членов Union в инициализаторе члена

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

#### <a name="hidden-friend-name-lookup-rules"></a>Правила поиска скрытых дружественных имен

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

#### <a name="use-scoped-enums-in-array-bounds"></a>Использование перечислений с областью действия в границах массива

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Использование for each в машинном коде

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Неоднозначные аргументы условного оператора

В версиях компилятора перед Visual Studio 2017 версии 15,3 компилятор принимает аргументы в условный оператор (или оператор ternary) `?:` , который считается неоднозначным по стандарту. В режиме **/permissive-** компилятор теперь выдает одну или несколько диагностических сведений в случаях, скомпилированных без диагностики в более ранних версиях.

Ниже перечислены распространенные ошибки, которые могут быть результатом этого изменения.

- Ошибка C2593: "оператор?" неоднозначно

- Ошибка C2679: двоичный "?": не найден оператор, принимающий правый операнд типа "B" (или приемлемое преобразование отсутствует)

- Ошибка C2678: binary "?": не найден оператор, принимающий левый операнд типа "A" (или приемлемое преобразование)

- Ошибка C2446: ":": нет преобразования из "B" в "A"

Типичный шаблон кода, который может вызвать эту неполадку, заключается в том, что некоторый класс C предоставляет как неявный конструктор из другого типа T, так и оператор неявного преобразования для типа T. В этом случае преобразование второго аргумента в тип третьего аргумента и преобразование третьего аргумента в тип второго аргумента являются допустимыми преобразованиями. Так как оба значения являются допустимыми, они являются неоднозначными в соответствии со стандартом.

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

Существует важное исключение из этого общего шаблона, когда T представляет один из строковых типов, завершающихся нулем ( `const char *` `const char16_t *`например,, и т. д.) `?:` , а фактический аргумент — это строковый литерал соответствующего типа. В c++ 17 была изменена семантика с C++ 14. В результате код в примере 2 принимается в **/std: c++ 14** и отклоняется в **/std: c++ 17** при использовании параметра **/Zc: ternary** или **/permissive-** .

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

Другой случай, когда ошибки могут возникнуть в условных операторах с одним аргументом `void`типа. Этот вариант может быть распространен в макросах, подобных УТВЕРЖДЕНию.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Вы также можете увидеть ошибки в шаблоне метапрограммирование, где типы результатов условного оператора могут измениться в разделе **/Zc: ternary** and **/permissive-** . Одним из способов устранения этой проблемы является использование [std:: remove_reference](../../standard-library/remove-reference-class.md) для результирующего типа.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>Два этапа поиска имен

Если задан параметр **/permissive-** , компилятор анализирует определения шаблонов функций и классов, определяя зависимые и независимые имена, используемые в шаблонах в соответствии с требованиями для поиска имен с двумя этапами. В Visual Studio 2017 версии 15,3 выполняется анализ зависимостей имен. В частности, независимые имена, не объявленные в контексте определения шаблона, вызывают диагностическое сообщение согласно требованиям стандартов ISO C++ . В Visual Studio 2017 версии 15,7 привязка независимых имен, требующих от аргумента поиска в контексте определения, также выполняется.

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

Если требуется использовать устаревшее поведение для двухэтапного поиска, но в противном случае требуется **/permissive-** поведение, добавьте параметр **/Zc: twoPhase** .

### <a name="windows-header-issues"></a>Проблемы с заголовком Windows

Параметр **/permissive-** имеет слишком малое значение для версий комплектов Windows до пакета SDK обновления Windows (10.0.16299.0) или набора драйверов Windows (WDK) версии 1709. Мы рекомендуем выполнить обновление до последних версий комплектов Windows, чтобы использовать **/permissive-** в коде драйвера Windows или устройства.

Некоторые файлы заголовков в пакете SDK для Windows от апреля 2018 с обновлением (10.0.17134.0), пакет SDK для дизайнеров Windows (10.0.16299.0) или набор драйверов Windows (WDK) 1709, по-прежнему имеют проблемы, которые делают их несовместимыми с использованием **/permissive-** . Чтобы обойти эти проблемы, рекомендуется ограничить использование этих заголовков только теми файлами исходного кода, которые им требуются, и удалить параметр **/permissive-** при компиляции этих файлов исходного кода.

Эти заголовки WRL WinRT, выпущенные в пакете SDK для обновлений Windows от апреля 2018 (10.0.17134.0), не удаляются с **/permissive-** . Чтобы обойти эти проблемы, либо не используйте **/permissive-** , либо используйте **/permissive-** с параметром **/Zc: twoPhase-** при работе с этими заголовками:

- Проблемы в WinRT/WRL/Async. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Проблемы в WinRT/WRL/Implements. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Эти заголовки пользовательского режима, выпущенные в пакете SDK для Windows от апреля 2018 с обновлением (10.0.17134.0), не являются чистыми с **/permissive-** . Чтобы обойти эти проблемы, не используйте **/permissive-** при работе с этими заголовками:

- Проблемы в UM/настройке. h

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Проблемы в UM/спддкхлп. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Проблемы в UM/рефптрко. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Эти проблемы относятся к заголовкам пользовательского режима в пакете SDK обновления Windows для дизайнеров (10.0.16299.0):

- Проблемы в UM/Query. h

   При использовании параметра `tagRESTRICTION` компилятора/permissive-структура не компилируется из-за элемента Case (рТор) или.

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

   Чтобы устранить эту ошибку, Скомпилируйте файлы, содержащие Query. h, без параметра **/permissive-** .

- Проблемы в UM/cellularapi_oem. h

   При использовании параметра компилятора **/permissive-** переупреждающее объявление `enum UICCDATASTOREACCESSMODE` вызывает предупреждение:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Прямым объявлением неограниченного перечисления является расширение Майкрософт. Чтобы устранить эту ошибку, Скомпилируйте файлы, содержащие cellularapi_oem. h, без параметра **/permissive-** , или используйте параметр [/WD](compiler-option-warning-level.md) для бездействия предупреждения C4471.

- Проблемы в UM/омскрипт. h

   В C++ 03 преобразование строкового литерала в BSTR (typedef для "wchar_t *") является нерекомендуемым, но допустимым. В C++ 11 преобразование больше не разрешено.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Чтобы устранить эту ошибку, Скомпилируйте файлы, содержащие омскрипт. h, без параметра **/permissive-** , или используйте параметр **/Zc: strictStrings** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

В Visual Studio 2017 версии 15,5 и более поздних версиях используйте следующую процедуру:

1. Откройте диалоговое окно **страницы свойств** проекта.

1. Выберите страницу свойств **конфигурации** > **C/C++**  > **Language** .

1. Измените значение свойства **режим соответствия** на **Да (/permissive-)** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

В версиях до Visual Studio 2017 версии 15,5 Используйте следующую процедуру:

1. Откройте диалоговое окно **страницы свойств** проекта.

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++**  > **Командная строка**.

1. В поле **Дополнительные параметры** введите параметр компилятора **/permissive-** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)\
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
