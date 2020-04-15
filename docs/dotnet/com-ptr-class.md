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
ms.openlocfilehash: e494285f33cf282d7b7515aac374ec86ef3036b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372489"
---
# <a name="comptr-class"></a>Класс com::ptr

Обертка для объекта COM, который может быть использован в качестве члена класса CLR.  Обертка также автоматизирует управление продолжительностью жизни объекта COM, выпуская все принадлежащие ссылки на объект, когда вызывается его деструктор. Аналог [класса CComPtr](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Синтаксис

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Параметры

*_interface_type*<br/>
Интерфейс COM.

## <a name="remarks"></a>Remarks

A `com::ptr` также может использоваться в качестве локальной переменной функции для упрощения различных задач COM и автоматизации управления продолжительностью жизни.

A `com::ptr` не может быть использован непосредственно в качестве параметра функции; вместо этого использовать [оператора отслеживания или](../extensions/tracking-reference-operator-cpp-component-extensions.md) [ручку оператору объектов.](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)

A `com::ptr` не может быть непосредственно возвращен из функции; использовать ручку вместо.

## <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  Вызов общедоступных методов класса приводит к `IXMLDOMDocument` вызовам к содержащемуся объекту.  Образец создает экземпляр документа XML, заполняет его простым XML и делает упрощенную прогулку узлов в разогнанных деревьях документов для печати XML на консоль.

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

|Имя|Описание|
|---------|-----------|
|[ptr::ptr](#ptr)|Строит `com::ptr` для обертывания объекта COM.|
|[ptr::~ptr](#tilde-ptr)|Разрушает `com::ptr`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|---------|-----------|
|[ptr::Attach](#attach)|Прикрепляет объект COM `com::ptr`к .|
|[ptr::CreateInstance](#createInstance)|Создает экземпляр объекта COM в `com::ptr`пределах .|
|[ptr::Detach](#detach)|Отказывается от права собственности на объект COM, возвращая указатель на объект.|
|[ptr::GetInterface](#getInterface)|Создает экземпляр объекта COM в `com::ptr`пределах .|
|[ptr::QueryInterface](#queryInterface)|Запрашивает принадлежащий объект COM для интерфейса и `com::ptr`прикрепляет результат к другому.|
|[ptr::Release](#release)|Выпускает все принадлежащие ссылки на объект COM.|

### <a name="public-operators"></a>Публичные операторы

|Имя|Описание|
|---------|-----------|
|[ptr:оператор-&gt;](#operator-arrow)|Оператор доступа к членам, используемый для вызова методов на принадлежащем объекте COM.|
|[ptr::оператор](#operator-assign)|Прикрепляет объект COM `com::ptr`к .|
|[ptr::оператор&nbsp;бул](#operator-bool)|Оператор для `com::ptr` использования в условном выражении.|
|[ptr::operator!](#operator-logical-not)|Оператор, чтобы определить, является ли принадлежащий объект COM недействительным.|

## <a name="requirements"></a>Требования

**Файл** \<заголовка msclr-com-ptr.h>

**Namespace** msclr::com

## <a name="ptrptr"></a><a name="ptr"></a>ptr::ptr

Возвращает указатель на принадлежащий объект COM.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель интерфейса COM.

### <a name="remarks"></a>Remarks

Конструктор без аргумента присваивает `nullptr` основной ручке объекта. Будущие вызовы в `com::ptr` будет проверять внутренний объект и молча сбой, пока объект не будет создан или прикреплен.

Конструктор с одним аргументом добавляет ссылку на объект COM, но не выпускает ссылку вызываемого абонента, поэтому абонент должен обратиться к `Release` объекту COM, чтобы действительно отказаться от контроля. Когда `com::ptr`'s destructor вызывается, он автоматически выпускает свои ссылки на объект COM.

Переход `NULL` к этому конструктору - это то же самое, что вызвать версию без аргумента.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Он демонстрирует использование обеих версий конструктора.

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

## <a name="ptrptr"></a><a name="tilde-ptr"></a>ptr:::--ptr

Разрушает `com::ptr`.

```cpp
~ptr();
```

### <a name="remarks"></a>Remarks

При уничтожении, релизы `com::ptr` все ссылки он владеет на свой объект COM. Если предположить, что на объект COM нет других ссылок, объект COM будет удален, а его память освобождена.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  В `main` функции, `XmlDocument` деструкторов двух объектов будут вызваны, когда они `try` выходят из области `com::ptr` блока, в результате чего основной деструктор вызывается, выпуская все принадлежащие ссылки на объект COM.

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

## <a name="ptrattach"></a><a name="attach"></a>ptr::Attach

Прикрепляет объект COM `com::ptr`к .

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель интерфейса COM для крепления.

### <a name="exceptions"></a>Исключения

Если `com::ptr` у уже есть ссылка `Attach` на <xref:System.InvalidOperationException>объект COM, бросает .

### <a name="remarks"></a>Remarks

Вызов ссылки `Attach` на объект COM, но не выпускает ссылку вызываемого на него.

Переход `NULL` `Attach` к результатам не принимает никаких мер.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Функция `ReplaceDocument` участника сначала `Release` вызывает любой ранее `Attach` принадлежащий объект, а затем призывает прикрепить новый объект документа.

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

## <a name="ptrcreateinstance"></a><a name="createInstance"></a>ptr::СозданиеInstance

Создает экземпляр объекта COM в `com::ptr`пределах .

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

*Progid*<br/>
Строка `ProgID`.

*pouter*<br/>
Указатель на интерфейс IUnknown агрегата объекта (управление IUnknown). Если `pouter` не указано, `NULL` используется.

*cls_context*<br/>
Контекст, в котором будет работать код, управляющий вновь созданным объектом. Значения взяты из перечисления. `CLSCTX` Если `cls_context` не указано, используется значение CLSCTX_ALL.

*rclsid*<br/>
`CLSID`связанных с данными и кодом, которые будут использоваться для создания объекта.

### <a name="exceptions"></a>Исключения

Если `com::ptr` у уже есть ссылка `CreateInstance` на <xref:System.InvalidOperationException>объект COM, бросает .

Эта функция `CoCreateInstance` вызывает <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> и использует `HRESULT` для преобразования любой ошибки в соответствующее исключение.

### <a name="remarks"></a>Remarks

`CreateInstance`использует `CoCreateInstance` для создания нового экземпляра указанного объекта, идентифицированного либо из ProgID, либо CLSID. Ссылки `com::ptr` на вновь созданный объект и автоматически выпускают все принадлежащие ссылки после уничтожения.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Конструкторы класса используют две различные формы `CreateInstance` для создания объекта документа либо из ProgID, либо из CLSID плюс CLSCTX.

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

## <a name="ptrdetach"></a><a name="detach"></a>ptr::Detach

Отказывается от права собственности на объект COM, возвращая указатель на объект.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект COM.

Если объект не принадлежит, NULL возвращается.

### <a name="exceptions"></a>Исключения

Внутренне, `QueryInterface` вызывается на принадлежащий объект `HRESULT` COM и любая <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>ошибка преобразуется в исключение .

### <a name="remarks"></a>Remarks

`Detach`сначала добавляет ссылку на объект COM от имени вызываемого абонента, а затем выпускает все ссылки, принадлежащие `com::ptr`.  Звонящее должно в конечном счете освободить возвращенный объект, чтобы уничтожить его.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  Функция `DetachDocument` участника `Detach` требует отказаться от владения объектом COM и вернуть указатель вызывающему.

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

## <a name="ptrgetinterface"></a><a name="getInterface"></a>ptr::GetInterface

Возвращает указатель на принадлежащий объект COM.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на принадлежащий объект COM.

### <a name="exceptions"></a>Исключения

Внутренне, `QueryInterface` вызывается на принадлежащий объект `HRESULT` COM и любая <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>ошибка преобразуется в исключение .

### <a name="remarks"></a>Remarks

Добавлена `com::ptr` ссылка на объект COM от имени вызываемого абонента, а также сохраняет свою собственную ссылку на объект COM. Абонент должен в конечном счете освободить ссылку на возвращенный объект, иначе он никогда не будет уничтожен.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Функция `GetDocument` члена `GetInterface` использует для возврата указателя на объект COM.

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

## <a name="ptrqueryinterface"></a><a name="queryInterface"></a>ptr::Квиинтерфейс

Запрашивает принадлежащий объект COM для интерфейса и `com::ptr`прикрепляет результат к другому.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Параметры

*Других*<br/>
То, `com::ptr` что получит интерфейс.

### <a name="exceptions"></a>Исключения

Внутренне, `QueryInterface` вызывается на принадлежащий объект `HRESULT` COM и любая <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>ошибка преобразуется в исключение .

### <a name="remarks"></a>Remarks

Используйте этот метод для создания обертки COM для другого интерфейса объекта COM, принадлежащего текущей обертке. Этот метод `QueryInterface` вызывает через принадлежащий объект COM запросить указатель на определенный интерфейс объекта COM и `com::ptr`прикрепляет возвращенный указатель интерфейса к пройденному объекту.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Функция `WriteTopLevelNode` члена `QueryInterface` использует для `com::ptr` заполнения `IXMLDOMNode` локального с, а затем передает `com::ptr` (путем отслеживания ссылки) на функцию частного члена, который записывает имя узла и свойства текста на консоль.

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

## <a name="ptrrelease"></a><a name="release"></a>ptr::Release

Выпускает все принадлежащие ссылки на объект COM.

```cpp
void Release();
```

### <a name="remarks"></a>Remarks

Вызов этой функции высвобождает все принадлежащие ссылки `nullptr`на объект COM и устанавливает внутреннюю ручку к объекту COM.  Если никаких других ссылок на объект COM не существует, он будет уничтожен.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  Функция `ReplaceDocument` участника `Release` используется для выпуска любого предварительного объекта документа перед присоединением нового документа.

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

## <a name="ptroperator-gt"></a><a name="operator-arrow"></a>ptr:оператор-&gt;

Оператор доступа к членам, используемый для вызова методов на принадлежащем объекте COM.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Возвращаемое значение

A `smart_com_ptr` к объекту COM.

### <a name="exceptions"></a>Исключения

Внутренне, `QueryInterface` вызывается на принадлежащий объект `HRESULT` COM и любая <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>ошибка преобразуется в исключение .

### <a name="remarks"></a>Remarks

Этот оператор позволяет называть методы принадлежащего com объекта. Он возвращает `smart_com_ptr` временное, что `AddRef` автоматически `Release`обрабатывает свои собственные и .

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Функция `WriteDocument` используется `operator->` для `get_firstChild` вызова элемента объекта документа.

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

## <a name="ptroperator"></a><a name="operator-assign"></a>ptr::оператор

Прикрепляет объект COM `com::ptr`к .

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Параметры

*_right*<br/>
Указатель интерфейса COM для крепления.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на отслеживание `com::ptr`на .

### <a name="exceptions"></a>Исключения

Если `com::ptr` у уже есть ссылка `operator=` на <xref:System.InvalidOperationException>объект COM, бросает .

### <a name="remarks"></a>Remarks

Назначение объекта COM ссылкам `com::ptr` на объект COM, но не освобождает ссылку вызываемого на него.

Этот оператор имеет тот `Attach`же эффект, что и .

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  Функция `ReplaceDocument` элемента `Release` сначала вызывает любой ранее `operator=` принадлежащий объект, а затем использует для присоединения нового объекта документа.

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

## <a name="ptroperator-bool"></a><a name="operator-bool"></a>ptr::оператор бул

Оператор для `com::ptr` использования в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

`true`если принадлежащий com объект действителен; `false` в противном случае.

### <a name="remarks"></a>Remarks

Принадлежащий объект COM действителен, `nullptr`если он не является.

Этот оператор преобразует, к `_detail_class::_safe_bool` `bool` которому безопаснее, чем потому, что он не может быть преобразован в интегральный тип.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена. Функция `CreateInstance` элемента `operator bool` использует после создания нового объекта документа, чтобы определить, является ли он действительным, и записывает на консоль, если она есть.

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

## <a name="ptroperator"></a><a name="operator-logical-not"></a>ptr:Оператор!

Оператор, чтобы определить, является ли принадлежащий объект COM недействительным.

```cpp
bool operator!();
```

### <a name="return-value"></a>Возвращаемое значение

`true`если принадлежащий com объект является недействительным; `false` в противном случае.

### <a name="remarks"></a>Remarks

Принадлежащий объект COM действителен, `nullptr`если он не является.

### <a name="example"></a>Пример

Этот пример реализует класс CLR, `com::ptr` который использует `IXMLDOMDocument` для обертывания своего частного объекта-члена.  Функция `CreateInstance` элемента `operator!` использует для определения того, принадлежит ли объект документа уже, и создает новый экземпляр только в том случае, если объект недействителен.

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
