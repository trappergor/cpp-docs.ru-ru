---
title: 'PTR:: ~ ptr | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.com.ptr.~ptr
- ptr.~ptr
- msclr::com.ptr::~ptr
- ~ptr
- ptr::~ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr::~ptr
ms.assetid: 5f644aa5-fe66-4992-a5f8-13ec1292c949
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c3449adef6da61b7e671c8441ef4f1b51440fd96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ptrptr"></a>ptr::~ptr
Destructs `com::ptr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
~ptr();  
```  
  
## <a name="remarks"></a>Примечания  
 При уничтожении объекта `com::ptr` освобождает все ссылки, которыми владеет COM-объекта. При условии, что нет ссылок, хранимые на COM-объекта, COM-объект будет удален и освободить память.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` программы-оболочки для своего закрытого члена `IXMLDOMDocument` объекта.  В `main` функция, два `XmlDocument` деструкторы объектов будет вызываться, когда они выходят за пределы области `try` блока, возникающие в базовом `com::ptr` деструктор, сводятся освобождения все принадлежащие ссылок на COM объект.  
  
```  
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
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\com\ptr.h >  
  
 **Пространство имен** msclr::com  
  
## <a name="see-also"></a>См. также  
 [Члены PTR](../dotnet/ptr-members.md)   
 [PTR::PTR](../dotnet/ptr-ptr.md)   
 [ptr::CreateInstance](../dotnet/ptr-createinstance.md)