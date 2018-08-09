---
title: модуль (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.module
dev_langs:
- C++
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e7354dc422027207bc1dab357487ffcce48a4ca
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018598"
---
# <a name="module-c"></a>module (C++)
Определяет блок библиотеки в IDL-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ module (  
   type=dll,  
   name=string,  
   version=1.0,  
   uuid=uuid,  
   lcid=integer,  
   control=boolean,  
   helpstring=string,  
   helpstringdll=string,  
   helpfile=string,  
   helpcontext=integer,  
   helpstringcontext=integer,  
   hidden=boolean,  
   restricted=boolean,  
   custom=string,  
   resource_name=string,  
) ];  
```  
  
### <a name="parameters"></a>Параметры  
*Тип* (необязательно)  
Ниже указаны доступные значения.  
  
-   `dll` Добавляет функции и классы, которые позволяют итоговому файлу DLL выступать в качестве внутрипроцессного COM-сервера. Это значение по умолчанию.  
  
-   `exe` Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве внешнепроцессного COM-сервера.  
  
-   `service` Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве службы NT.  
  
-   `unspecified` Отключает внедрение кода ATL, связанного с атрибутом module: внедрение класса ATL Module, глобальный экземпляр _AtlModule и запись функции точек. Не отключает внедрение кода ATL из-за других атрибутов в проекте.  
  
*name* (необязательно)  
Имя блока библиотеки.  
  
*версия* (необязательно)  
Номер версии, который вы хотите назначить блоку библиотеки. Значение по умолчанию — 1,0.  
  
*uuid*  
Уникальный идентификатор для библиотеки. Если этот параметр опущен, идентификатор для библиотеки будет создан автоматически. Может потребоваться получить *uuid* для блока библиотеки, что можно сделать с помощью идентификатора **__uuidof (***Имя_библиотеки***)**.  
  
*lcid*  
Параметр локализации. Дополнительные сведения см. в описании [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) .  
  
*элемент управления* (необязательно)  
Указывает, что все коклассы в библиотеке являются элементами управления.  
  
*helpstring*  
Указывает библиотеку типов.  
  
*helpstringdll* (необязательно)  
Задает имя DLL-файла, используемого для выполнения уточняющего запроса строки документа. Дополнительные сведения см. в описании [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) .  
  
*HelpFile* (необязательно)  
Имя **помочь** файл для библиотеки типов.  
  
*HelpContext* (необязательно)  
**Идентификатор справки** для этой библиотеки типов.  
  
*helpstringcontext* (необязательно)  
Дополнительные сведения см. в описании [helpstringcontext](../windows/helpstringcontext.md) .  
  
*скрытые* (необязательно)  
Запрещает отображение всей библиотеки. Этот режим предназначен для использования с элементами управления. Узлы должны создать новую библиотеку типов, инкапсулирующую элемент управления с расширенными свойствами. Дополнительные сведения см. в описании атрибута MIDL [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) .  
  
*ограниченные* (необязательно)  
Элементы библиотеки нельзя вызывать произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) .  
  
*пользовательские* (необязательно)  
Один или несколько атрибутов; аналогично атрибуту [custom](../windows/custom-cpp.md) . Первый параметр для *пользовательских* является идентификатором GUID атрибута. Пример:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
*имя_ресурса*  
Идентификатор строкового ресурса RGS-файла, используемый для регистрации идентификатора приложения для библиотеки DLL, исполняемого файла или службы. Если модуль имеет тип service, этот аргумент также используется для получения идентификатора строки, содержащей имя службы.  
  
> [!NOTE]
>  Как RGS-файл, так и строка с именем службы должны содержать одинаковое числовое значение.  
  
## <a name="remarks"></a>Примечания  
 Если не указать *ограниченных* параметр [emitidl](../windows/emitidl.md), **модуль** требуется в любой программе, использующей атрибуты C++.  
  
 Блок библиотеки создается, если в дополнение к атрибуту **module** исходный код также использует [dispinterface](../windows/dispinterface.md), [dual](../windows/dual.md), [object](../windows/object-cpp.md)либо атрибут, подразумевающий [coclass](../windows/coclass.md).  
  
 В IDL-файле разрешен один блок библиотеки. Несколько записей module в исходном коде будут объединены с применением самых последних значений параметров.  
  
 Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанного выше поведения, атрибут также вставляет глобальный объект (вызывается `_AtlModule`) правильного типа и дополнительный код поддержки. Если атрибут является автономным, он вставляет класс, производный от правильного типа module. Если атрибут применяется к классу, он добавляет базовый класс правильного типа module. Правильный тип определяется по значению *тип* параметр:  
  
-   `type` = **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) используется в качестве базового класса и стандартных точек входа библиотеки DLL, необходимых для COM-сервера. Это точки входа: [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368)и [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891).  
  
-   `type` = **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **service**  
  
     [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **unspecified**  
  
     Отключает внедрение кода ATL, связанного с атрибутом module.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как создать блок библиотеки в сформированном IDL-файле.  
  
```cpp  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 В следующем коде показано, что можно предоставить собственную реализацию функции, которая будет отображаться в коде, внедренном в результате применения **module**. Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../build/reference/fx-merge-injected-code.md) . Чтобы переопределить одну из функций, вставленных атрибутом **module** , создайте класс, который будет содержать реализацию функции, и примените к этому классу атрибут **module** .  
  
```cpp  
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
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [Библиотека](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [HelpContext](../windows/helpcontext.md)   
 [HelpString](../windows/helpstring.md)   
 [HelpFile](../windows/helpfile.md)   
 [version](../windows/version-cpp.md)   