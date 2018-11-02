---
title: __writefsbyte, __writefsdword, __writefsqword, __writefsword
ms.date: 11/04/2016
f1_keywords:
- __writefsword
- __writefsbyte
- __writefsqword
- __writefsdword
helpviewer_keywords:
- writefsbyte intrinsic
- __writefsword intrinsic
- writefsqword intrinsic
- writefsdword intrinsic
- __writefsdword intrinsic
- __writefsqword intrinsic
- __writefsbyte intrinsic
- writefsword intrinsic
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
ms.openlocfilehash: 5ee560576ebd3024e4eb555625c97f99c464f96c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517026"
---
# <a name="writefsbyte-writefsdword-writefsqword-writefsword"></a>__writefsbyte, __writefsdword, __writefsqword, __writefsword

**Блок, относящийся только к системам Microsoft**

Запись памяти в расположении, заданном в качестве смещения относительно начала сегмента FS.

## <a name="syntax"></a>Синтаксис

```
void __writefsbyte( 
   unsigned long Offset, 
   unsigned char Data 
);
void __writefsword( 
   unsigned long Offset, 
   unsigned short Data 
);
void __writefsdword( 
   unsigned long Offset, 
   unsigned long Data 
);
void __writefsqword( 
   unsigned long Offset, 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>Параметры

*Смещение*<br/>
[in] Смещение от начала FS для записи.

*Данные*<br/>
[in] Записываемое значение.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writefsbyte`|x86|
|`__writefsword`|x86|
|`__writefsdword`|x86|
|`__writefsqword`|x86|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные функции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)