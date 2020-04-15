---
title: Атрибутивное программирование. Часто задаваемые вопросы
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: 6c1762994d2cb109e86397bb0a5db1258cf33be2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376066"
---
# <a name="attribute-programming-faq"></a>Атрибутивное программирование. Часто задаваемые вопросы

Эта тема отвечает на следующие часто задаваемые вопросы:

- [Что такое HRESULT?](#vcconattributeprogrammmingfaqanchor1)

- [Когда нужно указать имя параметра для атрибута?](#vcconattributeprogrammmingfaqanchor2)

- [Могу ли я использовать комментарии в блоке атрибутов?](#vcconattributeprogrammmingfaqanchor3)

- [Как атрибуты взаимодействуют с наследованием?](#vcconattributeprogrammmingfaqanchor4)

- [Как использовать атрибуты в неприписываемом проекте ATL?](#vcconattributeprogrammmingfaqanchor5)

- [Как использовать файл .idl в приписываемом проекте?](#vcconattributeprogrammmingfaqanchor6)

- [Могу ли я изменить код, который вводится атрибутом?](#vcconattributeprogrammmingfaqanchor7)

- [Как я могу переделать объявление приписываемого интерфейса?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Могу ли я использовать атрибуты в классе, полученном из класса, который также использует атрибуты?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

## <a name="what-is-an-hresult"></a><a name="vcconattributeprogrammmingfaqanchor1"></a>Что такое HRESULT?

HRESULT — это простой тип данных, который часто используется в качестве значения возврата атрибутами и ATL в целом. В следующей таблице описаны различные значения. Дополнительные значения содержатся в файле заголовка winerror.h.

|Имя|Описание|Значение|
|----------|-----------------|-----------|
|S_OK|Операция выполнена успешно|0x00000000|
|E_UNEXPECTED|Неожиданный сбой|0x8000FFFF|
|E_NOTIMPL|Не реализовано|0x80004001|
|E_OUTOFMEMORY|Не удалось выделить необходимую память|0x8007000E|
|E_INVALIDARG|Один или несколько аргументов недействительны|0x80070057|
|E_NOINTERFACE|Нет такого интерфейса поддерживается|0x80004002|
|E_POINTER|Недействительный указатель|0x80004003|
|E_HANDLE|Недействительная ручка|0x80070006|
|E_ABORT|Операция прервана|0x80004004|
|E_FAIL|Неопределенный сбой|0x80004005|
|E_ACCESSDENIED|Общий доступ отказано в ошибке|0x80070005|

## <a name="when-do-i-have-to-specify-the-parameter-name-for-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor2"></a>Когда нужно указать имя параметра для атрибута?

В большинстве случаев, если атрибут имеет один параметр, этот параметр назван. Это имя не требуется при вставке атрибута в код. Например, следующее использование [агрегируемого](aggregatable.md) атрибута:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

точно так же, как:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Однако следующие атрибуты имеют одиночные, неназванные параметры:

||||
|-|-|-|
|[call_as](call-as.md)|[Случае](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[default](default-cpp.md)|[Defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[Запись](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[справочный файл](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[helpstringdll](helpstringdll.md)|[id](id.md)|
|[iid_is](iid-is.md)|[Импорт](import.md)|[importlib](importlib.md)|
|[Включают](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[Ограничен](restricted.md)|
|[size_is](size-is.md)|[Источник](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

## <a name="can-i-use-comments-in-an-attribute-block"></a><a name="vcconattributeprogrammmingfaqanchor3"></a>Могу ли я использовать комментарии в блоке атрибутов?

Вы можете использовать как однолинейные, так и многолинейные комментарии в блоке атрибута. Тем не менее, вы не можете использовать ни один из стилей комментариев в скобках, удерживая параметры к атрибуту.

Допускается следующее:

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

Не допускается следующее:

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

## <a name="how-do-attributes-interact-with-inheritance"></a><a name="vcconattributeprogrammmingfaqanchor4"></a>Как атрибуты взаимодействуют с наследованием?

Вы можете наследовать как приписываемые, так и неотнесенные классы из других классов, которые сами по себе могут быть отнесены или нет. Результат вывода из приписываемого класса такой же, как вывод из этого класса после того, как поставщик атрибутов изменил свой код. Атрибуты не передаются полученным классам через наследование СЗ. Поставщик атрибутов преобразует код только в непосредственной близости от его атрибутов.

## <a name="how-can-i-use-attributes-in-a-nonattributed-atl-project"></a><a name="vcconattributeprogrammmingfaqanchor5"></a>Как использовать атрибуты в неприписываемом проекте ATL?

У вас может быть неприписываемый проект ATL, в котором есть файл .idl, и вы можете начать добавлять приписываемые объекты. В этом случае используйте **«Волшебник добавленного класса»** для предоставления кода.

## <a name="how-can-i-use-an-idl-file-in-an-attributed-project"></a><a name="vcconattributeprogrammmingfaqanchor6"></a>Как использовать файл .idl в приписываемом проекте?

У вас может быть файл .idl, который вы хотите использовать в проекте ATL. В этом случае вы будете использовать атрибут [importidl,](importidl.md) компилировать файл .idl в файл .h (см. [страницы свойств MIDL](../../build/reference/midl-property-pages.md) в диалоговом поле **страниц свойств** проекта), а затем включить файл .h в свой проект.

## <a name="can-i-modify-code-that-is-injected-by-an-attribute"></a><a name="vcconattributeprogrammmingfaqanchor7"></a>Могу ли я изменить код, который вводится атрибутом?

Некоторые атрибуты вводят код в проект. Вы можете увидеть вводимый код с помощью опции компилятора [/Fx.](../../build/reference/fx-merge-injected-code.md) Также можно скопировать код из впрыскиваемого файла и вставить его в исходный код. Это позволяет изменить поведение атрибута. Тем не менее, возможно, вам придется изменить другие части кода, а также.

Следующий пример является результатом копирования вводили код в файл исходного кода:

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
]

class ATL_NO_VTABLE CTestTest : public ITestTest,
// the following base classes support added injected code
public IConnectionPointContainerImpl<CTestTest>,
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>
{
public:
   CTestTest() {
   }
   // this line would be commented out from original file
   // __event __interface _ITestTestEvents;
   DECLARE_PROTECT_FINAL_CONSTRUCT()
   HRESULT FinalConstruct() {
      return S_OK;
   }

void FinalRelease() {}

public:
   CComBSTR m_value;
   STDMETHOD(DoTest)(BSTR str) {
      VARIANT_BOOL bCancel = FALSE;
      BeforeChange(str,&bCancel);
      if (bCancel) {
          return Error("Error : Someone don't want us to change the value");
      }

   m_value =str;
   return S_OK;
    }
// the following was copied in from the injected code.
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {
   HRESULT hr = S_OK;
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;
   VARIANT rgvars[2];
   Lock();
   IUnknown** pp = p->m_vec.begin();
   Unlock();
   while (pp < p->m_vec.end()) {
      if (*pp != NULL) {
         IDispatch* pDispatch = (IDispatch*) *pp;
         ::VariantInit(&rgvars[1]);
         rgvars[1].vt = VT_BSTR;
         V_BSTR(&rgvars[1])= (BSTR) i1;
         ::VariantInit(&rgvars[0]);
         rgvars[0].vt = (VT_BOOL | VT_BYREF);
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };
         VARIANT ret_val;
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);
         if (FAILED(hr))
            break;
      }
      pp++;
   }
   return hr;
}

BEGIN_CONNECTION_POINT_MAP(CTestTest)
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))
END_CONNECTION_POINT_MAP()
// end added code section

// _ITestCtrlEvents Methods
public:
};

int main() {}
```

## <a name="how-can-i-forward-declare-an-attributed-interface"></a><a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a>Как я могу переделать объявление приписываемого интерфейса?

Если вы собираетесь сделать передовую декларацию приписываемого интерфейса, необходимо применить те же атрибуты к форвардной декларации, которая применяется к фактической декларации интерфейса. Вы также должны применить [экспортный](export.md) атрибут к своей форвардной декларации.

## <a name="can-i-use-attributes-on-a-class-derived-from-a-class-that-also-uses-attributes"></a><a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a>Могу ли я использовать атрибуты в классе, полученном из класса, который также использует атрибуты?

Нет, использование атрибутов на классе, полученном из класса, который также использует атрибуты, не поддерживается.

## <a name="see-also"></a>См. также раздел

[Атрибуты C++ для модели COM и .NET](cpp-attributes-com-net.md)
