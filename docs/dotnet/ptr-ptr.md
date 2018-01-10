---
title: "PTR::PTR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr::ptr
- ptr.ptr
- msclr.com.ptr.ptr
- msclr::com::ptr::ptr
dev_langs: C++
helpviewer_keywords: ptr::ptr
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49013e718ad540e88a1cbd00eceb6bb3dc0071b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ptrptr"></a>ptr::ptr
Создает `com::ptr` программы-оболочки COM-объектом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ptr();  
ptr(  
   _interface_type * p  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `P`  
 Указатель интерфейса COM.  
  
## <a name="remarks"></a>Примечания  
 Конструктор без аргументов присваивает `nullptr` для базового объекта дескриптора. Последующие вызовы `com::ptr` будет проверить внутренний объект и автоматически ошибкой, пока объект имеет фактически или присоединенного.  
  
 Один аргумент конструктора добавляет ссылку на COM-объекта, но не освобождает ссылку вызывающего, вызывающий объект должен вызвать `Release` действительно освобождать управления COM-объекта. При `com::ptr`его деструктор вызывается автоматически освобождает ссылки COM-объекта.  
  
 Передача `NULL` для этого конструктора является таким же, как вызывать версию без аргументов.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` программы-оболочки для своего закрытого члена `IXMLDOMDocument` объекта. Он демонстрирует использование обеих версий конструктора.  
  
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
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\com\ptr.h >  
  
 **Пространство имен** msclr::com  
  
## <a name="see-also"></a>См. также  
 [Члены PTR](../dotnet/ptr-members.md)   
 [PTR::CreateInstance](../dotnet/ptr-createinstance.md)   
 [ptr::~ptr](../dotnet/ptr-tilde-ptr.md)