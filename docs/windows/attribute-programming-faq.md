---
title: Атрибут часто задаваемые вопросы по программированию | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35b57c8813778cf0bbf8efbfcbee8466074b87f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="attribute-programming-faq"></a>Атрибутивное программирование. Часто задаваемые вопросы
В этом разделе ответы на следующие вопросы:  
  
-   [Что такое значение HRESULT](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Если нужно указать имя параметра для атрибута?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Можно использовать комментарии в блоке атрибута?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [Как атрибуты взаимодействуют с наследованием?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Использование атрибутов в проект ATL без атрибутов](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Как использовать IDL-файл в проекте с атрибутами](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Можно изменить код, который вставлен с помощью атрибута](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Как опережающее объявление интерфейсе с атрибутами?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Можно использовать атрибуты для класса, производного от класса, который также использует атрибуты](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> Что такое значение HRESULT  
 `HRESULT` Является простой тип данных, часто используется в качестве возвращаемого значения атрибутов и ATL в целом. В следующей таблице описаны различные значения. Дополнительные значения содержатся в файле winerror.h файла заголовка.  
  
|name|Описание|Значение|  
|----------|-----------------|-----------|  
|S_OK|Операция выполнена успешно|0x00000000|  
|E_UNEXPECTED|Непредвиденная ошибка|0x8000FFFF|  
|E_NOTIMPL|Не реализовано|0x80004001|  
|E_OUTOFMEMORY|Не удалось выделить необходимую память|0x8007000E|  
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми|0x80070057|  
|E_NOINTERFACE|Интерфейс не поддерживается|0x80004002|  
|E_POINTER|Недопустимый указатель|отметкой 0x80004003|  
|E_HANDLE|Недопустимый дескриптор|0x80070006|  
|E_ABORT|Операция прервана|0x80004004|  
|E_FAIL|Неизвестная ошибка|0x80004005|  
|E_ACCESSDENIED|Ошибка доступа|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Если нужно указать имя параметра для атрибута?  
 В большинстве случаев Если атрибут имеет один параметр, именем этого параметра. Это имя не требуется при вставке атрибута в коде. Например, следующее использование [статистическую обработку](../windows/aggregatable.md) атрибута:  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 именно таким же, как:  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Однако следующие атрибуты имеют один неименованные параметры:  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entry](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[id](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[include](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[Источник](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Можно использовать комментарии в блоке атрибута?  
 Можно использовать однострочный и многострочный комментарии в блоке атрибутов. Тем не менее нельзя использовать либо стиль комментария в круглых скобках, содержащий параметры для атрибута.  
  
 Следующее выражение допустимо:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Следующие запрещено.  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> Как атрибуты взаимодействуют с наследованием?  
 Атрибутами и неопределенные классы могут наследовать другие классы, которые могут сами быть атрибуты или нет. Результат наследование от класса с атрибутом является производным от этого класса, после атрибута поставщика обеспечит его код. Атрибуты не передаются производных классов через наследование C++. Только поставщика атрибутов преобразует код вблизи его атрибуты.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Использование атрибутов в проект ATL без атрибутов  
 Возможно, проект ATL без атрибутов, который IDL-файл, и можно начать добавлять атрибутами объектов. В этом случае используйте мастер добавления класса предоставления кода.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Как использовать IDL-файл в проекте с атрибутами  
 Имеется IDL-файл, который вы хотите использовать в проекте ATL с атрибутами. В этом случае используется [importidl](../windows/importidl.md) атрибута, компиляции IDL-файла h-файл (см. [страницы свойств MIDL](../ide/midl-property-pages.md) в диалоговом окне страницы свойств проекта) и включите h-файл в проект .  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Можно изменить код, который вставлен с помощью атрибута  
 Некоторые атрибуты вводят кода в проекте. Этот код можно просмотреть с помощью [/Fx](../build/reference/fx-merge-injected-code.md) параметр компилятора. Можно также скопировать код из внедренного файла и вставьте его в исходный код. Это позволяет изменять поведение атрибута. Тем не менее может потребоваться изменить другие части кода также.  
  
 Следующий пример является результатом копирования введенный код в файл исходного кода:  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
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
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Как опережающее объявление интерфейсе с атрибутами?  
 Если планируется сделать опережающее объявление интерфейсе с атрибутами, необходимо применить те же атрибуты для опережающего объявления, применяются к объявлению реального интерфейса. Необходимо также применить [Экспорт](../windows/export.md) для вашей опережающего объявления атрибута.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Можно использовать атрибуты для класса, производного от класса, который также использует атрибуты  
 Нет, с помощью атрибутов в классе, производном от класса, который также использует атрибуты не поддерживается.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../windows/attributed-programming-concepts.md)