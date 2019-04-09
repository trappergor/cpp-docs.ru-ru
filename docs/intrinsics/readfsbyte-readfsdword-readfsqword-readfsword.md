---
title: __readfsbyte, __readfsdword, __readfsqword, __readfsword
ms.date: 11/04/2016
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
ms.openlocfilehash: f291747d1f46ebdf3ea1f71cd9ab7e074058201d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036816"
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte, __readfsdword, __readfsqword, __readfsword

**Блок, относящийся только к системам Microsoft**

Прочитать память из расположения, указанной в качестве смещения относительно начала сегмента FS.

## <a name="syntax"></a>Синтаксис

```
unsigned char __readfsbyte(
   unsigned long Offset
);
unsigned short __readfsword(
   unsigned long Offset
);
unsigned long __readfsdword(
   unsigned long Offset
);
unsigned __int64 __readfsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Параметры

*Смещение*<br/>
[in] Смещение от начала `FS` считаны.

## <a name="return-value"></a>Возвращаемое значение

Содержимое памяти байт, слово, двойное или quadword (как указано в имени функции, вызываемой) в расположении `FS:[Offset]`.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)