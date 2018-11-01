---
title: ptr::Attach
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::com::ptr::Attach
- ptr::Attach
- ptr.Attach
- msclr.com.ptr.Attach
helpviewer_keywords:
- Attach method
ms.assetid: 81d930de-cb2a-4c30-9bd6-94d65942c47a
ms.openlocfilehash: 194c5397c8598e839699f3d87df4c10de7a69d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466382"
---
# <a name="ptrattach"></a>ptr::Attach

Присоединяет COM-объекту `com::ptr`.

## <a name="syntax"></a>Синтаксис

```
void Attach(
   _interface_type * _right
);
```

#### <a name="parameters"></a>Параметры

*_справа*<br/>
Указатель на интерфейс COM для присоединения.

## <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылку на COM-объект `Attach` вызывает <xref:System.InvalidOperationException>.

## <a name="remarks"></a>Примечания

Вызов `Attach` ссылается на объект COM, но не освобождает вызывающего ссылку на него.

Передача `NULL` для `Attach` приводит не будет предпринято никаких действий.

## <a name="example"></a>Пример

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

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\\com\\ptr.h >

**Пространство имен** msclr::com

## <a name="see-also"></a>См. также

[Члены ptr](../dotnet/ptr-members.md)<br/>
[ptr::operator=](../dotnet/ptr-operator-assign.md)<br/>
[ptr::Release](../dotnet/ptr-release.md)