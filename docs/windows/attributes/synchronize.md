---
title: Synchronize (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: a0f4702de4cfde8586cc573f9ff5a6195984d207
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214517"
---
# <a name="synchronize"></a>synchronize

Синхронизирует доступ к целевому методу.

## <a name="syntax"></a>Синтаксис

```cpp
[synchronize]
```

## <a name="remarks"></a>Remarks

Атрибут **Synchronize** C++ реализует поддержку синхронизации целевого метода объекта. Синхронизация позволяет нескольким объектам использовать общий ресурс (например, метод класса), управляя доступом к целевому методу.

Код, вставленный этим атрибутом, вызывает соответствующий метод `Lock` (определяется потоковой моделью) в начале целевого метода. Когда метод завершает работу, `Unlock` вызывается автоматически. Дополнительные сведения об этих функциях см. в разделе [ккомаутосреадмодуле:: Lock.](../../atl/reference/ccomautothreadmodule-class.md#lock)

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например, если применяется `progid`, применяются также `vi_progid` и `coclass`.

## <a name="example"></a>Пример

Следующий код обеспечивает синхронизацию для метода `UpdateBalance` объекта `CMyClass`.

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод класса, метод|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|Один или несколько из следующих элементов: `coclass`, `progid`или `vi_progid`.|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)
