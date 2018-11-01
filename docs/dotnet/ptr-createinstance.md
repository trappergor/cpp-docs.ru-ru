---
title: ptr::CreateInstance
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
helpviewer_keywords:
- ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
ms.openlocfilehash: 5b1a59eef44c7ad1c1903cb2cb1b75a4cbd8fabb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536179"
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance

Создает экземпляр COM-объекта в `com::ptr`.

## <a name="syntax"></a>Синтаксис

```
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

#### <a name="parameters"></a>Параметры

*progid*<br/>
Строка `ProgID`.

*pouter*<br/>
Указатель на интерфейс IUnknown агрегатного объекта (управляющий IUnknown). Если `pouter` не указан, `NULL` используется.

*cls_context*<br/>
Контекст, в котором будет выполняться код, который управляет вновь созданный объект. Значения берутся из `CLSCTX` перечисления. Если `cls_context` не указан, значение, используемое CLSCTX_ALL.

*rclsid*<br/>
`CLSID` связанный с данными и кодом, который будет использоваться для создания объекта.

## <a name="exceptions"></a>Исключения

Если `com::ptr` уже владеет ссылку на COM-объект `CreateInstance` вызывает <xref:System.InvalidOperationException>.

Эта функция вызывает `CoCreateInstance` и использует <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> преобразовать любой ошибки `HRESULT` в соответствующее исключение.

## <a name="remarks"></a>Примечания

`CreateInstance` использует `CoCreateInstance` для создания нового экземпляра заданного объекта, определяемого с ProgID или CLSID. `com::ptr` Ссылается на вновь созданный объект и автоматически освобождает все собственные ссылки после уничтожения.

## <a name="example"></a>Пример

Этот пример реализует класс CLR, который использует `com::ptr` программы-оболочки для его закрытого члена `IXMLDOMDocument` объекта. Конструкторы класса использовать два различных вида `CreateInstance` для создания объекта документа, ProgID или CLSID, а также CLSCTX.

```
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

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\com\ptr.h >

**Пространство имен** msclr::com

## <a name="see-also"></a>См. также

[Члены ptr](../dotnet/ptr-members.md)