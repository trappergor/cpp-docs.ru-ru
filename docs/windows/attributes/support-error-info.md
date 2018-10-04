---
title: support_error_info (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c6bb07071efa162b5b33ae5f1dfe72ac7ea02e8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791268"
---
# <a name="supporterrorinfo"></a>support_error_info

Реализует поддержку для возвращения подробных сведений об ошибках.

## <a name="syntax"></a>Синтаксис

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Параметры

*error_interface*<br/>
Идентификатор для реализации интерфейса `IErrorInfo`.

## <a name="remarks"></a>Примечания

Атрибут **support_error_info** языка C++ реализует поддержку для возвращения на клиент подробных контекстных ошибок, обнаруженных для целевого объекта. Чтобы объект поддерживал ошибки, методы класса `IErrorInfo` интерфейс должен быть реализован в объекте. Дополнительные сведения см. в разделе [поддержка IDispatch и IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md).

Этот атрибут добавляет [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) класс как базовый класс для целевого объекта. Это приведет к реализация по умолчанию `ISupportErrorInfo` и может использоваться, когда отдельный интерфейс выдает ошибки для объекта.

## <a name="example"></a>Пример

Следующий код добавляет поддержку по умолчанию `ISupportErrorInfo` интерфейс `CMyClass` объекта.

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)  