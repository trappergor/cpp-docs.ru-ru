---
title: __addfsbyte, __addfsword, __addfsdword
ms.date: 11/04/2016
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
ms.openlocfilehash: 61053d9f8c56d8352b12ed535dfa870c0856f558
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032707"
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte, __addfsword, __addfsdword

**Блок, относящийся только к системам Microsoft**

Добавить значение в ячейку памяти, указанной в качестве смещения относительно начала `FS` сегмента.

## <a name="syntax"></a>Синтаксис

```
void __addfsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addfsword(
   unsigned long Offset,
   unsigned short Data
);
void __addfsdword(
   unsigned long Offset,
   unsigned long Data
);
```

#### <a name="parameters"></a>Параметры

*Смещение*<br/>
[in] Смещение от начала `FS`.

*Данные*<br/>
[in] Значение, добавляемое в область памяти.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__addfsbyte`|x86|
|`__addfsword`|x86|
|`__addfsdword`|x86|

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__incfsbyte, \__incfsword, \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)<br/>
[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)