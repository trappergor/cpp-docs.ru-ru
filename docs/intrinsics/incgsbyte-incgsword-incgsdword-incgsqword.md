---
title: __incgsbyte, __incgsword, __incgsdword, __incgsqword
ms.date: 11/04/2016
f1_keywords:
- __incgsdword
- __incgsqword_cpp
- __incgsword_cpp
- __incgsword
- __incgsbyte
- __incgsbyte_cpp
- __incgsqword
- __incgsdword_cpp
helpviewer_keywords:
- __incgsbyte intrinsic
- __incgsword intrinsic
- __incgsqword intrinsic
- __incgsdword intrinsic
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
ms.openlocfilehash: d1b394a578ada8afaec18cf3437fce4e654e89de
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326151"
---
# <a name="incgsbyte-incgsword-incgsdword-incgsqword"></a>__incgsbyte, __incgsword, __incgsdword, __incgsqword

**Блок, относящийся только к системам Microsoft**

Добавьте одно значение в ячейку памяти, указанной в качестве смещения относительно начала `GS` сегмента.

## <a name="syntax"></a>Синтаксис

```
void __incgsbyte(
   unsigned long Offset
);
void __incgsword(
   unsigned long Offset
);
void __incgsdword(
   unsigned long Offset
);
void __incgsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Параметры

*Смещение*<br/>
[in] Смещение от начала `GS`.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__incgsbyte`|X64|
|`__incgsword`|X64|
|`__incgsdword`|X64|
|`__incgsqword`|X64|

## <a name="remarks"></a>Примечания

Эти встроенные функции доступны только в режиме ядра и процедуры доступны только как встроенные функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__addgsbyte, \__addgsword, \__addgsdword, \__addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)<br/>
[__readgsbyte, \__readgsdword, \__readgsqword, \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)<br/>
[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)