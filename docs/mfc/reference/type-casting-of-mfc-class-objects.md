---
title: Приведение типов объектов классов MFC
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: 953acc32c3510b31c265f2d64d0a013f6dee06cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372894"
---
# <a name="type-casting-of-mfc-class-objects"></a>Приведение типов объектов классов MFC

Тип литья макросы обеспечивают способ бросить данный указатель на указатель, который указывает на объект конкретного класса, с или без проверки, что литые является законным.

В следующей таблице перечислены макросы литья типа MFC.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>Макрос, что кастовые указатели для MFC класса объектов

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Отбрасывает указатель на указатель на объект класса при проверке, является ли литые законным.|
|[STATIC_DOWNCAST](#static_downcast)|Отбрасывает указатель на объект из одного класса в указатель связанного типа. В отладке сборки вызывает ASSERT, если объект не является "видом" целевого типа.|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST

Предоставляет удобный способ бросить указатель на указатель на объект класса при проверке, если литые является законным.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Параметры

*class*<br/>
Имя класса.

*указатель*<br/>
Указатель, отбрасываемый на указатель на объект *класса*типа.

### <a name="remarks"></a>Remarks

Макрос будет отбрасывать параметр *указателя* на указатель на объект типа *класса.*

Если объект, на который ссылается указатель, является «видом» идентифицированного класса, макрос возвращает соответствующий указатель. Если это не юридический бросок, макровозвращает NULL.

## <a name="static_downcast"></a><a name="static_downcast"></a>STATIC_DOWNCAST

Бросает *пункт* к указателю на *class_name* объект.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса, в который отбрасываются.

*побъект*<br/>
Указатель, который будет отлит на указатель на *объект class_name.*

### <a name="remarks"></a>Remarks

*pobject* должен быть либо NULL, либо указывать на объект класса, который происходит прямо или косвенно от *class_name.* В сборках вашего приложения с определенным _DEBUG символом препроцессора, макрос будет УТВЕРЖДАТЬ, если *pobject* не является NULL, или если он указывает на объект, который не является "видом" класса, указанного в *class_name* параметре (см. [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). В **не-_DEBUG** сборки, макровыполняет литые без какой-либо проверки типа.

Класс, указанный в *class_name* параметре, должен быть выведен из `CObject` DECLARE_DYNAMIC и IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE, или DECLARE_SERIAL и IMPLEMENT_SERIAL макросов, как поясняется в статье [CObject Class: Вывод класса из CObject](../../mfc/deriving-a-class-from-cobject.md).

Например, можно отбросить указатель на , называется, `CMyDoc` `pMyDoc`на указатель на `CDocument` использование этого выражения:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Если `pMyDoc` не указывает на объект, полученный `CDocument`прямо или косвенно из, макрос будет ASSERT.

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
