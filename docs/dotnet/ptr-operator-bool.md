---
title: PTR::operator bool | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr::operator bool
- ptr.operator bool
- operator bool
- msclr::com::ptr::operator bool
- msclr.com.ptr.operator bool
dev_langs:
- C++
helpviewer_keywords:
- ptr::operator bool
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dcccfd23151d2e09f1fcafeb255dd7261ae2c12a
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163794"
---
# <a name="ptroperator-bool"></a>ptr::operator bool

Оператор для использования `com::ptr` в условном выражении.

## <a name="syntax"></a>Синтаксис

```
operator bool();
```

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если принадлежащий COM-объект является допустимым; **false** в противном случае.

## <a name="remarks"></a>Примечания

Собственный объект COM допустим, если это не `nullptr`.

Этот оператор фактически преобразует `_detail_class::_safe_bool` которого является более безопасным, чем `bool` , так как он не может быть преобразован в целочисленный тип.

## <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. `CreateInstance` Функция-член использует `operator bool` после создания нового объекта документа, чтобы определить, если он является допустимым и выводит на консоль в том случае, если это.

```
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

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\com\ptr.h >

**Пространство имен** msclr::com

## <a name="see-also"></a>См. также

[Члены ptr](../dotnet/ptr-members.md)<br/>
[ptr::operator!](../dotnet/ptr-operator-logical-not.md)