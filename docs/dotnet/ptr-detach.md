---
title: "PTR::Detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.Detach
- msclr.com.ptr.Detach
- ptr::Detach
- msclr::com::ptr::Detach
dev_langs:
- C++
helpviewer_keywords:
- ptr::Detach
ms.assetid: 23370c8a-8f79-4880-9fa1-46e110c1a92c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf50fa11677ea8d93ce557f94015030e8b16331e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ptrdetach"></a>ptr::Detach
Отдает владения объектом COM, возвращающая указатель на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_interface_type * Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на COM-объект.  
  
 Если объект не имеет владельца, возвращается значение NULL.  
  
## <a name="exceptions"></a>Исключения  
 На внутреннем уровне `QueryInterface` будет вызван на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение по <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.  
  
## <a name="remarks"></a>Примечания  
 `Detach`Сначала добавляется ссылка на COM-объект, от имени вызывающего объекта, а затем освобождает все ссылки, принадлежащих `com::ptr`.  В конечном счете, вызывающий объект должен освободить уничтожить его возвращаемый объект.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` программы-оболочки для своего закрытого члена `IXMLDOMDocument` объекта.  `DetachDocument` Функция-член вызывает `Detach` перестает быть владельцем COM-объекта и возвращает указатель в вызывающий объект.  
  
```  
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
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\com\ptr.h >  
  
 **Пространство имен** msclr::com  
  
## <a name="see-also"></a>См. также  
 [Члены PTR](../dotnet/ptr-members.md)   
 [PTR::Release](../dotnet/ptr-release.md)   
 [ptr::Attach](../dotnet/ptr-attach.md)