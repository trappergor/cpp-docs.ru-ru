---
title: Класс com::ptr
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: 8909f91e31279f1fc1395610aea4708b79731113
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805972"
---
# <a name="comptr-class"></a>Класс com::ptr

Оболочка для COM-объекта, который может использоваться как член класса CLR.  Оболочки также позволяет автоматизировать управление жизненным циклом COM-объекта, освобождая все собственные ссылки объекта, когда его деструктора. Аналогично [класс CComPtr](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Синтаксис

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Параметры

*_interface_type*<br/>
COM-интерфейс.

## <a name="remarks"></a>Примечания

Объект `com::ptr` также может быть использована как переменная локальной функции для упрощения задач различных COM и автоматизировать управление жизненным циклом.

Объект `com::ptr` нельзя использовать непосредственно в качестве параметра функции, используйте [оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md) или [оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) вместо этого.

Объект `com::ptr` не возвращается из функции напрямую; вместо этого используйте дескриптор.

## <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  Вызывая открытые методы класса результатов в вызовах содержащегося `IXMLDOMDocument` объекта.  Образец создает экземпляр XML-документа, заполняет его простой XML-код и упрощенный обход узлов в дереве синтаксического анализа документа для печати XML на консоль.

```cpp
// comptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into the document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // simplified function to write just the first xml node to the console
   void WriteXml() {
      IXMLDOMNode* pNode = NULL;

      try {
         // the first child of the document is the first real xml node
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            WriteNode(pNode);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(IXMLDOMNode* pNode) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteXml();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<word>persnickety</word>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание:| 
|---------|-----------| 
|[ptr::ptr](#ptr)|Создает `com::ptr` программы-оболочки COM-объекта.| 
|[ptr::~ptr](#tilde-ptr)|Destructs `com::ptr`.| 

### <a name="public-methods"></a>Открытые методы

|name|Описание:|
|---------|-----------| 
|[ptr::Attach](#attach)|Присоединяет COM-объекту `com::ptr`.| 
|[ptr::CreateInstance](#createInstance)|Создает экземпляр COM-объекта в `com::ptr`.| 
|[ptr::Detach](#detach)|Отдает владения объектом COM, возвращающая указатель на объект.| 
|[ptr::GetInterface](#getInterface)|Создает экземпляр COM-объекта в `com::ptr`.| 
|[ptr::QueryInterface](#queryInterface)|Запрашивает собственный объект COM для интерфейса и прикрепляет результаты в другой `com::ptr`.| 
|[ptr::Release](#release)|Освобождает все собственные ссылки на COM-объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание:|
|---------|-----------| 
|[PTR::operator-&gt;](#operator-arrow)|Оператор доступа к члену, используемый для вызова методов для собственных COM-объекта.| 
|[ptr::operator=](#operator-assign)|Присоединяет COM-объекту `com::ptr`.| 
|[PTR::operator&nbsp;bool](#operator-bool)|Оператор для использования `com::ptr` в условном выражении.| 
|[ptr::operator!](#operator-logical-not)|Оператор, чтобы определить, если собственный объект COM является недопустимым.| 

## <a name="requirements"></a>Требования

**Header file** \<msclr\com\ptr.h>

**Пространство имен** msclr::com

 

## <a name="ptr"></a>ptr::ptr

Возвращает указатель на принадлежащий COM-объекта.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель интерфейса COM.

### <a name="remarks"></a>Примечания

Конструктор без аргументов присваивает `nullptr` на базовый дескриптор объекта. Вызовы будущего `com::ptr` будут проверены внутренний объект и автоматически ошибкой, пока не будет создан или присоединенного объекта.

Один аргумент конструктора добавляет ссылку на COM-объекта, но не освобождает ссылку вызывающей стороны, чтобы вызывающий объект должен вызвать `Release` для COM-объекта по-настоящему теряете контроль. При `com::ptr`его деструктор вызывается автоматически освобождает ссылки COM-объекта.

Передача `NULL` в этот конструктор является таким же, как вызывать версию без аргументов.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. Он демонстрирует использование обеих версий конструктора.

```cpp
// comptr_ptr.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="tilde-ptr"></a>PTR:: ~ ptr

Destructs `com::ptr`.

```cpp
~ptr();
```

### <a name="remarks"></a>Примечания

При уничтожении объекта `com::ptr` высвобождает все ссылки, которые ему принадлежат к COM-объекта. При условии, что нет других ссылок, хранящиеся на COM-объект, COM-объекта будут удалены и освободить память.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  В `main` функция, два `XmlDocument` деструкторы объектов будет вызываться, когда они выходят за пределы области `try` блок, полученный в базовом `com::ptr` деструктор вызывается, освобождения всех собственных ссылок на COM объект.

```cpp
// comptr_dtor.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="attach"></a>PTR::Attach

Присоединяет COM-объекту `com::ptr`.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель на интерфейс COM для присоединения.

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылку на COM-объект `Attach` вызывает <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Примечания

Вызов `Attach` ссылается на объект COM, но не освобождает вызывающего ссылку на него.

Передача `NULL` для `Attach` приводит не будет предпринято никаких действий.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `ReplaceDocument` Функция-член первого вызывает `Release` для какого-либо прежде был владельцем объекта, а затем вызывает `Attach` для присоединения объекта документа.

```cpp
// comptr_attach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="createInstance"></a>ptr::CreateInstance

Создает экземпляр COM-объекта в `com::ptr`.

```cpp
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   System::String ^ progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   System::String ^ progid
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   const wchar_t * progid,
   LPUNKNOWN pouter
);
void CreateInstance(
   const wchar_t * progid
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter,
   DWORD cls_context
);
void CreateInstance(
   REFCLSID rclsid,
   LPUNKNOWN pouter
);
void CreateInstance(
   REFCLSID rclsid
);
```

### <a name="parameters"></a>Параметры

*progid*<br/>
Строка `ProgID`.

*pouter*<br/>
Указатель на интерфейс IUnknown агрегатного объекта (управляющий IUnknown). Если `pouter` не указан, `NULL` используется.

*cls_context*<br/>
Контекст, в котором будет выполняться код, который управляет вновь созданный объект. Значения берутся из `CLSCTX` перечисления. Если `cls_context` не указан, значение, используемое CLSCTX_ALL.

*rclsid*<br/>
`CLSID` связанный с данными и кодом, который будет использоваться для создания объекта.

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылку на COM-объект `CreateInstance` вызывает <xref:System.InvalidOperationException>.

Эта функция вызывает `CoCreateInstance` и использует <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> преобразовать любой ошибки `HRESULT` в соответствующее исключение.

### <a name="remarks"></a>Примечания

`CreateInstance` использует `CoCreateInstance` для создания нового экземпляра заданного объекта, определяемого с ProgID или CLSID. `com::ptr` Ссылается на вновь созданный объект и автоматически освобождает все собственные ссылки после уничтожения.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. Конструкторы класса использовать два различных вида `CreateInstance` для создания объекта документа, ProgID или CLSID, а также CLSCTX.

```cpp
// comptr_createinstance.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }
   XmlDocument(REFCLSID clsid, DWORD clsctx) {
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc1("Msxml2.DOMDocument.3.0");

      // or from a clsid with specific CLSCTX
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

## <a name="detach"></a>PTR::Detach

Отдает владения объектом COM, возвращающая указатель на объект.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на COM-объекта.

Если объект не имеет владельца, возвращается значение NULL.

### <a name="exceptions"></a>Исключения

На внутреннем уровне `QueryInterface` вызывается на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение, <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Примечания

`Detach` Сначала добавляется ссылка на COM-объект, от лица абонента и освобождает все ссылки, принадлежащие `com::ptr`.  В конечном счете, вызывающий объект должен освободить возвращаемый объект уничтожить его.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  `DetachDocument` Функция-член вызывает `Detach` сдаться владения COM-объекта и возвращает указатель на вызывающий объект.

```cpp
// comptr_detach.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

## <a name="getInterface"></a>PTR::GetInterface

Возвращает указатель на принадлежащий COM-объекта.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на принадлежащий COM-объекта.

### <a name="exceptions"></a>Исключения

На внутреннем уровне `QueryInterface` вызывается на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение, <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Примечания

`com::ptr` Добавляет ссылку на COM-объект для вызывающего объекта, а также обеспечивает собственную ссылку на COM-объекта. Вызывающий объект в конечном счете необходимо освободить ссылку для возвращенного объекта или никогда не будут уничтожены.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `GetDocument` Функция-член использует `GetInterface` для возврата указателя на COM-объект.

```cpp
// comptr_getinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="queryInterface"></a>PTR::QueryInterface

Запрашивает собственный объект COM для интерфейса и прикрепляет результаты в другой `com::ptr`.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Параметры

*other*<br/>
`com::ptr` , Получите интерфейс.

### <a name="exceptions"></a>Исключения

На внутреннем уровне `QueryInterface` вызывается на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение, <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Примечания

Используйте этот метод для создания оболочки COM для другой интерфейс COM-объекта, принадлежащие текущей программой-оболочкой. Этот метод вызывает метод `QueryInterface` через принадлежащий COM-объект, чтобы запросить указатель на конкретный интерфейс COM-объекта и присоединяет возвращаемый указатель интерфейса для переданного `com::ptr`.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `WriteTopLevelNode` Функция-член использует `QueryInterface` для заполнения локальной `com::ptr` с `IXMLDOMNode` , а затем передает `com::ptr` (по отслеживаемая ссылка) на функцию закрытый член, которая записывает имя и текст свойства узла на консоль.

```cpp
// comptr_queryinterface.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   void LoadXml(String^ xml) {
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);
      BSTR bstr = NULL;

      try {
         // load some XML into our document
         bstr = ::SysAllocString(pinnedXml);
         if (NULL == bstr) {
            throw gcnew OutOfMemoryException;
         }
         VARIANT_BOOL bIsSuccessful = false;
         // use operator -> to call IXMODOMDocument member function
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   // write the top level node to the console
   void WriteTopLevelNode() {
      com::ptr<IXMLDOMNode> ptrNode;

      // query for the top level node interface
      m_ptrDoc.QueryInterface(ptrNode);
      WriteNode(ptrNode);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   // simplified function that only writes the node
   void WriteNode(com::ptr<IXMLDOMNode> % node) {
      BSTR bstr = NULL;

      try {
         // write out the name and text properties
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));
         String^ strName = gcnew String(bstr);
         Console::Write("<{0}>", strName);
         ::SysFreeString(bstr);
         bstr = NULL;

         Marshal::ThrowExceptionForHR(node->get_text(&bstr));
         Console::Write(gcnew String(bstr));
         ::SysFreeString(bstr);
         bstr = NULL;

         Console::WriteLine("</{0}>", strName);
      }
      finally {
         ::SysFreeString(bstr);
      }
   }

   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // stream some xml into the document
      doc.LoadXml("<word>persnickety</word>");

      // write the document to the console
      doc.WriteTopLevelNode();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
<#document>persnickety</#document>
```

## <a name="release"></a>PTR::Release

Освобождает все собственные ссылки на COM-объекта.

```cpp
void Release();
```

### <a name="remarks"></a>Примечания

Вызов этой функции освобождает все собственные ссылки на COM-объект и задает внутренний дескриптор COM-объект для `nullptr`.  При отсутствии других ссылок на COM-объект, он будет уничтожен.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  `ReplaceDocument` Функция-член использует `Release` для освобождения объекта любого предыдущего документа перед присоединением новый документ.

```cpp
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-arrow"></a>PTR::operator-&gt;

Оператор доступа к члену, используемый для вызова методов для собственных COM-объекта.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `smart_com_ptr` COM-объект.

### <a name="exceptions"></a>Исключения

На внутреннем уровне `QueryInterface` вызывается на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение, <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Примечания

Этот оператор позволяет вызывать методы, принадлежащий COM-объекта. Она возвращает временную `smart_com_ptr` , автоматически обрабатывает собственный `AddRef` и `Release`.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `WriteDocument` Функция использует `operator->` для вызова `get_firstChild` члена объекта документа.

```cpp
// comptr_op_member.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));
            String^ strName = gcnew String(bstr);
            Console::Write("<{0}>", strName);
            ::SysFreeString(bstr);
            bstr = NULL;

            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));
            Console::Write(gcnew String(bstr));
            ::SysFreeString(bstr);
            bstr = NULL;

            Console::WriteLine("</{0}>", strName);
         }
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }

   }
}
```

```Output
<word>persnickety</word>
```

## <a name="operator-assign"></a>PTR::operator =

Присоединяет COM-объекту `com::ptr`.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель на интерфейс COM для присоединения.

### <a name="return-value"></a>Возвращаемое значение

Отслеживаемая ссылка на `com::ptr`.

### <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылку на COM-объект `operator=` вызывает <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Примечания

Назначение COM-объекту `com::ptr` ссылается на объект COM, но не освобождает вызывающего ссылку на него.

Этот оператор имеет тот же эффект, что `Attach`.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  `ReplaceDocument` Функция-член первого вызывает `Release` для какого-либо прежде был владельцем объекта, а затем используется `operator=` для присоединения объекта документа.

```cpp
// comptr_op_assign.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="operator-bool"></a> PTR::operator bool

Оператор для использования `com::ptr` в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если собственный объект COM является допустимым; `false` в противном случае.

### <a name="remarks"></a>Примечания

Собственный объект COM допустим, если это не `nullptr`.

Этот оператор преобразует `_detail_class::_safe_bool` которого является более безопасным, чем `bool` , так как он не может быть преобразован в целочисленный тип.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `CreateInstance` Функция-член использует `operator bool` после создания нового объекта документа, чтобы определить, если он является допустимым и выводит на консоль в том случае, если это.

```cpp
// comptr_op_bool.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) { // uses operator bool
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```

## <a name="operator-logical-not"></a>PTR::operator!

Оператор, чтобы определить, если собственный объект COM является недопустимым.

```cpp
bool operator!();
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если собственный объект COM является недопустимым; `false` в противном случае.

### <a name="remarks"></a>Примечания

Собственный объект COM допустим, если это не `nullptr`.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  `CreateInstance` Функция-член использует `operator!` чтобы определить, использует ли объект документа уже есть владелец и создает новый экземпляр, только если объект является недопустимым.

```cpp
// comptr_op_not.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   void CreateInstance(String^ progid) {
      if (!m_ptrDoc) {
         m_ptrDoc.CreateInstance(progid);
         if (m_ptrDoc) {
            Console::WriteLine("DOM Document created.");
         }
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   try {
      XmlDocument doc;
      // create the instance from a progid string
      doc.CreateInstance("Msxml2.DOMDocument.3.0");
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
}
```

```Output
DOM Document created.
```
