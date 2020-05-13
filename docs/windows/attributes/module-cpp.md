---
title: модуль (атрибут C ' COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: 9d4f9e23aaf182e28930ba3a4462b07533ba9015
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754381"
---
# <a name="module-c"></a>module (C++)

Определяет блок библиотеки в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Параметры

*type*<br/>
(Необязательно) Может быть одним из следующих:

- `dll`Добавляет функции и классы, которые позволяют полученному DLL функционировать в качестве в процессе COM сервера. Это значение по умолчанию.

- `exe`Добавляет функции и классы, которые позволяют в результате исполняемой функции функционировать в качестве неизлечимых COM сервера.

- `service`Добавляет функции и классы, которые позволяют в результате исполняемой функции в качестве службы NT.

- `unspecified`Отстраняет впрыски кода ATL, связанные с атрибутом модуля: инъекция класса ATL Module, глобальный экземпляр _AtlModule и функции точки входа. Не отключает внедрение кода ATL из-за других атрибутов в проекте.

*name*<br/>
(Необязательно) Название библиотечного блока.

*version*<br/>
(Необязательно) Номер версии, который вы хотите присвоить блоку библиотеки. Значение по умолчанию — 1,0.

*uuid*<br/>
Уникальный идентификатор для библиотеки. Если этот параметр опущен, идентификатор для библиотеки будет создан автоматически. Может потребоваться получить значение *uuid* для блока библиотеки, что можно сделать с помощью идентификатора **__uuidof(** *имя_библиотеки* **)**.

*lcid*<br/>
Параметр локализации. Дополнительные сведения см. в описании [lcid](/windows/win32/Midl/lcid) .

*Управления*<br/>
(Необязательно) Уточняется, что все коклассы в библиотеке являются элементами управления.

*helpstring*<br/>
Указывает библиотеку типов.

*helpstringdll*<br/>
(Необязательно) Устанавливает имя файла .dll для выполнения поиска строки документа. Дополнительные сведения см. в описании [helpstringdll](/windows/win32/Midl/helpstringdll) .

*справочный файл*<br/>
(Необязательно) Имя файла **справки** для библиотеки типов.

*helpcontext*<br/>
(Необязательно) **Идентификатор справки** для этой библиотеки типов.

*helpstringcontext*<br/>
(Необязательно) Для получения дополнительной информации можно ознакомиться с [помощью helpstringcontext.](helpstringcontext.md)

*Скрытые*<br/>
(Необязательно) Предотвращает отображение всей библиотеки. Этот режим предназначен для использования с элементами управления. Узлы должны создать новую библиотеку типов, инкапсулирующую элемент управления с расширенными свойствами. Дополнительные сведения см. в описании атрибута MIDL [hidden](/windows/win32/Midl/hidden) .

*Ограничен*<br/>
(Необязательно) Члены библиотеки нельзя назвать произвольно. Дополнительные сведения см. в описании атрибута MIDL [restricted](/windows/win32/Midl/restricted) .

*Пользовательские*<br/>
(Необязательно) Один или несколько атрибутов; это похоже на [пользовательский](custom-cpp.md) атрибут. Первым *параметром, пользовательским* является GUID атрибута. Пример:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
Идентификатор строкового ресурса RGS-файла, используемый для регистрации идентификатора приложения для библиотеки DLL, исполняемого файла или службы. Если модуль имеет тип service, этот аргумент также используется для получения идентификатора строки, содержащей имя службы.

> [!NOTE]
> Как RGS-файл, так и строка с именем службы должны содержать одинаковое числовое значение.

## <a name="remarks"></a>Remarks

Если не указать параметр *restricted* для [emitidl](emitidl.md), **module** требуется в любой программе, использующей атрибуты C++.

Блок библиотеки создается, если в дополнение к атрибуту **module** исходный код также использует [dispinterface](dispinterface.md), [dual](dual.md), [object](object-cpp.md)либо атрибут, подразумевающий [coclass](coclass.md).

В IDL-файле разрешен один блок библиотеки. Несколько записей module в исходном коде будут объединены с применением самых последних значений параметров.

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. В дополнение к вышеупомянутому поведению, атрибут `_AtlModule`также вставляет глобальный объект (называемый ) правильного типа и дополнительный код поддержки. Если атрибут является автономным, он вставляет класс, производный от правильного типа module. Если атрибут применяется к классу, он добавляет базовый класс правильного типа module. Правильный тип определяется значением параметра *типа:*

- `type` = **Dll**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) используется в качестве базового класса и стандартных точек входа библиотеки DLL, необходимых для COM-сервера. Это точки входа: [DllMain](/windows/win32/Dlls/dllmain), [DllRegisterServer](/windows/win32/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/win32/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)и [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- `type` = **exe**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/win32/api/winbase/nf-winbase-winmain).

- `type` = **Службы**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/win32/api/winbase/nf-winbase-winmain).

- `type` = **Неопределенное**

   Отключает внедрение кода ATL, связанного с атрибутом module.

## <a name="example"></a>Пример

В следующем коде показано, как создать блок библиотеки в сформированном IDL-файле.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

В следующем коде показано, что можно предоставить собственную реализацию функции, которая будет отображаться в коде, внедренном в результате применения **module**. Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../../build/reference/fx-merge-injected-code.md) . Чтобы переопределить одну из функций, вставленных атрибутом **module** , создайте класс, который будет содержать реализацию функции, и примените к этому классу атрибут **module** .

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
|**Повторяемые**|нет|
|**Требуемые атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Самостоятельные атрибуты](stand-alone-attributes.md)<br/>
[Типдеф, Enum, Союз и Struct атрибуты](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Библиотека](/windows/win32/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[справочный файл](helpfile.md)<br/>
[version](version-cpp.md)
