---
title: __addgsbyte, __addgsword, __addgsdword, __addgsqword
ms.date: 11/04/2016
f1_keywords:
- __addgsdword
- __addgsqword
- __addgsword_cpp
- __addgsword
- __addgsbyte_cpp
- __addgsqword_cpp
- __addgsbyte
- __addgsdword_cpp
helpviewer_keywords:
- __addgsword intrinsic
- __addgsqword intrinsic
- __addgsdword intrinsic
- __addgsbyte intrinsic
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
ms.openlocfilehash: 9514c193468d526aa645ea7984691034feebc07a
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220469"
---
# <a name="addgsbyte-addgsword-addgsdword-addgsqword"></a>__addgsbyte, __addgsword, __addgsdword, __addgsqword

**Блок, относящийся только к системам Microsoft**

Добавить значение в ячейку памяти, указанной в качестве смещения относительно начала `GS` сегмента.

## <a name="syntax"></a>Синтаксис

```
void __addgsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addgsword(
   unsigned long Offset,
   unsigned short Data
);
void __addgsdword(
   unsigned long Offset,
   unsigned long Data
);
void __addgsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Параметры

*Смещение*<br/>
[in] Смещение от начала `GS`.

*Данные*<br/>
[in] Значение, добавляемое в область памяти.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__addgsbyte`|X64|
|`__addgsword`|X64|
|`__addgsdword`|X64|
|`__addgsqword`|X64|

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__incgsbyte, \__incgsword, \__incgsdword, \__incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)<br/>
[__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
