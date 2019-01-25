---
title: модуль (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: bafdb65f255ddf33964d22e5ea80a62446c2ad45
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893526"
---
# <a name="module-c"></a>module (C++)

Определяет блок библиотеки в IDL-файле.

## <a name="syntax"></a>Синтаксис

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Параметры

*type*<br/>
(Необязательно) Может принимать одно из следующих:

- `dll` Добавляет функции и классы, которые позволяют итоговому файлу DLL выступать в качестве внутрипроцессного COM-сервера. Это значение по умолчанию.

- `exe` Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве внешнепроцессного COM-сервера.

- `service` Добавляет функции и классы, которые позволяют итоговому исполняемому файлу выступать в качестве службы NT.

- `unspecified` Отключает внедрение кода ATL, связанного с атрибутом module: внедрение класса ATL Module, глобальный экземпляр _AtlModule и запись функции точек. Не отключает внедрение кода ATL из-за других атрибутов в проекте.

*name*<br/>
(Необязательно) Имя блока библиотеки.

*version*<br/>
(Необязательно) Номер версии, которую вы хотите назначить блоку библиотеки. Значение по умолчанию — 1,0.

*uuid*<br/>
Уникальный идентификатор для библиотеки. Если этот параметр опущен, идентификатор для библиотеки будет создан автоматически. Может потребоваться получить *uuid* для блока библиотеки, что можно сделать с помощью идентификатора **__uuidof (** *Имя_библиотеки* **)**.

*lcid*<br/>
Параметр локализации. Дополнительные сведения см. в описании [lcid](/windows/desktop/Midl/lcid) .

*control*<br/>
(Необязательно) Указывает, что все коклассы в библиотеке являются элементами управления.

*helpstring*<br/>
Указывает библиотеку типов.

*helpstringdll*<br/>
(Необязательно) Задает имя DLL-файла, в которых будет производиться уточняющего запроса строки документа. Дополнительные сведения см. в описании [helpstringdll](/windows/desktop/Midl/helpstringdll) .

*helpfile*<br/>
(Необязательно) Имя **помочь** файл для библиотеки типов.

*helpcontext*<br/>
(Необязательно) **Идентификатор справки** для этой библиотеки типов.

*helpstringcontext*<br/>
(Необязательно) См. в разделе [helpstringcontext](helpstringcontext.md) Дополнительные сведения.

*hidden*<br/>
(Необязательно) Запрещает отображение всей библиотеки. Этот режим предназначен для использования с элементами управления. Узлы должны создать новую библиотеку типов, инкапсулирующую элемент управления с расширенными свойствами. Дополнительные сведения см. в описании атрибута MIDL [hidden](/windows/desktop/Midl/hidden) .

*restricted*<br/>
(Необязательно) Элементы библиотеки нельзя вызывать произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](/windows/desktop/Midl/restricted) .

*custom*<br/>
(Необязательно) Один или несколько атрибутов; Это похоже на [пользовательских](custom-cpp.md) атрибута. Первый параметр для *пользовательских* является идентификатором GUID атрибута. Пример:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
Идентификатор строкового ресурса RGS-файла, используемый для регистрации идентификатора приложения для библиотеки DLL, исполняемого файла или службы. Если модуль имеет тип service, этот аргумент также используется для получения идентификатора строки, содержащей имя службы.

> [!NOTE]
> Как RGS-файл, так и строка с именем службы должны содержать одинаковое числовое значение.

## <a name="remarks"></a>Примечания

Если не указать параметр *restricted* для [emitidl](emitidl.md), **module** требуется в любой программе, использующей атрибуты C++.

Блок библиотеки создается, если в дополнение к атрибуту **module** исходный код также использует [dispinterface](dispinterface.md), [dual](dual.md), [object](object-cpp.md)либо атрибут, подразумевающий [coclass](coclass.md).

В IDL-файле разрешен один блок библиотеки. Несколько записей module в исходном коде будут объединены с применением самых последних значений параметров.

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанного выше поведения, атрибут также вставляет глобальный объект (вызывается `_AtlModule`) правильного типа и дополнительный код поддержки. Если атрибут является автономным, он вставляет класс, производный от правильного типа module. Если атрибут применяется к классу, он добавляет базовый класс правильного типа module. Правильный тип определяется по значению *тип* параметр:

- `type` = **dll**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) используется в качестве базового класса и стандартных точек входа библиотеки DLL, необходимых для COM-сервера. Это точки входа: [DllMain](/windows/desktop/Dlls/dllmain), [DllRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow)и [DllGetClassObject](https://msdn.microsoft.com/library/windows/desktop/dd797891).

- `type` = **exe**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **service**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) используется в качестве базового класса и стандартной точки входа исполняемого файла [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **unspecified**

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
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Библиотека](/windows/desktop/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[version](version-cpp.md)