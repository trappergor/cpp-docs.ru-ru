---
title: __halt
ms.date: 11/04/2016
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: d99a87b1f3fd70d1fffb724629e9acded025732a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617182"
---
# <a name="halt"></a>__halt

**Блок, относящийся только к системам Microsoft**

Приостанавливает микропроцессор, пока не произойдет прерывание включена, немаскируемое прерывание (NMI) или сброс событий.

## <a name="syntax"></a>Синтаксис

```
void __halt( void );
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__halt`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`__halt` Функция эквивалентна `HLT` инструкции компьютера и доступна только в режиме ядра. Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)