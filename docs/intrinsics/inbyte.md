---
title: __inbyte
ms.date: 11/04/2016
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 20c583b874c2bdb56affc6a90c8464b82c4824f0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040839"
---
# <a name="inbyte"></a>__inbyte

**Блок, относящийся только к системам Microsoft**

Создает `in` инструкции, возвращая один байт чтения с портом, указанным `Port`.

## <a name="syntax"></a>Синтаксис

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для чтения из.

## <a name="return-value"></a>Возвращаемое значение

Байт, считанный из указанного порта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)