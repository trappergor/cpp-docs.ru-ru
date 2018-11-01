---
title: __outbyte
ms.date: 11/04/2016
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: 8695fafb25be730ebe84828527d0689211c7801b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479028"
---
# <a name="outbyte"></a>__outbyte

**Блок, относящийся только к системам Microsoft**

Создает `out` инструкция, которая отправляет 1 байт, установленный параметром `Data` номера порта ввода-вывода, определяемое `Port`.

## <a name="syntax"></a>Синтаксис

```
void __outbyte( 
   unsigned short Port, 
   unsigned char Data 
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для отправки данных.

*Данные*<br/>
[in] Байт, будут отправлены для указанного порта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__outbyte`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)