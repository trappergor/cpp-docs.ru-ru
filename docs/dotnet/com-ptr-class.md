---
title: Класс com::ptr
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
helpviewer_keywords:
- ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: c4d5818698f553fe1d003aab6ca3c7f31e85f843
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665374"
---
# <a name="comptr-class"></a>Класс com::ptr

Оболочка для COM-объекта, который может использоваться как член класса CLR.  Оболочки также позволяет автоматизировать управление жизненным циклом COM-объекта, освобождая все собственные ссылки объекта, когда его деструктора. Аналогично [класс CComPtr](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Синтаксис

```
template<class _interface_type>
ref class ptr;
```

#### <a name="parameters"></a>Параметры

*_interface_type*<br/>
COM-интерфейс.

## <a name="remarks"></a>Примечания

Объект `com::ptr` также может быть использована как переменная локальной функции для упрощения задач различных COM и автоматизировать управление жизненным циклом.

Объект `com::ptr` нельзя использовать непосредственно в качестве параметра функции, используйте [оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md) или [оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) вместо этого.

Объект `com::ptr` не возвращается из функции напрямую; вместо этого используйте дескриптор.

## <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта.  Вызывая открытые методы класса результатов в вызовах содержащегося `IXMLDOMDocument` объекта.  Образец создает экземпляр XML-документа, заполняет его простой XML-код и упрощенный обход узлов в дереве синтаксического анализа документа для печати XML на консоль.

```
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

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\com\ptr.h >

**Пространство имен** msclr::com

## <a name="see-also"></a>См. также

[Библиотека поддержки C++](../dotnet/cpp-support-library.md)<br/>
[Члены ptr](../dotnet/ptr-members.md)