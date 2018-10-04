---
title: Атрибут программирование часто задаваемые вопросы | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a93dc67bd06f0dc88603643646fed3ad65052874
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792228"
---
# <a name="attribute-programming-faq"></a>Атрибутивное программирование. Часто задаваемые вопросы

В этом разделе содержатся ответы на следующие часто задаваемые вопросы:

- [Что такое значение HRESULT](#vcconattributeprogrammmingfaqanchor1)

- [Если необходимо указать имя параметра для атрибута?](#vcconattributeprogrammmingfaqanchor2)

- [Можно использовать комментарии в блоке атрибута?](#vcconattributeprogrammmingfaqanchor3)

- [Как атрибуты взаимодействуют с наследованием?](#vcconattributeprogrammmingfaqanchor4)

- [Как использовать атрибуты в проекте ATL без атрибутов?](#vcconattributeprogrammmingfaqanchor5)

- [Как использовать IDL-файл в проекте с атрибутами?](#vcconattributeprogrammmingfaqanchor6)

- [Можно изменить код, который вставлен с помощью атрибута?](#vcconattributeprogrammmingfaqanchor7)

- [Как пересылать объявить интерфейсе с атрибутами?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Можно использовать атрибуты в классе, производном от класса, который также использует атрибуты](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

##  <a name="vcconattributeprogrammmingfaqanchor1"></a> Что такое значение HRESULT

Значение HRESULT является простой тип данных, часто используется в качестве возвращаемого значения атрибутов и ATL в целом. В следующей таблице описаны различные значения. Дополнительные значения содержатся в файле winerror.h файл заголовка.

|name|Описание|Значение|
|----------|-----------------|-----------|
|S_OK|Операция выполнена успешно|0x00000000|
|E_UNEXPECTED|Непредвиденная ошибка|0x8000FFFF|
|E_NOTIMPL|Не реализовано|0x80004001|
|E_OUTOFMEMORY|Не удалось выделить необходимую память|0x8007000E|
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми|0x80070057|
|E_NOINTERFACE|Интерфейс не поддерживается|0x80004002|
|E_POINTER|Недопустимый указатель|0x80004003|
|E_HANDLE|Недопустимый дескриптор|0x80070006|
|E_ABORT|Операция прервана|0x80004004|
|E_FAIL|Неизвестная ошибка|0x80004005|
|E_ACCESSDENIED|Ошибка доступа|0x80070005|

##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Если необходимо указать имя параметра для атрибута?

В большинстве случаев Если атрибут имеет один параметр, этот параметр называется. Это имя не требуется при вставке атрибутов в коде. Например, следующее использование [статистическую обработку](aggregatable.md) атрибут:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

именно так же, как:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Тем не менее следующие атрибуты имеют единый, неименованные параметры:

||||
|-|-|-|
|[call_as](call-as.md)|[case](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[default](default-cpp.md)|[defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[entry](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[helpfile](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[helpstringdll](helpstringdll.md)|[id](id.md)|
|[iid_is](iid-is.md)|[import](import.md)|[importlib](importlib.md)|
|[include](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[restricted](restricted.md)|
|[size_is](size-is.md)|[source](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Можно использовать комментарии в блоке атрибута?

Можно использовать однострочные и многострочные комментарии в блоке атрибута. Тем не менее нельзя использовать либо стиль комментария в круглых скобках, содержащий параметры для атрибута.

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

##  <a name="vcconattributeprogrammmingfaqanchor4"></a> Как атрибуты взаимодействуют с наследованием?

Классы с атрибутом и неопределенными может наследовать от других классов, которые могут сами быть атрибуты или нет. Результат использования производного от класса с атрибутом является производным от этого класса, после поставщик атрибутов изменила свой код. Атрибуты, не передаются по производные классы через наследование C++. Поставщик атрибутов только преобразует код вблизи его атрибуты.

##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Как использовать атрибуты в проекте ATL без атрибутов?

Возможно, проект ATL без атрибутов, который IDL-файле, и можно приступить к добавлению помеченных атрибутами объектов. В этом случае следует использовать **мастер добавления класса** для предоставления кода.

##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Как использовать IDL-файл в проекте с атрибутами?

Возможно IDL-файла, который вы хотите использовать в проекте ATL с атрибутами. В этом случае используется [importidl](importidl.md) атрибут, для компиляции в IDL-файл h-файл (см. в разделе [страницы свойств MIDL](../../ide/midl-property-pages.md) в проекте **страницы свойств** диалоговое окно), и Включите h-файл в проект.

##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Можно изменить код, который вставлен с помощью атрибута?

Некоторые атрибуты вставки кода в проекте. Этот код можно просмотреть с помощью [/Fx](../../build/reference/fx-merge-injected-code.md) параметр компилятора. Можно также скопировать код из внедренного файла и вставьте его в исходном коде. Это позволяет изменять поведение атрибута. Тем не менее может потребоваться изменить другие части кода также.

Следующий пример является результатом копирования введенного кода в файл исходного кода:

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

##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Как пересылать объявить интерфейсе с атрибутами?

Если вы собираетесь сделать у прямого объявления интерфейсе с атрибутами, необходимо применить те же атрибуты для опережающего объявления, относящиеся к объявлению фактический интерфейс. Необходимо также применить [Экспорт](export.md) для вашей опережающего объявления атрибута.

##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Можно использовать атрибуты в классе, производном от класса, который также использует атрибуты

Нет, с помощью атрибутов в классе, производном от класса, который также использует атрибуты не поддерживается.

## <a name="see-also"></a>См. также

[Атрибуты C++ для COM и .NET](cpp-attributes-com-net.md)