---
title: "Компонентный класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.coclass
dev_langs: C++
helpviewer_keywords: coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bcae762c603f05ce11eae5d14eb2e182c666797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coclass"></a>кокласс
Создает объект COM, который можно реализовать COM-интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[coclass]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Coclass** атрибута C++ помещает конструкцию компонентного класса в сгенерированный IDL-файл.  
  
 При определении компонентного класса, можно также указать [uuid](../windows/uuid-cpp-attributes.md), [версии](../windows/version-cpp.md), [работа с потоками](../windows/threading-cpp.md), [vi_progid](../windows/vi-progid.md), и [progid ](../windows/progid.md) атрибуты. Если один из них не указан, он будет создан.  
  
 Если два файла заголовков содержат классы с **coclass** атрибута и не указан идентификатор GUID, компилятор будет использовать идентификатор GUID для обоих классов, и что приведет к ошибке MIDL.  Таким образом, следует использовать `uuid` атрибут при использовании **компонентного класса**.  
  
 **Проекты ATL**  
  
 Если этот атрибут предшествует определения класса или структуры в проект ATL его:  
  
-   Внедряет кода или данных для поддержки автоматическую регистрацию для объекта.  
  
-   Внедряет кода или данных для поддержки фабрики класса COM для объекта.  
  
-   Внедряет кода или данных для реализации **IUnknown** и сделать объект создаваемыми COM объекта.  
  
 В частности следующих базовых классов добавляются на целевой объект:  
  
-   [Класс CComCoClass](../atl/reference/ccomcoclass-class.md) предоставляет модель фабрики и статистической обработки по умолчанию класса для объекта.  
  
-   [Класс CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) имеет шаблона, основанного на потоковой модели класса, указанного параметром [работа с потоками](../windows/threading-cpp.md) атрибута. Если **работа с потоками** атрибут не указан, значение по умолчанию потоковая модель является подразделением.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) добавляется, если [noncreatable](../windows/noncreatable.md) атрибут не указан для целевого объекта.  
  
 Наконец, любые сдвоенный интерфейс, который не определен с помощью внедренный IDL заменяется соответствующего [IDispatchImpl](../atl/reference/idispatchimpl-class.md) класса. Если сдвоенный интерфейс определен во внедренный IDL, определенный интерфейс в базовый список не изменяется.  
  
 **Coclass** атрибута также доступны следующие функции через введенного кода или в случае, когда `GetObjectCLSID`, как статический метод в базовом классе `CComCoClass`:  
  
-   `UpdateRegistry`Регистрация фабрик классов целевого класса.  
  
-   `GetObjectCLSID`, которое связано с регистрацией, также можно получить CLSID целевого класса.  
  
-   **GetObjectFriendlyName** по умолчанию возвращает строку в формате «\<*имя класса*> `Object`». Если эта функция уже существует, она не добавляется. Добавьте эту функцию для целевого класса для возврата более понятные имена, от того, создается автоматически.  
  
-   **GetProgID**, которое связано с регистрацией, возвращает строки, указанные с [progid](../windows/progid.md) атрибута.  
  
-   **GetVersionIndependentProgID** имеет ту же функциональность, что **GetProgID**, но оно возвращает строки, указанной [vi_progid](../windows/vi-progid.md).  
  
 Следующие изменения, которые связаны с картой COM, выполняются для целевого класса:  
  
-   Операции для всех интерфейсов, целевой класс является производным от и все операции, заданные добавляется сопоставление COM [точки входа интерфейса COM](../mfc/com-interface-entry-points.md) атрибута или требованиям [статистические выражения](../windows/aggregates.md) атрибута.  
  
-   [OBJECT_ENTRY_AUTO](../atl/reference/object-map-macros.md#object_entry_auto) макрос вставляется в сопоставление COM.
  
 Имя компонентного класса, создаваемого в IDL-файл для класса будет иметь имя, совпадающее с именем класса.  Например, а также ссылки на следующий пример для доступа к идентификатор класса для компонентного класса CMyClass, в клиенте с помощью файла заголовка, созданные MIDL, используйте CLSID_CMyClass.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать **coclass** атрибута:  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 Следующий пример показано, как переопределить реализацию по умолчанию функции, которая отображается в коду, введенному **coclass** атрибута. Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../build/reference/fx-merge-injected-code.md) . В этот код будет отображаться все базовые классы и интерфейсы, которые можно использовать для класса.   Кроме того Если класс включается по умолчанию в этот код, можно явно указать этого класса в качестве базы для вашего компонентного класса атрибута поставщик будет использовать форма, указанная в коде.  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты COM](../windows/com-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)