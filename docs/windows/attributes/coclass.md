---
title: coclass (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: 76540e90fef2e840b91bb07f570a7b8c0987eb10
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168335"
---
# <a name="coclass"></a>кокласс

Создает COM-объект, который может реализовать интерфейс COM.

## <a name="syntax"></a>Синтаксис

```cpp
[coclass]
```

## <a name="remarks"></a>Remarks

Атрибут **coclass** C++ помещает конструкцию coclass в созданный IDL-файл.

При определении компонентного класса можно также указать атрибуты [UUID](uuid-cpp-attributes.md), [версии](version-cpp.md), [потоков](threading-cpp.md), [vi_progid](vi-progid.md)и [ProgID](progid.md) . Если один из них не указан, он будет создан.

Если два файла заголовков содержат классы с атрибутом **coclass** и не указывают идентификатор GUID, компилятор будет использовать один и тот же идентификатор GUID для обоих классов, что приведет к ошибке MIDL.  Поэтому при использовании **компонентного класса**следует использовать атрибут `uuid`.

**Проекты ATL**

Когда этот атрибут предшествует определению класса или структуры в проекте ATL, он:

- Внедряет код или данные для поддержки автоматической регистрации объекта.

- Внедряет код или данные для поддержки фабрики классов COM для объекта.

- Внедряет код или данные для реализации `IUnknown` и сделать объект объектом, создаваемым моделью COM.

В частности, в целевой объект добавляются следующие базовые классы:

- [Класс CComCoClass](../../atl/reference/ccomcoclass-class.md) предоставляет фабрику класса по умолчанию и статистическую модель для объекта.

- [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) имеет шаблон, основанный на классе потоковой модели, заданном атрибутом [потоковой обработки](threading-cpp.md) . Если атрибут `threading` не указан, то потоковая модель по умолчанию — это апартамент.

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md) добавляется, если [несоздаваемый](noncreatable.md) атрибут не задан для целевого объекта.

Наконец, любой двойной интерфейс, не определенный с помощью встроенного IDL, заменяется соответствующим классом [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) . Если сдвоенный интерфейс определен во внедренном IDL, то конкретный интерфейс в базовом списке не изменяется.

Атрибут **coclass** также делает доступными следующие функции через внедренный код или в случае `GetObjectCLSID`, как статический метод в базовом классе `CComCoClass`:

- `UpdateRegistry` регистрирует фабрики класса целевого класса.

- `GetObjectCLSID`, который связан с регистрацией, может также использоваться для получения идентификатора CLSID целевого класса.

- `GetObjectFriendlyName` по умолчанию возвращает строку формата "\<*имя целевого класса*> `Object`". Если эта функция уже существует, она не добавляется. Добавьте эту функцию в целевой класс, чтобы вернуть более дружественное имя, отличное от автоматически создаваемого.

- `GetProgID`, который связан с регистрацией, возвращает строку, указанную с помощью атрибута [ProgID](progid.md) .

- `GetVersionIndependentProgID` имеет те же функциональные возможности, что и `GetProgID`, но она возвращает строку, указанную в [vi_progid](vi-progid.md).

Следующие изменения, связанные с картой COM, выполняются в целевом классе:

- Добавлена карта COM с записями для всех интерфейсов, от которых наследуется целевой класс, и всех записей, заданных атрибутом [точки входа com-интерфейса](../../mfc/com-interface-entry-points.md) , или теми, которые необходимы атрибуту [агрегатов](aggregates.md) .

- Макрос [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) вставляется в карту com.

Имя компонентного класса, созданного в IDL-файле для класса, будет иметь то же имя, что и класс.  Например, чтобы получить доступ к ИДЕНТИФИКАТОРу класса для компонентного класса `CMyClass`, в клиенте с помощью файла заголовка, созданного с помощью MIDL, используйте `CLSID_CMyClass`.

## <a name="example"></a>Пример

В следующем коде показано, как использовать атрибут **coclass** :

```cpp
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

В следующем примере показано, как переопределить реализацию по умолчанию функции, которая отображается в коде, вставленном атрибутом **coclass** . Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../../build/reference/fx-merge-injected-code.md) . Все базовые классы или интерфейсы, используемые для класса, будут отображаться во вставленном коде. Кроме того, если класс включен в внедренный код по умолчанию и вы явно указали этот класс как основу для компонентного класса, поставщик атрибутов будет использовать форму, указанную в коде.

```cpp
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
   // by adding the definition of UpdateRegistry to your code, // the function will not be included in the injected code
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {
      // you can add to the default implementation
      CRegistryVirtualMachine rvm;
      HRESULT hr;
      if (FAILED(hr = rvm.AddStandardReplacements()))
         return hr;
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),       GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);
   }
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)
