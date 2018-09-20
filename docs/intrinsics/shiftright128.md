---
title: __shiftright128 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftright128
dev_langs:
- C++
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10e848321f105f60643f579c12772f6a40edebeb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383523"
---
# <a name="shiftright128"></a>__shiftright128

**Блок, относящийся только к системам Microsoft**

Сдвигает 128-разрядную величину, представленную в виде двух 64-разрядныхвеличин `HighPart``LowPart`и , `Shift` вправо на количество разрядов, указанное в  и возвращает младшие 64 разряда результата.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __shiftright128( 
   unsigned __int64 LowPart, 
   unsigned __int64 HighPart, 
   unsigned char Shift 
);
```

#### <a name="parameters"></a>Параметры

*Значение подверсии*<br/>
[in] Младшие 64 разряда 128-разрядной величины для сдвига.

*HighPart*<br/>
[in] Старшие 64 разряда 128-разрядной величины для сдвига.

*SHIFT*<br/>
[in] Количество битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Младшие 64 разряда результата.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__shiftright128`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Это значение `Shift` всегда берется по модулю 64, и, например, при вызове `__shiftright128(0, 1, 64)`, функция будет сдвигать вправо старшую часть `0` разрядов и возвращать младшую часть `0`, а не `1`, как в противном случае можно было ожидать.

## <a name="example"></a>Пример

Например, см. в разделе [__shiftleft128](../intrinsics/shiftleft128.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)