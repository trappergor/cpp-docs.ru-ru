---
title: "ptr::ptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr::ptr"
  - "ptr.ptr"
  - "msclr.com.ptr.ptr"
  - "msclr::com::ptr::ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::ptr"
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ptr::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает `com::ptr` для создания com\-объекта.  
  
## Синтаксис  
  
```  
ptr();  
ptr(  
   _interface_type * p  
);  
```  
  
#### Параметры  
 `P`  
 Указатель интерфейса COM.  
  
## Заметки  
 Конструктор без аргументов присвоить `nullptr` к базовому дескриптор объекта.  Последующие вызовы `com::ptr` проверяют внутренний объект и автоматически завершится ошибкой до тех пор, пока объект фактически не создается или будет вложен.  
  
 Конструктор от аргумента добавляет ссылки на COM\-объект, но не освобождает ссылку вызывающего объекта, поэтому вызывающий объект должен вызвать `Release` com\-объекта действительно для освобождения элемента управления.  Если деструктор `com::ptr` вызывается автоматически освобождает его ссылки на COM\-объект.  
  
 Передача `NULL` к этому конструктору аналогичен вызову версия без аргумента.  
  
## Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` для создания его объект `IXMLDOMDocument` закрытого члена.  Демонстрируется потребление обеих версий конструктора.  
  
```  
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
  
## Требования  
 **Файл заголовка**\<msclr\\com\\ptr.h\>  
  
 **Пространство имен** msclr::com  
  
## См. также  
 [Члены ptr](../dotnet/ptr-members.md)   
 [ptr::CreateInstance](../dotnet/ptr-createinstance.md)   
 [ptr::~ptr](../dotnet/ptr-tilde-ptr.md)