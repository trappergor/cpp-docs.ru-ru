---
title: Макрос offsetof
ms.date: 11/04/2016
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: a0f367dbe6fa2681a7d413304f32b5699b8f7cee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156076"
---
# <a name="offsetof-macro"></a>Макрос offsetof

Возвращает смещение члена относительно начала его родительской структуры.

## <a name="syntax"></a>Синтаксис

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Параметры

*structName*<br/>
Имя родительской структуры данных.

*Имя пользователя*<br/>
Имя члена в родительской структуре данных, для которого определяется смещение.

## <a name="return-value"></a>Возвращаемое значение

**offsetof** Возвращает смещение в байтах указанного члена относительно начала его родительской структуры данных. Для битовых полей оно будет неопределенным.

## <a name="remarks"></a>Примечания

**Offsetof** макрос возвращает смещение в байтах *memberName* от начала структуры, указанной в *structName* как значение типа **size_ t**. Можно указать типы с **структуры** ключевое слово.

> [!NOTE]
> **offsetof** не является функцией и не может быть описан с помощью C прототипа.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
