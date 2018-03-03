---
title: "ptr::operator! | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr::operator!
- msclr::com::ptr::operator!
- ptr.operator!
- msclr.com.ptr.operator!
dev_langs:
- C++
helpviewer_keywords:
- ptr::operator!
ms.assetid: 7f4101dc-2045-42e7-abb1-6a30e17147f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d3ef67f9ef6128560d8bb6fef9d0d6fd75d08aca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ptroperator"></a>ptr::operator!
Оператор, чтобы определить, если собственный объект COM является недопустимым.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool operator!();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если COM-объекта, принадлежащего недопустим. `false` в противном случае.  
  
## <a name="remarks"></a>Примечания  
 Собственный объект COM является действительным, если он не `nullptr`.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` программы-оболочки для своего закрытого члена `IXMLDOMDocument` объекта.  `CreateInstance` Функция-член использует `operator!` для определения, если уже есть владелец объекта документа и создает новый экземпляр, только если объект является недопустимым.  
  
```  
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
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\com\ptr.h >  
  
 **Пространство имен** msclr::com  
  
## <a name="see-also"></a>См. также  
 [Члены PTR](../dotnet/ptr-members.md)   
 [ptr::operator bool](../dotnet/ptr-operator-bool.md)