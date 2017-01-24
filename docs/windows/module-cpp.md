---
title: "module (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "атрибуты модуля"
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# module (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет блок библиотеки в IDL\-файле.  
  
## Синтаксис  
  
```  
  
[ module (  
type  
=dll,  
name  
=  
string  
,  
version  
=1.0,  
   uuid=  
uuid  
,  
   lcid=  
integer  
,  
   control=  
boolean  
,  
   helpstring=  
string  
,  
helpstringdll  
=  
string  
,  
helpfile  
=  
string  
,  
helpcontext  
=  
integer  
,  
helpstringcontext  
=  
integer  
,  
hidden  
=  
boolean  
,  
restricted  
=  
boolean  
,  
custom  
=  
string  
,  
   resource_name=  
string  
,  
) ];  
  
```  
  
#### Параметры  
 ***type***  \(необязательно\)  
 Ниже указаны доступные значения.  
  
-   **dll** Добавляет функции и классы, которые позволяют итоговому файлу DLL выступать в качестве внутрипроцессного COM\-сервера. Это значение по умолчанию.  
  
-   **exe** Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве внешнепроцессного COM\-сервера.  
  
-   **service** Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве службы NT.  
  
-   **unspecified** Отключает внедрение кода ATL, связанного с атрибутом module: внедрение класса Module ATL, глобальный экземпляр \_AtlModule и функции точек входа.  Не отключает внедрение кода ATL из\-за других атрибутов в проекте.  
  
 ***name***  \(необязательно\)  
 Имя блока библиотеки.  
  
 ***version***  \(необязательно\)  
 Номер версии, который вы хотите назначить блоку библиотеки. Значение по умолчанию — 1,0.  
  
 `uuid`  
 Уникальный идентификатор для библиотеки. Если этот параметр опущен, идентификатор для библиотеки будет создан автоматически. Может потребоваться получить значение *uuid* для блока библиотеки, что можно сделать с помощью идентификатора **\_\_uuidof\(***имя\_библиотеки***\)**.  
  
 **lcid**  
 Параметр локализации. Дополнительные сведения см. в описании [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067).  
  
 **control** \(необязательно\)  
 Указывает, что все коклассы в библиотеке являются элементами управления.  
  
 **helpstring**  
 Указывает библиотеку типов.  
  
 ***helpstringdll***  \(необязательно\)  
 Задает имя DLL\-файла, используемого для выполнения уточняющего запроса строки документа. Дополнительные сведения см. в описании [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860).  
  
 **helpfile** \(необязательно\)  
 Имя файла справки для библиотеки типов.  
  
 **helpcontext** \(необязательно\)  
 Идентификатор справки для этой библиотеки типов.  
  
 **helpstringcontext** \(необязательно\)  
 Дополнительные сведения см. в описании [helpstringcontext](../windows/helpstringcontext.md).  
  
 **hidden** \(необязательно\)  
 Запрещает отображение всей библиотеки. Этот режим предназначен для использования с элементами управления. Узлы должны создать новую библиотеку типов, инкапсулирующую элемент управления с расширенными свойствами. Дополнительные сведения см. в описании атрибута MIDL [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861).  
  
 **restricted** \(необязательно\)  
 Элементы библиотеки нельзя вызывать произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157).  
  
 ***custom***  \(необязательно\)  
 Один или несколько атрибутов; аналогично атрибуту [custom](../windows/custom-cpp.md). Первый параметр для `custom` является идентификатором GUID атрибута. Пример:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
 **resource\_name**  
 Идентификатор строкового ресурса RGS\-файла, используемый для регистрации идентификатора приложения для библиотеки DLL, исполняемого файла или службы. Если модуль имеет тип service, этот аргумент также используется для получения идентификатора строки, содержащей имя службы.  
  
> [!NOTE]
>  Как RGS\-файл, так и строка с именем службы должны содержать одинаковое числовое значение.  
  
## Заметки  
 Если не указать параметр **restricted** для [emitidl](../windows/emitidl.md), **module** требуется в любой программе, использующей атрибуты C\+\+.  
  
 Блок библиотеки создается, если в дополнение к атрибуту **module** исходный код также использует [dispinterface](../windows/dispinterface.md), [dual](../Topic/dual.md), [object](../Topic/object%20\(C++\).md) либо атрибут, подразумевающий [coclass](../windows/coclass.md).  
  
 В IDL\-файле разрешен один блок библиотеки. Несколько записей module в исходном коде будут объединены с применением самых последних значений параметров.  
  
 Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанного выше поведения, атрибут также вставляет глобальный объект \(называемый **\_AtlModule**\) правильного типа и дополнительный код поддержки. Если атрибут является автономным, он вставляет класс, производный от правильного типа module. Если атрибут применяется к классу, он добавляет базовый класс правильного типа module. Правильный тип определяется по значению параметра `type`:  
  
-   `type` \= **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) используется в качестве базового класса и стандартных точек входа библиотеки DLL, необходимых для COM\-сервера. Это точки входа: [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368) и [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891).  
  
-   `type` \= **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` \= **service**  
  
     [CAtlServiceModuleT](../Topic/CAtlServiceModuleT%20Class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` \= **unspecified**  
  
     Отключает внедрение кода ATL, связанного с атрибутом module.  
  
## Пример  
 В следующем коде показано, как создать блок библиотеки в сформированном IDL\-файле.  
  
```  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 В следующем коде показано, что можно предоставить собственную реализацию функции, которая будет отображаться в коде, внедренном в результате применения **module**. Дополнительные сведения о просмотре внедренного кода см. в разделе [\/Fx](../build/reference/fx-merge-injected-code.md). Чтобы переопределить одну из функций, вставленных атрибутом **module**, создайте класс, который будет содержать реализацию функции, и примените к этому классу атрибут **module**.  
  
```  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [библиотека](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [helpfile](../Topic/helpfile.md)   
 [version](../windows/version-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)