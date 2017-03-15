---
title: "coclass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.coclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coclass attribute"
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# coclass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает COM\-объект, который может реализовать интерфейс модели COM.  
  
## Синтаксис  
  
```  
  
[coclass]  
  
```  
  
## Заметки  
 CoClass Атрибут C\+\+ задает конструкцию компонентного класса в сгенерированном файле idl.  
  
 При указании можно также определить компонентный класс [UUID](../windows/uuid-cpp-attributes.md)"  [версия](../windows/version-cpp.md)"  [Потоки](../windows/threading-cpp.md)"  [vi\_progid](../windows/vi-progid.md)и  [идентификатор progid](../Topic/progid.md) атрибуты.  Если любое из них не задан, то оно будет создано.  
  
 Если файл заголовка содержит классы с 2 CoClass атрибут, и не указывает идентификатор GUID, компилятор будет использовать один и тот же идентификатор GUID для обоих классов, и это приведет к ошибке MIDL.  Поэтому необходимо использовать `uuid` атрибут при использовании  **CoClass**.  
  
 **Проекты ATL**  
  
 Когда этот атрибут предшествует определение класса или структуры, в проекте библиотеки ATL:  
  
-   Вставляет код или данные для поддержки автоматической регистрации для объекта.  
  
-   Вставляет код или данные, чтобы поддерживать фабрика COM\-класс для объекта.  
  
-   Вставляет код или данные для реализации IUnknown объект COM\-creatable и сделайте объектом.  
  
 В частности, следующие базовые классы добавляются к целевому объекту.  
  
-   CComCoClass Class предоставляет модель по умолчанию фабрики классов и агрегата для объекта.  
  
-   [CComObjectRootEx Class](../atl/reference/ccomobjectrootex-class.md) есть шаблон, основанный на классе потоковой модели указанном  [Потоки](../windows/threading-cpp.md) атрибут.  Если **Потоки** атрибут не указан, по умолчанию используется потоковая модель подразделении.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) добавляет если  [noncreatable](../windows/noncreatable.md) атрибут не определен для целевого объекта.  
  
 Наконец, любой сдвоенный интерфейс, который не указан, используя внедренные IDL заменяется соответствовать IDispatchImpl класс.  Если сдвоенный интерфейс определен во внедренном IDL, не изменен заданный интерфейс в базовом списке.  
  
 **CoClass** атрибут также выполняет следующие функции, доступные через введенный код или, в случае  `GetObjectCLSID`, в качестве статического метода в базовом классе  `CComCoClass`.  
  
-   `UpdateRegistry` регистрирует фабрики класса целевого объекта.  
  
-   `GetObjectCLSID`, который относится к регистрации, может также использоваться для получения идентификатора CLSID класса целевого объекта.  
  
-   **GetObjectFriendlyName** по умолчанию возвращает строку формата "\<имя класса целевого объекта\>  `Object`".  Если эта функция уже существует, то она не добавляется.  Добавьте эту функцию к классу целевого объекта для возвращения более понятное имя, чем автоматически созданное веб\-приложение.  
  
-   **GetProgID**, который относится к регистрации возвращает строку, определенную с  [идентификатор progid](../Topic/progid.md) атрибут.  
  
-   **GetVersionIndependentProgID** имеет ту же функциональность, что и  **GetProgID**она возвращает только строку, определенную с  [vi\_progid](../windows/vi-progid.md).  
  
 Внесены следующие изменения, которые относятся к сопоставлению модели COM к классу целевого объекта:  
  
-   Сопоставление модели COM добавляется с записями для всех интерфейсов класс целевого объекта наследуется от и все записи указанных [Точки входа com\-интерфейса](../mfc/com-interface-entry-points.md) атрибут или эти необходимые  [агрегаты](../windows/aggregates.md) атрибут.  
  
-   OBJECT\_ENTRY\_AUTO макрос вставляется в сопоставление модели COM.  Этот макрос аналогичен OBJECT\_ENTRY с точки зрения функциональности, но не должен быть частью сопоставления модели COM класса целевого объекта.  
  
 Имя coclass, создаваемых в idl\-файле для класса будет иметь то же имя, что и класс.  Например, а ссылающся в следующем примере, чтобы получить доступ к идентификатор класса для компонентного класса CMyClass в клиенте через MIDL\-произведенный файл заголовка, используйте CLSID\_CMyClass.  
  
## Пример  
 В следующем примере кода демонстрируется применение CoClass атрибут:  
  
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
  
 В следующем образце показано, как переопределить реализацию по умолчанию функции, которая отображается в введенного кода CoClass атрибут.  См. \/Fx дополнительные сведения о коде впрыснутом просмотром.  Все базовые классы или интерфейсы, используемые для класса будут представлены в введенный код.   Более того, если класс включено по умолчанию в впрыснутом коде и явно указать этот класс в качестве базового для совместного класса, то поставщик атрибута будет использовать форму, определенную в коде.  
  
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
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../Topic/appobject.md)