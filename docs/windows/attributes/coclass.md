---
title: coclass (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: 69f749dd6f8b2a8c42b4c75dd3790b9f7fbcf291
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603090"
---
# <a name="coclass"></a>кокласс

Создает объект COM, который можно реализовать COM-интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[coclass]
```

## <a name="remarks"></a>Примечания

**Coclass** атрибут C++ помещает конструкцию компонентного класса в созданного IDL-файла.

При определении кокласса, можно также указать [uuid](uuid-cpp-attributes.md), [версии](version-cpp.md), [threading](threading-cpp.md), [vi_progid](vi-progid.md), и [progid ](progid.md) атрибуты. Если один из них не указан, он создается.

Если два файла заголовков содержат классы с **coclass** атрибут и не указать идентификатор GUID, компилятор будет использовать тот же идентификатор GUID для обоих классов, и это приведет к ошибке MIDL.  Таким образом, следует использовать `uuid` атрибут при использовании **coclass**.

**Проекты ATL**

Если этот атрибут стоит перед определением класса или структуры в проект ATL, он:

- Внедряет код или данные для поддержки автоматической регистрацией для объекта.

- Внедряет код или данные для поддержки фабрики класса COM для объекта.

- Внедряет код или данные для реализации `IUnknown` и сделать объект COM-создаваемый объект.

В частности следующих базовых классов добавляются к целевому объекту:

- [Класс CComCoClass](../../atl/reference/ccomcoclass-class.md) предоставляет модель фабрики и статистической обработки по умолчанию класса для объекта.

- [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) имеет шаблона, основанного на потоковой модели класса, указанного параметром [threading](threading-cpp.md) атрибута. Если `threading` атрибут не указан, по умолчанию потоковая модель является подразделением.

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md) добавляется, если [noncreatable](noncreatable.md) атрибут не указан для целевого объекта.

Наконец, любой сдвоенный интерфейс, который не определен с помощью внедренные IDL заменяется соответствующего [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) класса. Если сдвоенный интерфейс определен во внедренный IDL, определенный интерфейс в базовый список не изменяется.

**Coclass** атрибут также доступны следующие функции с помощью введенного кода или в случае `GetObjectCLSID`, как статический метод в базовом классе `CComCoClass`:

- `UpdateRegistry` регистрирует фабрики классов целевого класса.

- `GetObjectCLSID`, который относится к регистрации, также может использоваться для получения CLSID целевого класса.

- `GetObjectFriendlyName` по умолчанию возвращает строку в формате "\<*имя класса*> `Object`«. Если эта функция уже существует, он не добавляется. Добавьте эту функцию для целевого класса для возвращения более понятные имена, отличного от того, который создается автоматически.

- `GetProgID`, которому относится к регистрации, возвращает строку, указанную с помощью [progid](progid.md) атрибута.

- `GetVersionIndependentProgID` имеет ту же функциональность, что `GetProgID`, но возвращает строки, указанной [vi_progid](vi-progid.md).

Следующие изменения, которые связаны с COM карты, выполняются в целевой класс:

- Операции для всех интерфейсов, целевой класс является производным от и все операции, заданные добавляется COM карты [точки входа интерфейса COM](../../mfc/com-interface-entry-points.md) атрибута или предусмотренные [статистические выражения](aggregates.md) атрибута.

- [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) макрос вставляется в сопоставление COM.

Имя компонентного класса, созданный в IDL-файл для класса будет иметь имя, совпадающее с именем класса.  Например, а также ссылки на следующий пример, чтобы получить доступ к идентификатор класса для компонентного класса `CMyClass`, в клиенте с помощью файла заголовка, созданные MIDL, использовать `CLSID_CMyClass`.

## <a name="example"></a>Пример

Ниже показано, как использовать **coclass** атрибут:

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

Следующий пример показано, как переопределить реализацию по умолчанию функции, которая отображается в коде, введенному **coclass** атрибута. Дополнительные сведения о просмотре внедренного кода см. в разделе [/Fx](../../build/reference/fx-merge-injected-code.md) . В этот код будет отображаться все базовые классы или интерфейсы, которые можно использовать для класса. Кроме того Если класс включен по умолчанию в этот код и явно указать этот класс базовым о вашей компонентного класса, поставщик атрибутов будет использовать формат, определенный в коде.

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
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)